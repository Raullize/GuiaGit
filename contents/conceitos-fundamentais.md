<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🔍 Conceitos Fundamentais do Git

## Estrutura Básica

### 📁 Objetos Git
Git armazena todas as informações em quatro tipos de objetos:

- **Blob** 📄: Armazena o conteúdo de arquivos
- **Tree** 🌳: Representa diretórios e seus conteúdos
- **Commit** 💾: Representa um snapshot do projeto
- **Tag** 🏷️: Aponta para um commit específico (geralmente usado para versões)

### 🔄 Estados dos Arquivos
Arquivos em um repositório Git passam por três estados principais:

1. **Modified** ✏️: Arquivo foi alterado mas não commitado
2. **Staged** 🎯: Arquivo marcado para ser incluído no próximo commit
3. **Committed** ✅: Arquivo salvo com segurança no repositório

## 🏗️ Áreas de Trabalho

### Working Tree (Working Directory) 🌳
- É onde você faz modificações nos arquivos
- Representa os arquivos atuais no seu sistema
- Exemplo: Quando você edita um arquivo no VS Code, está trabalhando aqui

### Staging Area (Index) 🧩
- Área intermediária onde você prepara as mudanças para um commit
- Permite selecionar quais alterações serão incluídas
- Comando: `git add` move arquivos para esta área

### Repository (Git Directory) 📂
- Onde o Git armazena os metadados e objetos do projeto
- Localizado na pasta `.git` do seu projeto
- Contém todo o histórico e configurações

## 🔄 Fluxo Básico de Trabalho

1. **Modificar** arquivos na Working Tree
   ```powershell
   # Edite arquivos no seu editor
   code arquivo.txt
   ```

2. **Preparar** alterações na Staging Area
   ```powershell
   # Adiciona arquivos específicos
   git add arquivo.txt
   
   # Adiciona todos os arquivos modificados
   git add .
   ```

3. **Commitar** para o repositório
   ```powershell
   git commit -m "feat: adiciona nova funcionalidade"
   ```

## 🌐 Repositórios

### Local Repository
- Repositório na sua máquina
- Contém todo o histórico do projeto
- Permite trabalhar offline

### Remote Repository
- Versão do repositório hospedada em um servidor (ex: GitHub)
- Permite colaboração entre equipes
- Serve como backup do projeto

## 🔗 Referências Git

### HEAD
- Ponteiro especial que indica o commit atual
- Geralmente aponta para o último commit da branch atual
- Pode ser movido com comandos como `checkout`

### Branch
- Linha independente de desenvolvimento
- Aponta para uma série de commits
- Principal: `main` ou `master`

### Tag
- Marco específico no histórico
- Geralmente usado para versões
- Exemplo: `v1.0.0`, `v2.1.3`

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>