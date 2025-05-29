<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🎯 Commits Semânticos

## 📋 Estrutura

A estrutura de um commit semântico segue o padrão:

```plaintext
tipo(escopo opcional): descrição

corpo opcional

rodapé opcional
```

## 🏷️ Tipos de Commit

### 1. feat ✨
**Novas funcionalidades**
```plaintext
feat(auth): adiciona login com Google
feat(api): implementa endpoints de usuário
feat(ui): adiciona componente de carousel
```

### 2. fix 🐛
**Correções de bugs**
```plaintext
fix(auth): corrige validação de token expirado
fix(api): resolve memory leak em consultas
fix(ui): ajusta posicionamento do modal
```

### 3. docs 📚
**Documentação**
```plaintext
docs(readme): atualiza instruções de instalação
docs(api): adiciona exemplos de uso
docs(contributing): adiciona guia de estilo
```

### 4. style 💄
**Formatação de código**
```plaintext
style(lint): ajusta indentação
style(format): remove espaços em branco
style(prettier): aplica regras de formatação
```

### 5. refactor ♻️
**Refatoração de código**
```plaintext
refactor(auth): simplifica lógica de validação
refactor(api): migra para async/await
refactor(models): reorganiza estrutura de dados
```

### 6. test ✅
**Testes**
```plaintext
test(auth): adiciona testes de integração
test(api): melhora cobertura de testes
test(utils): corrige mock de dados
```

### 7. chore 🔧
**Manutenção**
```plaintext
chore(deps): atualiza dependências
chore(build): configura pipeline CI
chore(release): prepara v1.0.0
```

### 8. perf ⚡
**Performance**
```plaintext
perf(api): otimiza consultas ao banco
perf(queries): adiciona índices
perf(cache): implementa estratégia de cache
```

## 🌟 Exemplos Completos

### Feature com Breaking Change
```plaintext
feat(api)!: altera estrutura de autenticação

BREAKING CHANGE: A estrutura do token JWT foi alterada.
Agora inclui permissões no payload.

Closes #123
```

### Correção com Escopo
```plaintext
fix(dashboard): corrige cálculo de métricas

- Ajusta fórmula de cálculo de ROI
- Atualiza cache após recálculo
- Adiciona validação de input

Resolves #456
```

### Refatoração com Contexto
```plaintext
refactor(auth): migra para novo sistema de permissões

- Separa lógica em middlewares
- Implementa verificação granular
- Adiciona testes de integração

Part of #789
```

## 🔄 Fluxo de Trabalho

### 1. Preparando o Commit
```powershell
# Verificar alterações
git status

# Adicionar arquivos
git add .

# Visualizar alterações
git diff --staged
```

### 2. Criando o Commit
```powershell
# Commit simples
git commit -m "feat: adiciona sistema de notificações"

# Commit com corpo
git commit -m "feat(auth): implementa 2FA

- Adiciona geração de códigos TOTP
- Integra com autenticador Google
- Implementa recovery codes"
```

### 3. Ajustando o Último Commit
```powershell
# Editar mensagem
git commit --amend -m "feat(auth): implementa autenticação 2FA"

# Adicionar mudanças esquecidas
git add .
git commit --amend --no-edit
```

## 🤖 Automação

### Commitlint
```json
// .commitlintrc.json
{
  "extends": ["@commitlint/config-conventional"],
  "rules": {
    "type-enum": [2, "always", [
      "feat", "fix", "docs", "style", "refactor",
      "test", "chore", "perf", "ci", "build", "temp"
    ]]
  }
}
```

### Husky
```json
// .husky/commit-msg
#!/bin/sh
npx --no -- commitlint --edit $1
```

### Commitizen
```powershell
# Instalar
npm install -g commitizen

# Configurar
commitizen init cz-conventional-changelog

# Usar
git cz
```

## 📊 Análise de Commits

### Conventional Changelog
```powershell
# Gerar changelog
conventional-changelog -p angular -i CHANGELOG.md -s
```

### Semantic Release
```json
// package.json
{
  "release": {
    "branches": ["main"],
    "plugins": [
      "@semantic-release/commit-analyzer",
      "@semantic-release/release-notes-generator",
      "@semantic-release/changelog",
      "@semantic-release/github",
      "@semantic-release/npm"
    ]
  }
}
```

## 🎯 Dicas Práticas

### 1. Mantenha Commits Atômicos
✅ Um commit = Uma alteração lógica
❌ Evite commits com múltiplas alterações não relacionadas

### 2. Seja Descritivo
✅ "feat(auth): implementa recuperação de senha"
❌ "atualiza código"

### 3. Use o Corpo do Commit
✅ Explique o "por quê" das mudanças
✅ Liste alterações principais
✅ Referencie issues relacionadas

### 4. Evite Commits Temporários
❌ "wip"
❌ "teste"
❌ "fix bug"

### 5. Mantenha Consistência
✅ Siga o padrão do projeto
✅ Use ferramentas de lint
✅ Revise commits antes do push

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>