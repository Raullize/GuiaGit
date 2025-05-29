<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>


# 🔀 O que são Conflitos de Merge?

Conflitos de merge ocorrem quando o Git não consegue resolver automaticamente diferenças entre branches. Isso geralmente acontece quando duas branches modificam a mesma parte de um arquivo ou quando um arquivo foi modificado em uma branch e deletado em outra.

## ⚠️ Tipos de Conflitos

### 1. Conflitos de Conteúdo 📝
Quando a mesma linha ou seção é modificada em branches diferentes:

```plaintext
<<<<<<< HEAD (Branch Atual)
console.log("Olá Mundo!");
=======
console.log("Hello World!");
>>>>>>> feature-branch
```

### 2. Conflitos de Estrutura 🏗️
- Arquivo renomeado em uma branch e editado em outra
- Arquivo deletado em uma branch e modificado em outra
- Arquivo movido para outro diretório

### 3. Conflitos de Deleção ❌
Ocorre quando um arquivo é modificado em uma branch e deletado em outra.

```plaintext
error: The following untracked working tree files would be overwritten by merge:
    src/utils/helper.js
Please move or remove them before you merge.
```

## 🛠️ Como Resolver Conflitos

### Método Manual

1. **Identificar arquivos conflitantes**:
   ```powershell
   git status
   ```

2. **Abrir o arquivo e localizar marcadores de conflito**:
   ```plaintext
   <<<<<<< HEAD
   Sua versão
   =======
   Versão da outra branch
   >>>>>>> branch-name
   ```

3. **Editar o arquivo**:
   - Remover marcadores de conflito
   - Manter o código desejado
   - Salvar as alterações

4. **Marcar como resolvido**:
   ```powershell
   git add arquivo-com-conflito.txt
   ```

5. **Completar o merge**:
   ```powershell
   git commit -m "fix: resolve conflitos de merge"
   ```

### Usando Ferramentas Visuais 🖥️

1. **VS Code Git**:
   - Mostra botões "Accept Current Change" e "Accept Incoming Change"
   - Interface visual para comparar alterações

2. **Git Mergetool**:
   ```powershell
   git mergetool
   ```

## 🚫 Prevenindo Conflitos

### 1. Comunicação Clara
- Coordene com a equipe quem está trabalhando em quais arquivos
- Use issues e pull requests para documentar mudanças

### 2. Branches Pequenas e Focadas
- Mantenha branches curtas e específicas
- Faça merge frequentemente com a branch principal

### 3. Atualize sua Branch
```powershell
# Atualizar branch com main
git checkout sua-branch
git pull origin main
```

### 4. Rebase vs Merge
```powershell
# Usando rebase (mantém histórico linear)
git checkout sua-branch
git rebase main

# Usando merge (mantém histórico completo)
git checkout sua-branch
git merge main
```

## 🆘 Situações Comuns e Soluções

### 1. Conflito em Arquivo Binário
- Use `git checkout --ours arquivo.bin` para manter sua versão
- Use `git checkout --theirs arquivo.bin` para usar a versão deles

### 2. Muitos Conflitos
```powershell
# Abortar merge e recomeçar
git merge --abort

# Tentar estratégia diferente
git merge -X ours branch-name  # Preferir nossas mudanças
git merge -X theirs branch-name  # Preferir mudanças deles
```

### 3. Conflitos em Arquivos de Configuração
- Considere usar `.gitattributes` para definir estratégias de merge
- Mantenha arquivos de exemplo versionados (ex: `config.example.json`)

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>