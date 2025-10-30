<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🧑‍💻 Mantendo um Padrão de Commits

> **📋 Pré-requisitos:** Este guia assume conhecimento de **[📜 O que são Commits](o-que-sao-commits.md)** e **[🎯 Commits Semânticos](commits-semanticos.md)**.

## 🎯 Por que Padronizar em Equipe?

Manter um padrão consistente de commits é fundamental para o sucesso de projetos colaborativos. Vai além de simplesmente escrever mensagens bonitas - é sobre criar um sistema que facilite a comunicação, automação e manutenção do código.

### 🌟 Benefícios da Padronização:

#### 📈 **Para o Projeto**
- **Histórico Legível**: Facilita revisão de código e debugging
- **Automação**: Permite geração automática de changelogs e releases
- **Rastreabilidade**: Conecta mudanças com issues e requisitos
- **Qualidade**: Reduz bugs através de commits mais focados

#### 👥 **Para a Equipe**
- **Comunicação Clara**: Todos entendem o que foi alterado
- **Onboarding Rápido**: Novos membros se adaptam mais facilmente
- **Revisão Eficiente**: Code reviews mais rápidos e precisos
- **Colaboração**: Reduz conflitos e mal-entendidos

#### 🏢 **Para a Organização**
- **Compliance**: Atende requisitos de auditoria e governança
- **Métricas**: Permite análise de produtividade e qualidade
- **Documentação**: Histórico serve como documentação técnica
- **Manutenção**: Facilita correções e atualizações futuras

## 🏗️ Implementando Padrões em Equipe

### 1. 📋 Definindo o Padrão

#### 🎯 **Escolha da Convenção**
```markdown
## Opções Populares:

✅ **Conventional Commits** (Recomendado)
- Padrão da indústria
- Suporte amplo de ferramentas
- Automação robusta

✅ **Gitmoji** (Visual)
- Identificação rápida por emojis
- Boa para equipes visuais
- Pode ser combinado com Conventional

✅ **Padrão Customizado**
- Adaptado às necessidades específicas
- Requer mais documentação
- Menor suporte de ferramentas
```

#### 📝 **Documentação do Padrão**
```markdown
# COMMIT_GUIDELINES.md

## Estrutura Obrigatória
tipo(escopo): descrição

## Tipos Permitidos
- feat: nova funcionalidade
- fix: correção de bug
- docs: documentação
- style: formatação
- refactor: refatoração
- test: testes
- chore: manutenção

## Regras
1. Usar presente do indicativo
2. Não usar ponto final
3. Máximo 72 caracteres no título
4. Escopo obrigatório para mudanças em módulos específicos
5. Corpo obrigatório para breaking changes

## Exemplos
✅ feat(auth): adiciona login com Google
✅ fix(api): corrige timeout em requests
❌ Arrumei o bug do login
❌ feat: implementa várias coisas
```

### 2. 🛠️ Ferramentas de Enforcement

#### 🔒 **Git Hooks com Husky**
```json
// package.json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.{js,ts}": ["eslint --fix", "git add"],
    "*.md": ["markdownlint --fix", "git add"]
  }
}
```

#### ⚙️ **Configuração do Commitlint**
```json
// .commitlintrc.json
{
  "extends": ["@commitlint/config-conventional"],
  "rules": {
    "type-enum": [2, "always", [
      "feat", "fix", "docs", "style", "refactor", 
      "test", "chore", "perf", "ci", "build"
    ]],
    "scope-enum": [2, "always", [
      "auth", "api", "ui", "db", "config", "docs"
    ]],
    "scope-empty": [2, "never"],
    "subject-case": [2, "always", "lower-case"],
    "header-max-length": [2, "always", 72],
    "body-max-line-length": [2, "always", 100]
  }
}
```

