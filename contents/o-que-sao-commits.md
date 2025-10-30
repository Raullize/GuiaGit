<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📜 O que são Commits?

## 🎯 Conceito Base

Um **commit** é como uma fotografia do seu código em um momento específico no tempo. É a unidade fundamental de versionamento no Git, representando um conjunto de alterações que foram aplicadas ao projeto.

### 🔍 O que um Commit Registra:
- **Quais arquivos** foram alterados, adicionados ou removidos
- **O conteúdo exato** das modificações (diff)
- **Quem** fez as alterações (autor e committer)
- **Quando** as alterações foram feitas (timestamp)
- **Por que** as alterações foram feitas (mensagem de commit)
- **Referência** ao commit anterior (parent)

### 🌟 Características Importantes:
- **Imutável**: Uma vez criado, o conteúdo não pode ser alterado
- **Único**: Cada commit tem um hash SHA-1 único
- **Rastreável**: Forma uma cadeia histórica do projeto
- **Atômico**: Representa uma unidade lógica de mudança

## 📝 Anatomia de um Commit

### 1. Identificação
```plaintext
commit 8f937c683929b08379097828c8a04350b9b8e937
Author: Seu Nome <seu.email@exemplo.com>
Date:   Qui Mai 29 14:30:00 2025 -0300
```

### 2. Mensagem
```plaintext
feat: adiciona autenticação com Google

- Implementa OAuth2 flow
- Adiciona middleware de autenticação
- Cria rotas de callback
- Atualiza documentação

Closes #123
```

### 3. Alterações (diff)
```diff
+ import GoogleAuth from './auth/google';
- import LocalAuth from './auth/local';

  class AuthService {
+   async googleLogin() {
+     return GoogleAuth.authenticate();
+   }
-   async localLogin() {
-     return LocalAuth.authenticate();
-   }
  }
```

## 🔄 Ciclo de Vida Básico

### 1. 📝 Modificação (Working Directory)
```powershell
# Criar ou editar arquivos
code src/auth.js
echo "console.log('Hello');" > app.js
```

### 2. 📋 Preparação (Staging Area)
```powershell
# Adicionar arquivo específico
git add src/auth.js

# Adicionar parte de um arquivo (interativo)
git add -p src/auth.js

# Adicionar todos os arquivos modificados
git add .

# Verificar o que está preparado
git status
```

### 3. 📸 Confirmação (Repository)
```powershell
# Commit básico
git commit -m "adiciona função de autenticação"

# Commit com editor (para mensagens longas)
git commit

# Commit pulando o staging (cuidado!)
git commit -am "atualiza todos os arquivos modificados"
```

## 🔍 Comandos de Investigação

### 📚 Visualizar Histórico
```powershell
# Histórico completo
git log

# Histórico resumido (uma linha por commit)
git log --oneline

# Histórico com gráfico de branches
git log --graph --oneline --all

# Últimos 5 commits
git log -5

# Histórico com diferenças
git log -p
```

### 🔎 Buscar Commits
```powershell
# Por autor
git log --author="João Silva"

# Por mensagem (regex)
git log --grep="fix"

# Por conteúdo alterado
git log -S "função específica"

# Por arquivo
git log -- src/auth.js

# Entre datas
git log --since="2024-01-01" --until="2024-12-31"
```

### 📊 Comparar Alterações
```powershell
# Ver alterações não commitadas
git diff

# Ver alterações no staging
git diff --staged

# Entre commits específicos
git diff abc123..def456

# Entre commit e estado atual
git diff HEAD~3

# Entre branches
git diff main..feature-branch
```

## 🛠️ Manipulação Básica

### ✏️ Editar Último Commit
```powershell
# Alterar apenas a mensagem
git commit --amend -m "nova mensagem corrigida"

# Adicionar mudanças esquecidas
git add arquivo-esquecido.js
git commit --amend --no-edit

# Alterar autor do último commit
git commit --amend --author="Nome Correto <email@correto.com>"
```

### ↩️ Reverter Alterações
```powershell
# Reverter commit específico (cria novo commit)
git revert abc123

# Reverter último commit
git revert HEAD

# Reverter merge commit
git revert -m 1 merge-commit-hash

# Reverter sem criar commit automaticamente
git revert --no-commit abc123
```

### 🗂️ Informações do Commit
```powershell
# Detalhes de um commit específico
git show abc123

# Apenas a mensagem
git show --format="%s" abc123

# Arquivos alterados
git show --name-only abc123

# Estatísticas das alterações
git show --stat abc123
```

## 🎯 Navegação Rápida

### 📍 Referências Úteis
```powershell
# Último commit
HEAD

# Penúltimo commit
HEAD~1 ou HEAD^

# Três commits atrás
HEAD~3

# Commit específico por hash
abc123 (primeiros caracteres do hash)

# Branch específica
main, develop, feature-branch
```

## 🔗 Recursos e Próximos Passos

### 📚 **Documentação Complementar**
- **[🎯 Commits Semânticos](commits-semanticos.md)** - Especificação técnica detalhada para padronização
- **[🧑‍💻 Mantendo um Padrão](mantendo-um-padrão-de-commits.md)** - Práticas de equipe e governança
- **[🎨 Commits com Emojis](emojis.md)** - Alternativas visuais para identificação rápida

### 🛠️ **Ferramentas Recomendadas**

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>