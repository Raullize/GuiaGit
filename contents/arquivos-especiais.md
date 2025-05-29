<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📜 Arquivos Especiais no Git

## 🔒 Arquivos de Configuração

### .gitignore 🚫
Controla quais arquivos o Git deve ignorar.

#### Estrutura Básica
```plaintext
# Comentários começam com #
*.log        # Ignora todos arquivos .log
build/       # Ignora pasta build
/dist        # Ignora dist apenas na raiz
node_modules # Ignora node_modules em qualquer lugar
!important.log # Não ignora important.log
```

#### Padrões Comuns
```plaintext
# Dependências
node_modules/
vendor/
*.jar

# Ambiente
.env
.env.local
*.env*
!.env.example

# Build
/dist
/build
/out

# IDE
.vscode/
.idea/
*.sublime-*

# Logs
*.log
npm-debug.log*
yarn-debug.log*

# Sistema
.DS_Store
Thumbs.db
```

### .gitattributes 🔧
Define atributos para caminhos.

#### Configurações Comuns
```plaintext
# Auto detecção de texto
* text=auto

# Forçar LF para scripts
*.sh text eol=lf
*.bash text eol=lf
*.py text eol=lf

# Forçar CRLF para scripts Windows
*.bat text eol=crlf
*.cmd text eol=crlf

# Arquivos binários
*.png binary
*.jpg binary
*.gif binary
*.ico binary
*.zip binary

# Linguagens específicas
*.cs diff=csharp
*.html diff=html
*.java diff=java
*.md diff=markdown
```

### .gitconfig ⚙️
Configuração global do Git.

#### Configurações Úteis
```ini
[user]
    name = Seu Nome
    email = seu.email@exemplo.com
    signingkey = sua-chave-gpg

[core]
    editor = code --wait
    autocrlf = input
    whitespace = trailing-space,space-before-tab

[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    lg = log --graph --pretty=format:'%C(red)%h%C(reset) -%C(yellow)%d%C(reset) %s %C(green)(%cr) %C(bold blue)<%an>%C(reset)'

[commit]
    template = ~/.gitmessage
    gpgsign = true

[pull]
    rebase = true

[merge]
    tool = vscode
```

## 📋 Documentação

### README.md 📖
```markdown
# Nome do Projeto

## Descrição
Breve descrição do projeto.

## Instalação
\`\`\`bash
npm install
\`\`\`

## Uso
\`\`\`javascript
const exemplo = require('exemplo');
exemplo.start();
\`\`\`

## Contribuição
1. Fork o projeto
2. Crie sua Feature Branch
3. Commit suas mudanças
4. Push para a Branch
5. Abra um Pull Request

## Licença
MIT
```

### CONTRIBUTING.md 🤝
```markdown
# Guia de Contribuição

## Processo
1. Verifique issues existentes
2. Discuta mudanças maiores
3. Siga style guide
4. Escreva testes
5. Atualize documentação

## Commits
- Use commits semânticos
- Mantenha commits atômicos
- Referencie issues

## Pull Requests
- Use template
- Inclua testes
- Atualize docs
```

### CHANGELOG.md 📝
```markdown
# Changelog

## [2.0.0] - 2025-05-29
### Breaking Changes
- Alteração na API principal

### Added
- Nova funcionalidade X
- Suporte para Y

### Fixed
- Bug #123
- Performance issue #456

## [1.1.0] - 2025-05-28
### Added
- Feature Z
```

## 🔧 Arquivos de CI/CD

### .github/workflows 🔄
```yaml
# ci.yml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node
        uses: actions/setup-node@v2
      - run: npm ci
      - run: npm test
```

### Issue Templates 📋
```yaml
# .github/ISSUE_TEMPLATE/bug_report.yml
name: Bug Report
description: Reporte um bug
body:
  - type: markdown
    attributes:
      value: |
        Descreva o bug em detalhes
  - type: input
    id: version
    attributes:
      label: Versão
    validations:
      required: true
```

### PR Template 📑
```markdown
# .github/pull_request_template.md

## Descrição
Descreva suas alterações

## Tipo de mudança
- [ ] Bug fix
- [ ] Nova feature
- [ ] Breaking change

## Checklist
- [ ] Testes atualizados
- [ ] Documentação atualizada
```

## 🪝 Git Hooks

### pre-commit
```bash
#!/bin/bash
# .git/hooks/pre-commit

# Executar linter
npm run lint

# Executar testes
npm test

# Verificar commits
npx commitlint --edit
```

### pre-push
```bash
#!/bin/bash
# .git/hooks/pre-push

# Executar testes completos
npm run test:full

# Verificar build
npm run build
```

### commit-msg
```bash
#!/bin/bash
# .git/hooks/commit-msg

# Validar mensagem de commit
npx commitlint --edit $1
```

## 🔐 Segurança

### .env.example
```plaintext
# Configurações do App
APP_NAME=MeuApp
APP_ENV=development
APP_KEY=sua-chave-secreta

# Database
DB_HOST=localhost
DB_PORT=5432
DB_USER=user
DB_PASS=password

# APIs
API_KEY=sua-api-key
STRIPE_KEY=sua-stripe-key
```

### .npmrc
```plaintext
save-exact=true
package-lock=false
registry=https://registry.npmjs.org/
//registry.npmjs.org/:_authToken=${NPM_TOKEN}
```

## 🎨 Editor Config

### .editorconfig
```ini
root = true

[*]
charset = utf-8
end_of_line = lf
indent_style = space
indent_size = 2
insert_final_newline = true
trim_trailing_whitespace = true

[*.md]
trim_trailing_whitespace = false

[*.{java,py}]
indent_size = 4
```

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>