#### 🎯 **Template de Commit**
```bash
# .gitmessage
# tipo(escopo): descrição curta (máx 72 chars)
#
# Corpo da mensagem (opcional):
# - Explique o QUE e POR QUE, não o COMO
# - Use bullet points para múltiplas mudanças
# - Referencie issues: Closes #123, Fixes #456
#
# Rodapé (opcional):
# BREAKING CHANGE: descreva mudanças incompatíveis
# Co-authored-by: Nome <email@exemplo.com>

# Configurar template globalmente:
# git config --global commit.template ~/.gitmessage
```

### 3. 🎓 Treinamento da Equipe

#### 📚 **Workshop de Onboarding**
```markdown
## Agenda do Workshop (2h)

### Parte 1: Fundamentos (30min)
- Por que commits importam?
- Impacto no workflow da equipe
- Demonstração de problemas comuns

### Parte 2: Padrão da Equipe (45min)
- Apresentação do padrão escolhido
- Exemplos práticos do projeto
- Exercícios hands-on

### Parte 3: Ferramentas (30min)
- Configuração do ambiente
- Uso do commitizen
- Resolução de problemas

### Parte 4: Q&A (15min)
- Dúvidas e casos especiais
- Feedback sobre o processo
```

#### 🎮 **Exercícios Práticos**
```powershell
# Exercício 1: Corrigir commits ruins
git log --oneline -10
# Identificar problemas e reescrever mensagens

# Exercício 2: Criar commits para cenários
# Cenário: Adicionar validação de email no formulário de cadastro
# Resposta esperada: feat(auth): adiciona validação de email no cadastro

# Exercício 3: Usar commitizen
npx cz
# Praticar o fluxo interativo
```

## 🔍 Revisão e Qualidade

### 📝 **Checklist para Code Review**

#### 👤 **Para o Autor**
```markdown
## Antes de Criar o PR

### Commits
- [ ] Cada commit representa uma mudança lógica
- [ ] Mensagens seguem o padrão da equipe
- [ ] Não há commits de "fix typo" ou "wip"
- [ ] Breaking changes estão documentadas

### Código
- [ ] Testes passando
- [ ] Linting sem erros
- [ ] Documentação atualizada
- [ ] Sem código comentado ou debug
```

#### 👥 **Para o Reviewer**
```markdown
## Durante a Revisão

### Histórico de Commits
- [ ] Commits são atômicos e bem descritos
- [ ] Sequência lógica de mudanças
- [ ] Mensagens explicam o "por quê"
- [ ] Referências a issues estão corretas

### Feedback Construtivo
✅ "O commit 'feat(api): adiciona cache' poderia incluir no corpo quais endpoints foram afetados"
❌ "Commit ruim"

✅ "Considere dividir este commit em dois: um para a feature e outro para os testes"
❌ "Muita coisa em um commit"
```

### 🔄 **Processo de Correção**
```powershell
# Cenário: Commits precisam ser ajustados antes do merge

# 1. Rebase interativo para limpar histórico
git rebase -i HEAD~3

# 2. Squash commits relacionados
# No editor: mudar 'pick' para 'squash' nos commits a unir

# 3. Reescrever mensagens conforme padrão
# 4. Force push (cuidado em branches compartilhadas)
git push --force-with-lease origin feature-branch
```

## 📊 Monitoramento e Métricas

### 📈 **Métricas de Qualidade**
```powershell
# Análise de conformidade com padrões
git log --oneline --since="1 month ago" | grep -E "^(feat|fix|docs|style|refactor|test|chore)" | wc -l

# Commits por tipo (últimos 30 dias)
git log --oneline --since="30 days ago" --pretty=format:"%s" | sed 's/:.*$//' | sort | uniq -c | sort -nr

# Autores mais ativos
git shortlog -sn --since="1 month ago"

# Tamanho médio de commits
git log --oneline --since="1 month ago" --pretty=format:"%s" | awk '{print length}' | awk '{sum+=$1; n++} END {print sum/n}'
```

