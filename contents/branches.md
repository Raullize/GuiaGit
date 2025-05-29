<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🌿 O que são Branches?

Branches são ramificações que permitem trabalhar em diferentes linhas de desenvolvimento dentro de um mesmo repositório.

## 🚀 Por que usar branches?

- **Isolamento de Trabalho**: Permite trabalhar em novas funcionalidades ou correções sem interferir na branch principal.
- **Histórico Organizado**: Mantém o histórico de desenvolvimento claro e bem estruturado.
- **Colaboração Facilitada**: Desenvolvedores podem trabalhar em suas próprias branches e integrar (merge) as mudanças quando finalizadas.

## 📂 Conceitos Fundamentais sobre Branches

- **Branch Principal**: Geralmente chamada de `main` ou `master`, é a linha principal de desenvolvimento onde o código mais estável é mantido.
- **Branch de Funcionalidade**: Usada para desenvolver uma nova funcionalidade ou melhoria. Criada a partir da branch principal e, ao final, suas mudanças são integradas de volta.
- **Branch de Correção**: Focada em resolver problemas ou bugs específicos. Funciona de maneira semelhante à branch de funcionalidade.

## ⚙️ Trabalhando com Branches

1. **Criar uma nova branch**:
   ```bash
   git branch nome-da-branch

2. **Mudar para uma branch existente**:
   ```bash
   git checkout nome-da-branch
- Dica: Use `git checkout -b nome-da-branch` para criar e mudar para uma nova branch em um único comando.

3. **Listar todas as branches no repositório**:
   ```bash
   git branch

4. **Integrar mudanças de uma branch para outra**:
   ```bash
   git merge nome-da-branch

## ❌ Quando Deletar Branches?

Após concluir o trabalho em uma branch e integrá-la à principal, você deve deletá-la para manter o repositório organizado.

- **Deletar branch local**:
  ```bash
  git branch -d nome-da-branch

- **Forçar a deleção de uma branch local**:
  ```bash
  git branch -D nome-da-branch

- **Deletar branch remota**:
  ```bash
  git push origin --delete nome-da-branch

## ✏️ Renomear Branch

- **Renomear branch atual**:
  ```bash
  git branch -m novo-nome

- **Renomear branch específica**:
  ```bash
  git branch -m nome-antigo novo-nome

---

# 🌿 O que são Branches?

## 📋 Estratégias de Branching

### 1. GitFlow 🔄
Estratégia robusta para projetos com releases planejadas

#### Branches Principais
- `main` (ou `master`): Código em produção
- `develop`: Base para desenvolvimento

#### Branches de Suporte
- `feature/*`: Novas funcionalidades
- `release/*`: Preparação para release
- `hotfix/*`: Correções urgentes
- `bugfix/*`: Correções não urgentes

```powershell
# Iniciar feature
git checkout develop
git checkout -b feature/login

# Finalizar feature
git checkout develop
git merge feature/login

# Criar hotfix
git checkout main
git checkout -b hotfix/2.1.1
```

### 2. GitHub Flow 🌐
Estratégia simplificada para entrega contínua

#### Características
- Branch `main` sempre deployável
- Branches de feature diretas
- Pull Requests obrigatórios

```powershell
# Criar branch de feature
git checkout -b feature/novo-botao

# Atualizar com main
git pull origin main

# Publicar branch
git push -u origin feature/novo-botao
```

### 3. Trunk-Based Development 🚀
Estratégia para times com CI/CD maduro

#### Características
- Commits frequentes na `main`
- Branches curtas (1-2 dias)
- Feature flags para controle

```powershell
# Criar branch curta
git checkout -b feat/pequena-mudanca

# Manter atualizado
git pull --rebase origin main

# Merge rápido
git checkout main
git merge feat/pequena-mudanca
```

## 🛠️ Técnicas Avançadas

### 1. Feature Flags
```javascript
// Exemplo de feature flag
if (featureFlags.novoLogin) {
    // Nova implementação
} else {
    // Implementação antiga
}
```

### 2. Branch por Ambiente
```powershell
# Branches de ambiente
git checkout -b env/development
git checkout -b env/staging
git checkout -b env/production

# Promover mudanças
git checkout env/staging
git merge env/development
```

### 3. Release Branches
```powershell
# Criar branch de release
git checkout -b release/2.0.0 develop

# Correções na release
git checkout -b bugfix/login-fix release/2.0.0
git checkout release/2.0.0
git merge bugfix/login-fix

# Finalizar release
git checkout main
git merge release/2.0.0
git tag -a v2.0.0 -m "Versão 2.0.0"
```

## 📊 Gerenciamento de Branches

### 1. Nomenclatura
```plaintext
feature/   → Novas funcionalidades
  ├─ feature/user-auth
  ├─ feature/payment-gateway
  └─ feature/dark-theme

bugfix/    → Correções de bugs
  ├─ bugfix/login-error
  └─ bugfix/payment-validation

hotfix/    → Correções urgentes
  └─ hotfix/security-vulnerability

release/   → Preparação para release
  ├─ release/2.0.0
  └─ release/2.1.0
```

### 2. Organização
```powershell
# Listar branches por padrão
git branch --list "feature/*"
git branch --list "release/*"

# Limpar branches mescladas
git branch --merged main | Where-Object {$_ -notmatch 'main|develop'} | ForEach-Object { git branch -d $_.Trim() }
```

### 3. Proteções
```yaml
# Exemplo de regras no GitHub
branches:
  main:
    protection:
      required_pull_request_reviews:
        required_approving_review_count: 2
      required_status_checks:
        strict: true
```

## 🔄 Workflows Comuns

### 1. Feature Branch
```powershell
# Criar e publicar
git checkout -b feature/nova-funcionalidade
git push -u origin feature/nova-funcionalidade

# Manter atualizada
git fetch origin
git rebase origin/main

# Finalizar
git checkout main
git merge --no-ff feature/nova-funcionalidade
```

### 2. Release Branch
```powershell
# Criar release
git checkout -b release/2.0.0 develop

# Correções na release
git checkout -b bugfix/ultimo-ajuste release/2.0.0
git commit -am "fix: ajuste final"
git checkout release/2.0.0
git merge bugfix/ultimo-ajuste

# Finalizar
git checkout main
git merge release/2.0.0
git checkout develop
git merge release/2.0.0
```

### 3. Hotfix
```powershell
# Criar hotfix
git checkout -b hotfix/2.0.1 main

# Corrigir e commitar
git commit -am "fix: correção crítica de segurança"

# Finalizar
git checkout main
git merge hotfix/2.0.1
git tag -a v2.0.1 -m "Hotfix 2.0.1"
git checkout develop
git merge hotfix/2.0.1
```

## 🎯 Melhores Práticas

### 1. Regras de Branch
- Mantenha branches pequenas e focadas
- Atualize frequentemente com a branch principal
- Use nomes descritivos e padronizados
- Delete branches após merge

### 2. Segurança
- Proteja branches importantes
- Exija revisão de código
- Mantenha CI/CD em todas as branches
- Use assinatura de commits

### 3. Performance
- Evite branches muito longas
- Faça rebase frequentemente
- Limpe branches obsoletas
- Use shallow clones quando apropriado

## 📈 Monitoramento

### 1. Métricas
- Tempo de vida da branch
- Tamanho dos Pull Requests
- Taxa de sucesso de CI/CD
- Frequência de merges

### 2. Ferramentas
```powershell
# Análise de branches
git for-each-ref --sort=-committerdate refs/heads/ --format='%(committerdate:short) %(refname:short)'

# Estatísticas
git shortlog -sn --all

# Visualização
git log --graph --oneline --all
```

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>