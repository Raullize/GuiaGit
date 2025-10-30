<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🎯 Commits Semânticos

> **💡 Novo nos commits?** Comece com **[📜 O que são Commits](o-que-sao-commits.md)** para entender os fundamentos básicos.

## 🎯 O que são Commits Semânticos?

Os **Commits Semânticos** (Conventional Commits) são uma especificação para padronizar mensagens de commit, tornando-as legíveis tanto para humanos quanto para máquinas. Esta convenção facilita a automação de versionamento, geração de changelogs e integração com ferramentas de CI/CD.

### 🎯 Benefícios:
- **Automação**: Geração automática de changelogs e versionamento semântico
- **Clareza**: Mensagens estruturadas e consistentes
- **Colaboração**: Padrão universal reconhecido pela comunidade
- **Ferramentas**: Integração com ferramentas de análise e release

## 📋 Estrutura Oficial

A estrutura de um commit semântico segue o padrão definido pela especificação:

```plaintext
<tipo>[escopo opcional]: <descrição>

[corpo opcional]

[rodapé opcional]
```

### 🔍 Componentes:

1. **Tipo** (obrigatório): Categoria da mudança
2. **Escopo** (opcional): Área do código afetada
3. **Descrição** (obrigatória): Resumo conciso da mudança
4. **Corpo** (opcional): Explicação detalhada
5. **Rodapé** (opcional): Breaking changes, issues, co-autores

## 🏷️ Tipos de Commit (Especificação)

### 📝 Tipos Principais (Obrigatórios)

#### 1. **feat** ✨ - Novas Funcionalidades
Adiciona uma nova funcionalidade ao código.
```plaintext
feat(auth): adiciona login com Google OAuth
feat(api): implementa endpoints de usuário
feat: adiciona componente de carousel
```

#### 2. **fix** 🐛 - Correções de Bugs
Corrige um bug no código.
```plaintext
fix(auth): corrige validação de token expirado
fix(api): resolve memory leak em consultas
fix: ajusta posicionamento do modal
```

### 🔧 Tipos Complementares (Recomendados)

#### 3. **docs** 📚 - Documentação
Alterações apenas na documentação.
```plaintext
docs(readme): atualiza instruções de instalação
docs(api): adiciona exemplos de uso
docs: corrige typos na documentação
```

#### 4. **style** 💄 - Formatação
Mudanças que não afetam o significado do código (espaços, formatação, etc.).
```plaintext
style: remove espaços em branco
style(lint): ajusta indentação
style: aplica regras do prettier
```

#### 5. **refactor** ♻️ - Refatoração
Mudança de código que não corrige bug nem adiciona funcionalidade.
```plaintext
refactor(auth): simplifica lógica de validação
refactor: migra para async/await
refactor(models): reorganiza estrutura de dados
```

#### 6. **test** ✅ - Testes
Adiciona ou corrige testes.
```plaintext
test(auth): adiciona testes de integração
test: melhora cobertura de testes
test(utils): corrige mock de dados
```

#### 7. **chore** 🔧 - Manutenção
Mudanças no processo de build ou ferramentas auxiliares.
```plaintext
chore(deps): atualiza dependências
chore: configura pipeline CI
chore(release): prepara v1.0.0
```

#### 8. **perf** ⚡ - Performance
Mudança que melhora a performance.
```plaintext
perf(api): otimiza consultas ao banco
perf: adiciona índices de busca
perf(cache): implementa estratégia de cache
```

### 🎯 Tipos Adicionais (Opcionais)

#### 9. **ci** 🤖 - Integração Contínua
```plaintext
ci: adiciona workflow do GitHub Actions
ci(docker): atualiza configuração de build
```

#### 10. **build** 🏗️ - Sistema de Build
```plaintext
build: atualiza configuração do webpack
build(npm): adiciona script de deploy
```

#### 11. **revert** ⏪ - Reversão
```plaintext
revert: reverte commit abc123
```

## 🌟 Exemplos Completos da Especificação

### 🚨 Breaking Change (Mudança Incompatível)
```plaintext
feat(api)!: altera estrutura de autenticação

BREAKING CHANGE: A estrutura do token JWT foi alterada.
Agora inclui permissões no payload principal.

Antes:
{
  "user": "123",
  "exp": 1234567890
}

Depois:
{
  "user": "123",
  "permissions": ["read", "write"],
  "exp": 1234567890
}

Closes #123
```