### 🎯 **Dashboard de Commits**
```json
// Exemplo de métricas para dashboard
{
  "period": "last_30_days",
  "metrics": {
    "total_commits": 156,
    "conventional_compliance": "94%",
    "average_message_length": 48,
    "types_distribution": {
      "feat": 45,
      "fix": 32,
      "docs": 12,
      "refactor": 18,
      "test": 25,
      "chore": 24
    },
    "scope_usage": "87%",
    "breaking_changes": 3
  }
}
```

## 🚀 Automação Avançada

### 🔄 **CI/CD Integration**
```yaml
# .github/workflows/commit-validation.yml
name: Commit Validation

on: [push, pull_request]

jobs:
  validate-commits:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      
      - name: Validate Commit Messages
        uses: wagoid/commitlint-github-action@v5
        with:
          configFile: '.commitlintrc.json'
      
      - name: Generate Commit Report
        run: |
          echo "## Commit Analysis" >> $GITHUB_STEP_SUMMARY
          git log --oneline --since="1 week ago" --pretty=format:"- %s" >> $GITHUB_STEP_SUMMARY
```

### 📦 **Release Automation**
```json
// .releaserc.json
{
  "branches": ["main"],
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    [
      "@semantic-release/changelog",
      {
        "changelogFile": "CHANGELOG.md"
      }
    ],
    "@semantic-release/npm",
    [
      "@semantic-release/git",
      {
        "assets": ["CHANGELOG.md", "package.json"],
        "message": "chore(release): ${nextRelease.version} [skip ci]\n\n${nextRelease.notes}"
      }
    ],
    "@semantic-release/github"
  ]
}
```

## 🎯 Casos Especiais e Soluções

### 🔄 **Migração de Projetos Existentes**
```markdown
## Estratégia de Migração Gradual

### Fase 1: Preparação (Semana 1)
- [ ] Definir padrão da equipe
- [ ] Configurar ferramentas
- [ ] Treinar equipe

### Fase 2: Soft Launch (Semana 2-3)
- [ ] Aplicar apenas em novas features
- [ ] Feedback e ajustes
- [ ] Documentar casos especiais

### Fase 3: Enforcement (Semana 4+)
- [ ] Ativar hooks obrigatórios
- [ ] Revisar PRs existentes
- [ ] Monitorar métricas
```

### 🚨 **Tratamento de Emergências**
```powershell
# Hotfix urgente - processo simplificado
git checkout main
git checkout -b hotfix/critical-security-fix
# Fazer correção mínima
git commit -m "fix(security): corrige vulnerabilidade XSS crítica

Closes #URGENT-123
Security-Impact: Critical"
git push origin hotfix/critical-security-fix
# Merge direto após revisão expressa
```

### 🔀 **Merge vs Rebase Strategy**
```markdown
## Política de Merge da Equipe

### Feature Branches
- **Rebase** antes do merge para histórico linear
- **Squash** commits de desenvolvimento
- **Manter** commits semânticos finais

### Hotfixes
- **Merge direto** para preservar contexto de urgência
- **Cherry-pick** para outras branches se necessário

### Release Branches
- **Merge commit** para marcar releases
- **Tag** com versão semântica
```

## 🔗 Recursos e Próximos Passos

### 📚 **Documentação Complementar**
- **[📜 O que são Commits](o-que-sao-commits.md)** - Fundamentos básicos
- **[🎯 Commits Semânticos](commits-semanticos.md)** - Especificação técnica detalhada
- **[🎨 Commits com Emojis](emojis.md)** - Alternativas visuais

### 🛠️ **Ferramentas Recomendadas**
- **Commitizen**: Assistente interativo para commits
- **Commitlint**: Validação de mensagens
- **Husky**: Git hooks automatizados
- **Semantic Release**: Automação de releases
- **Conventional Changelog**: Geração de changelogs

### 📈 **Próximos Níveis**
1. **Implementar métricas de qualidade**
2. **Configurar automação de releases**
3. **Integrar com ferramentas de project management**
4. **Criar dashboards de produtividade**
5. **Estabelecer políticas de governança**

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>