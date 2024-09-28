# Git: Conceitos e Comandos

## 💻 Introdução ao Git

Git é um sistema de controle de versão distribuído que permite gerenciar e acompanhar alterações em projetos de software de maneira eficiente e colaborativa. Criado por Linus Torvalds em 2005, o Git é amplamente utilizado no desenvolvimento de software para facilitar a colaboração entre desenvolvedores e manter um histórico completo das alterações feitas no código.

## 📌 Por que usar Git?

- **Rastreamento de Alterações**: Permite acompanhar o histórico de mudanças no projeto.
- **Colaboração**: Facilita o trabalho em equipe, permitindo que vários desenvolvedores trabalhem em paralelo.
- **Segurança**: Armazena as alterações de forma segura e rastreável.
- **Controle de Versão**: Mantém diferentes versões do projeto, permitindo reversões rápidas a versões anteriores.

## 🔧 Como usar o Git?

1. **Instalação**
    - Faça o [download do Git](https://git-scm.com/download) para o seu sistema operacional.
    - Verifique a instalação com o comando:

    ```bash
    git --version
    ```

2. **Configuração Inicial**
    - Configure seu nome de usuário e e-mail para identificar suas alterações:

    ```bash
    git config --global user.name "Seu Nome"
    git config --global user.email "seu.email@exemplo.com"
    ```

3. **Criando um Repositório**
    - Inicializar um repositório local:

    ```bash
    git init
    ```

    - Clonar um repositório existente:

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

2. **Criar uma Branch para a Nova Tarefa**

    ```bash
    git branch nome-da-branch
    git checkout nome-da-branch
    ```

3. **Adicionar e Comitar Alterações**

    ```bash
    git add .
    git commit -m "Descrição das mudanças"
    ```

4. **Atualizar Branch Principal**

    ```bash
    git checkout main
    git pull origin main
    ```

5. **Mesclar a Nova Branch na Principal**

    ```bash
    git merge nome-da-branch
    ```

6. **Enviar Alterações para o Repositório Remoto**

    ```bash
    git push origin main
    ```

## 📜 Padrões de Commits

De acordo com a [documentação do Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), commits semânticos são uma convenção simples para ser utilizada nas mensagens de commit. Essa convenção define um conjunto de regras para criar um histórico de commit explícito, facilitando a criação de ferramentas automatizadas e compreensão das alterações.

Esses commits ajudam você e sua equipe a entenderem de forma facilitada quais alterações foram realizadas no código. Essa identificação ocorre por meio de uma palavra que identifica se aquele commit realizado se trata de uma alteração de código, atualização de pacotes, documentação, alteração de visual, teste, entre outros.

## 📌 Tipo e Descrição

- **feat**: Inclusão de um novo recurso (relaciona-se ao MINOR do versionamento semântico).
- **fix**: Correção de um problema (bug fix, relacionado ao PATCH do versionamento semântico).
- **docs**: Alterações na documentação (sem mudanças no código).
- **test**: Alterações em testes (criação, alteração ou exclusão de testes unitários).
- **build**: Modificações em arquivos de build e dependências.
- **perf**: Alterações de código relacionadas à performance.
- **style**: Alterações referentes à formatação de código, semicolons, lint... (sem mudanças no código).
- **refactor**: Mudanças de refatoração sem alteração de funcionalidade.
- **chore**: Atualizações de tarefas de build, configurações, pacotes (sem mudanças no código).
- **ci**: Alterações relacionadas à integração contínua.
- **raw**: Mudanças em arquivos de configurações, dados, features, parâmetros.
- **cleanup**: Remoção de código comentado ou desnecessário para melhorar legibilidade e manutenibilidade.
- **remove**: Exclusão de arquivos, diretórios ou funcionalidades obsoletas ou não utilizadas.

## 📚 Recursos Adicionais

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2) - Livro gratuito sobre Git
- [Guia Interativo do Git](https://rogerdudler.github.io/git-guide/index.pt_BR.html) - Prática de comandos Git com visualização interativa
