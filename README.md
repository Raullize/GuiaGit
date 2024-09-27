
# Git: Conceitos e Comandos

# 💻 Git

## Introdução ao Git

Git é um sistema de controle de versão distribuído que permite gerenciar e acompanhar alterações em projetos de software de maneira eficiente e colaborativa. Criado por Linus Torvalds em 2005, o Git é amplamente utilizado em desenvolvimento de software para facilitar a colaboração entre desenvolvedores e manter um histórico completo das alterações feitas no código.

## 📌 Por que usar Git?

- **Rastreamento de Alterações**: Permite acompanhar o histórico de mudanças no projeto.
- **Colaboração**: Facilita o trabalho em equipe, permitindo que vários desenvolvedores trabalhem em paralelo.
- **Segurança**: Armazena as alterações de forma segura e rastreável.
- **Controle de Versão**: Mantém diferentes versões do projeto, permitindo reversões rápidas a versões anteriores.

## 🔧 Como usar o Git?

### 1. Instalação

- [Download do Git](https://git-scm.com/downloads) para seu sistema operacional.
- Verifique a instalação com o comando:

```bash
git --version
```

### 2. Configuração Inicial

Configure seu nome de usuário e e-mail para identificar suas alterações:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

### 3. Criando um Repositório

- **Inicializar um repositório local:**

```bash
git init
```

- **Clonar um repositório existente:**

```bash
git clone <url-do-repositorio>
```

## 📜 Principais Comandos do Git

### 🔄 Comandos de Controle de Versão

- `git status`: Verifica o estado atual do repositório.
- `git add <arquivo>`: Adiciona um arquivo ao stage.
- `git add .`: Adiciona todas as alterações ao stage.
- `git commit -m "mensagem"`: Cria um commit com uma mensagem descritiva.
- `git log`: Visualiza o histórico de commits.

### 🔀 Comandos de Ramificação e Merge

- `git branch`: Lista todas as branches no repositório.
- `git branch <nome-da-branch>`: Cria uma nova branch.
- `git checkout <nome-da-branch>`: Muda para a branch especificada.
- `git merge <nome-da-branch>`: Mescla a branch especificada na branch atual.

### 🌐 Comandos de Repositório Remoto

- `git remote add origin <url>`: Adiciona um repositório remoto.
- `git push origin <nome-da-branch>`: Envia os commits da branch especificada para o repositório remoto.
- `git pull`: Atualiza a branch local com as mudanças do repositório remoto.

### 🛠️ Comandos de Manutenção e Correção

- `git reset --hard <hash-do-commit>`: Retorna a uma versão específica do projeto.
- `git stash`: Salva temporariamente as alterações pendentes.
- `git stash pop`: Aplica as alterações salvas anteriormente.

## 🚀 Fluxo Básico de Trabalho com Git

1. **Clonar o Repositório**

```bash
git clone <url-do-repositorio>
```

1. **Criar uma Branch para a Nova Tarefa**

```bash
git branch nome-da-branch
git checkout nome-da-branch
```

1. **Adicionar e Comitar Alterações**

```bash
git add .
git commit -m "Descrição das mudanças"
```

1. **Atualizar Branch Principal**

```bash
git checkout main
git pull origin main
```

1. **Mesclar a Nova Branch na Principal**

```bash
git merge nome-da-branch
```

1. **Enviar Alterações para o Repositório Remoto**

```bash
git push origin main
```

## 📚 Recursos Adicionais

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2) - Livro gratuito sobre Git
- [Guia Interativo do Git](https://rogerdudler.github.io/git-guide/index.pt_BR.html) - Prática de comandos Git com visualização interativa
