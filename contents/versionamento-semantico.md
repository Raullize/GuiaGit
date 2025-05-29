<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📌 Versionamento Semântico (SemVer)

## 🔢 Formato Básico

O versionamento semântico segue o formato `MAJOR.MINOR.PATCH` (`X.Y.Z`):

### MAJOR (X) ⚠️
- Mudanças incompatíveis com versões anteriores
- Breaking changes
- Exemplos:
  ```plaintext
  1.0.0 → 2.0.0: Refatoração completa da API
  2.0.0 → 3.0.0: Mudança na estrutura de autenticação
  ```

### MINOR (Y) ✨
- Novas funcionalidades compatíveis
- Adições sem quebrar compatibilidade
- Exemplos:
  ```plaintext
  1.0.0 → 1.1.0: Adição de novo endpoint
  1.1.0 → 1.2.0: Nova feature de exportação
  ```

### PATCH (Z) 🐛
- Correções de bugs
- Patches de segurança
- Exemplos:
  ```plaintext
  1.1.0 → 1.1.1: Correção de bug no login
  1.1.1 → 1.1.2: Atualização de dependência
  ```

## 🏷️ Identificadores Especiais

### Pre-release 🚧
```plaintext
1.0.0-alpha.1
1.0.0-beta.2
1.0.0-rc.1
```

### Build Metadata 🔨
```plaintext
1.0.0+20130313144700
1.0.0-beta+exp.sha.5114f85
```

## 📝 Exemplos Práticos

### 1. Commit Messages → Versão

```plaintext
feat: adiciona novo endpoint
↓
MINOR (Y) increment

fix: corrige validação de formulário
↓
PATCH (Z) increment

feat!: altera API de autenticação
↓
MAJOR (X) increment
```

### 2. Cenários Comuns

#### Lançamento Inicial
```plaintext
0.1.0: Primeira versão alpha
0.2.0: Beta com novas features
1.0.0: Primeira versão estável
```

#### Ciclo de Desenvolvimento
```plaintext
1.0.0: Lançamento inicial
1.0.1: Hotfix de segurança
1.1.0: Nova funcionalidade
2.0.0: Redesign completo
```

## 🤖 Automação de Versões

### 1. Usando standard-version

```powershell
# Instalar
npm install -g standard-version

# Primeira release
standard-version --first-release

# Release normal
standard-version

# Release específica
standard-version --release-as minor
```

### 2. Usando semantic-release

```powershell
# Instalar
npm install -g semantic-release

# Configurar no package.json
{
  "release": {
    "branches": ["main"]
  }
}

# Executar
semantic-release
```

### 3. GitHub Actions Workflow

```yaml
name: Release
on:
  push:
    branches: [main]

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
      - run: npm ci
      - run: npx semantic-release
```

## 📋 Changelog Automático

### 1. Conventional Changelog

```powershell
# Instalar
npm install -g conventional-changelog-cli

# Gerar changelog
conventional-changelog -p angular -i CHANGELOG.md -s
```

### 2. Exemplo de CHANGELOG.md

```markdown
# Changelog

## [2.0.0] - 2025-05-29
### Breaking Changes
- Altera estrutura da API de autenticação

### Added
- Suporte a OAuth 2.0
- Novo endpoint para refresh token

### Fixed
- Correção na validação de tokens

## [1.1.0] - 2025-05-28
### Added
- Nova funcionalidade de exportação
- Suporte a múltiplos formatos

### Changed
- Melhoria na performance do cache
```

## 🔄 Fluxo de Release

1. **Desenvolvimento**
   ```powershell
   git checkout -b feature/nova-funcionalidade
   # desenvolver features...
   ```

2. **Preparação**
   ```powershell
   git checkout main
   git merge feature/nova-funcionalidade
   ```

3. **Versionamento**
   ```powershell
   standard-version
   ```

4. **Release**
   ```powershell
   git push --follow-tags origin main
   ```

## ⚠️ Considerações Importantes

1. **Compatibilidade**
- Documente breaking changes
- Mantenha changelog atualizado
- Forneça guias de migração

2. **Comunicação**
- Anuncie mudanças importantes
- Mantenha roadmap público
- Colete feedback dos usuários

3. **Manutenção**
- Suporte LTS para versões major
- Backport de fixes críticos
- Deprecie features gradualmente

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>