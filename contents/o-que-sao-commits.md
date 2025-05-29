<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📜 O que são Commits?

## 🎯 Conceito Base

Um commit é como uma fotografia do seu código em um momento específico. Cada commit registra:
- Quais arquivos foram alterados
- O que foi modificado em cada arquivo
- Quem fez as alterações
- Quando as alterações foram feitas
- Por que as alterações foram feitas (mensagem de commit)

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

## 🔄 Ciclo de Vida

### 1. Modificação
```powershell
# Criar/editar arquivos
code src/auth.js
```

### 2. Staging
```powershell
# Adicionar arquivo específico
git add src/auth.js

# Adicionar parte de um arquivo
git add -p src/auth.js

# Adicionar todos os arquivos
git add .
```

### 3. Commit
```powershell
# Commit básico
git commit -m "feat: adiciona autenticação"

# Commit com corpo
git commit -m "feat: implementa login com Google

- Adiciona SDK do Google
- Configura rotas OAuth
- Implementa callback handler
- Atualiza documentação"
```

## 📋 Tipos de Commit

### 1. Feature Commit ✨
```powershell
git commit -m "feat: adiciona sistema de notificações

- Implementa websockets
- Adiciona queue de mensagens
- Cria interface de notificação"
```

### 2. Bug Fix 🐛
```powershell
git commit -m "fix: corrige memory leak no WebSocket

Issue: #234
- Fecha conexões não utilizadas
- Implementa timeout
- Adiciona logs de debug"
```

### 3. Documentation 📚
```powershell
git commit -m "docs: atualiza API reference

- Adiciona novos endpoints
- Atualiza exemplos
- Corrige typos"
```

### 4. Refactor ♻️
```powershell
git commit -m "refactor: simplifica lógica de autenticação

- Extrai validações para middleware
- Remove código duplicado
- Melhora nomenclatura"
```

## 🛠️ Boas Práticas

### 1. Commits Atômicos
✅ **Bom**:
```powershell
git commit -m "feat: adiciona validação de email"
git commit -m "style: ajusta layout do formulário"
git commit -m "test: adiciona testes para validação"
```

❌ **Ruim**:
```powershell
git commit -m "implementa cadastro de usuário, arruma css e adiciona testes"
```

### 2. Mensagens Claras
✅ **Bom**:
```powershell
git commit -m "fix: corrige cálculo de juros compostos

- Ajusta fórmula matemática
- Corrige arredondamento
- Adiciona validação de input"
```

❌ **Ruim**:
```powershell
git commit -m "arruma bug"
```

### 3. Referências
✅ **Bom**:
```powershell
git commit -m "fix: resolve problema de auth

Closes #123
Breaking change: nova estrutura de token
See: #120, #121
Co-authored-by: @colega"
```

## 🔍 Investigação

### 1. Ver Histórico
```powershell
# Histórico detalhado
git log --patch

# Histórico resumido
git log --oneline

# Histórico com graph
git log --graph --oneline --all
```

### 2. Buscar Commits
```powershell
# Por autor
git log --author="Nome"

# Por mensagem
git log --grep="feat"

# Por conteúdo
git log -S "função específica"
```

### 3. Comparar Commits
```powershell
# Entre commits
git diff abc123..def456

# Com estado atual
git diff HEAD~3

# Entre branches
git diff main..feature
```

## 🔄 Manipulação

### 1. Editar Último Commit
```powershell
# Alterar mensagem
git commit --amend -m "nova mensagem"

# Adicionar mudanças
git add arquivo.js
git commit --amend --no-edit
```

### 2. Reverter Commits
```powershell
# Reverter commit específico
git revert abc123

# Reverter último commit
git revert HEAD

# Reverter merge commit
git revert -m 1 merge-commit-hash
```

### 3. Reescrever Histórico
```powershell
# Interativo últimos 3 commits
git rebase -i HEAD~3

# Squash commits
git reset --soft HEAD~3
git commit -m "feat: implementa feature completa"
```

## ⚠️ Cuidados

### 1. Commits Públicos
- Não reescreva histórico público
- Use `revert` em vez de `reset`
- Documente breaking changes

### 2. Segurança
- Não commite credenciais
- Use `.gitignore`
- Assine commits importantes

### 3. Performance
- Mantenha commits pequenos
- Evite arquivos binários grandes
- Use Git LFS quando necessário

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>