### 🔧 Correção com Escopo e Contexto
```plaintext
fix(dashboard): corrige cálculo de métricas financeiras

- Ajusta fórmula de cálculo de ROI
- Corrige arredondamento para 2 casas decimais
- Adiciona validação de input para valores negativos
- Atualiza cache após recálculo

O bug estava causando diferenças de até 0.5% nos relatórios.

Resolves #456
Tested-by: @qa-team
```

### ♻️ Refatoração com Justificativa
```plaintext
refactor(auth): migra para novo sistema de permissões

- Separa lógica de autorização em middlewares específicos
- Implementa verificação granular por recurso
- Remove dependência do sistema legado
- Adiciona testes de integração para novos fluxos

Esta mudança prepara o sistema para suporte a roles
customizáveis que será implementado na v2.0.

Part of #789
Co-authored-by: @security-team
```

### 📚 Documentação com Múltiplas Alterações
```plaintext
docs(api): atualiza documentação da API v2

- Adiciona exemplos de autenticação OAuth2
- Documenta novos endpoints de usuário
- Corrige typos na seção de webhooks
- Adiciona diagramas de fluxo de dados
- Atualiza códigos de erro HTTP

See: #101, #102, #103
```

## 🔄 Comandos e Fluxo de Trabalho

### 📝 Criando Commits Semânticos
```powershell
# Commit simples (tipo + descrição)
git commit -m "feat: adiciona sistema de notificações"

# Commit com escopo
git commit -m "fix(auth): corrige validação de email"

# Commit com breaking change
git commit -m "feat(api)!: altera formato de resposta JSON"

# Commit com corpo (usar editor)
git commit
# No editor:
# feat(auth): implementa autenticação 2FA
# 
# - Adiciona geração de códigos TOTP
# - Integra com Google Authenticator
# - Implementa recovery codes
# - Adiciona testes de segurança
```

### ✏️ Editando o Último Commit
```powershell
# Corrigir tipo ou escopo
git commit --amend -m "fix(auth): implementa autenticação 2FA"

# Adicionar mudanças esquecidas mantendo a mensagem
git add arquivo-esquecido.js
git commit --amend --no-edit

# Editar mensagem completa no editor
git commit --amend
```

## 🤖 Automação e Ferramentas

### 📋 Commitlint (Validação)
```json
// .commitlintrc.json
{
  "extends": ["@commitlint/config-conventional"],
  "rules": {
    "type-enum": [2, "always", [
      "feat", "fix", "docs", "style", "refactor",
      "test", "chore", "perf", "ci", "build", "revert"
    ]],
    "type-case": [2, "always", "lower-case"],
    "type-empty": [2, "never"],
    "subject-empty": [2, "never"],
    "subject-full-stop": [2, "never", "."],
    "header-max-length": [2, "always", 72]
  }
}
```

### 🎯 Commitizen (Assistente Interativo)
```powershell
# Instalar globalmente
npm install -g commitizen cz-conventional-changelog

# Configurar no projeto
echo '{ "path": "cz-conventional-changelog" }' > ~/.czrc

# Usar assistente interativo
git cz
# ou
npx cz
```

### 🔄 Husky (Git Hooks)
```json
// package.json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```

```bash
# .husky/commit-msg
#!/bin/sh
npx --no -- commitlint --edit $1
```

### 📊 Semantic Release (Automação de Versões)
```json
// .releaserc.json
{
  "branches": ["main"],
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/changelog",
    "@semantic-release/npm",
    "@semantic-release/github"
  ]
}
```

### 📈 Conventional Changelog
```powershell
# Instalar
npm install -g conventional-changelog-cli

# Gerar changelog
conventional-changelog -p angular -i CHANGELOG.md -s

# Gerar changelog completo
conventional-changelog -p angular -i CHANGELOG.md -s -r 0
```

## 🔗 Próximos Passos

Para implementar commits semânticos efetivamente:

- **[🧑‍💻 Mantendo um Padrão](mantendo-um-padrão-de-commits.md)** - Aprenda a implementar e manter padrões em equipe
- **[📜 O que são Commits](o-que-sao-commits.md)** - Revise os conceitos fundamentais
- **[🎨 Commits com Emojis](emojis.md)** - Explore alternativas visuais complementares

### 📈 **Próximos Níveis**
1. **[🧑‍💻 Implementar em equipe](mantendo-um-padrão-de-commits.md)** - Governança e práticas colaborativas
2. **[🎨 Adicionar emojis](emojis.md)** - Alternativa visual para identificação rápida
3. **Configurar automação** - CI/CD e ferramentas de release
4. **Estabelecer métricas** - Qualidade e produtividade da equipe

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>