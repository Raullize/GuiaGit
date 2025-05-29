# 🧩 Git Hooks e Automação

## 🎯 O que são Git Hooks?

Git Hooks são scripts que o Git executa automaticamente antes ou depois de eventos como commit, push e merge. Eles permitem personalizar o comportamento interno do Git e acionar ações customizadas em pontos específicos do seu workflow.

## 📂 Localização dos Hooks

Os hooks ficam no diretório `.git/hooks/` do seu repositório. Cada hook é um arquivo executável sem extensão (Linux/Mac) ou com extensão .bat/.ps1 (Windows).

```powershell
# Ver hooks disponíveis
ls .git/hooks/
```

## 🔄 Tipos de Hooks

### 1. Hooks de Commit

#### pre-commit
Executa antes da mensagem de commit ser criada
```bash
#!/bin/bash
# .git/hooks/pre-commit

# Executar linter
npm run lint

# Executar testes
npm test

# Se algum comando falhar, impede o commit
if [ $? -ne 0 ]; then
    echo "❌ Testes falharam. Commit abortado."
    exit 1
fi
```

#### prepare-commit-msg
Executa antes do editor de mensagem de commit abrir
```bash
#!/bin/bash
# .git/hooks/prepare-commit-msg

# Adicionar branch name ao commit
BRANCH_NAME=$(git branch --show-current)
echo "$BRANCH_NAME: $(cat $1)" > $1
```

#### commit-msg
Valida a mensagem do commit
```bash
#!/bin/bash
# .git/hooks/commit-msg

# Validar formato do commit
if ! grep -qE "^(feat|fix|docs|style|refactor|test|chore)(\(.+\))?: .{1,}$" "$1"; then
    echo "❌ Commit message deve seguir o formato: tipo(escopo): mensagem"
    exit 1
fi
```

### 2. Hooks de Email

#### pre-rebase
Executa antes do rebase
```bash
#!/bin/bash
# .git/hooks/pre-rebase

# Impedir rebase da main
if [ "$1" = "main" ]; then
    echo "❌ Não é permitido rebase na main"
    exit 1
fi
```

#### post-rewrite
Executa após comandos que reescrevem commits
```bash
#!/bin/bash
# .git/hooks/post-rewrite

# Atualizar dependências após rebase
if [ "$1" = "rebase" ]; then
    npm install
fi
```

### 3. Hooks de Rede

#### pre-push
Executa antes do push
```bash
#!/bin/bash
# .git/hooks/pre-push

# Executar testes
npm run test:full

# Verificar build
npm run build

# Verificar tamanho do bundle
if [ $(stat -f%z dist/bundle.js) -gt 1000000 ]; then
    echo "❌ Bundle muito grande!"
    exit 1
fi
```

#### post-receive
Executa após receber um push (servidor)
```bash
#!/bin/bash
# .git/hooks/post-receive

# Deploy automático
git --work-tree=/var/www/html --git-dir=/var/repo/site.git checkout -f
npm install
npm run build
```

## 🛠️ Implementação com Husky

### 1. Instalação
```powershell
# Instalar Husky
npm install husky --save-dev

# Ativar hooks
npx husky install
```

### 2. Configuração
```json
// package.json
{
  "scripts": {
    "prepare": "husky install"
  },
  "husky": {
    "hooks": {
      "pre-commit": "npm test",
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
      "pre-push": "npm run build"
    }
  }
}
```

### 3. Criando Hooks
```powershell
# Adicionar hook
npx husky add .husky/pre-commit "npm test"
npx husky add .husky/commit-msg "npx commitlint --edit $1"
```

## 🔄 Workflows Comuns

### 1. Validação de Código
```bash
#!/bin/bash
# .husky/pre-commit

# Executar ESLint
npm run lint

# Executar Prettier
npm run format

# Executar TypeScript
npm run type-check
```

### 2. Testes Automatizados
```bash
#!/bin/bash
# .husky/pre-push

# Executar testes unitários
npm run test:unit

# Executar testes e2e
npm run test:e2e

# Verificar cobertura
npm run test:coverage
```

### 3. Conventional Commits
```bash
#!/bin/bash
# .husky/commit-msg

# Validar mensagem do commit
npx --no -- commitlint --edit $1
```

## 🔧 Ferramentas Úteis

### 1. lint-staged
```json
// package.json
{
  "lint-staged": {
    "*.{js,jsx,ts,tsx}": [
      "eslint --fix",
      "prettier --write"
    ],
    "*.{json,md}": [
      "prettier --write"
    ]
  }
}
```

### 2. commitlint
```javascript
// commitlint.config.js
module.exports = {
  extends: ['@commitlint/config-conventional'],
  rules: {
    'type-enum': [2, 'always', [
      'feat', 'fix', 'docs', 'style', 'refactor',
      'test', 'chore', 'revert', 'perf'
    ]]
  }
};
```

### 3. release-it
```json
// .release-it.json
{
  "git": {
    "commitMessage": "chore: release v${version}",
    "tagName": "v${version}",
    "requireCleanWorkingDir": true
  },
  "hooks": {
    "before:init": ["npm test"],
    "after:release": "echo Successfully released ${version}"
  }
}
```

## ⚠️ Considerações Importantes

### 1. Desempenho
- Mantenha hooks leves e rápidos
- Use lint-staged para verificar apenas arquivos alterados
- Cache resultados quando possível

### 2. Manutenção
- Documente hooks personalizados
- Mantenha hooks no controle de versão
- Use ferramentas padronizadas

### 3. Colaboração
- Comunique mudanças nos hooks
- Forneça forma de pular hooks (--no-verify)
- Considere diferentes ambientes de desenvolvimento
