# Git: Conceitos e Comandos

## 💻 Introdução ao Git

Git é um sistema de controle de versão distribuído que permite gerenciar e acompanhar alterações em projetos de software de maneira eficiente e colaborativa. Criado por Linus Torvalds em 2005, o Git é amplamente utilizado no desenvolvimento de software para facilitar a colaboração entre desenvolvedores e manter um histórico completo das alterações feitas no código.

## 📌 Por que usar Git?

- **Rastreamento de Alterações**: Permite acompanhar o histórico de mudanças no projeto.
- **Colaboração**: Facilita o trabalho em equipe, permitindo que vários desenvolvedores trabalhem em paralelo.
- **Segurança**: Armazena as alterações de forma segura e rastreável.
- **Controle de Versão**: Mantém diferentes versões do projeto, permitindo reversões rápidas a versões anteriores.

## 🔍 Conceitos Fundamentais do Git

- **Repositório** 📁: O projeto como um todo. O diretório raiz de onde serão monitoradas todas as alterações.
- **Commit** 💾: O ato de salvar uma ou mais alterações no código. Também pode se referir ao conjunto dessas alterações.
- **Working Tree** 🌳: O espaço de trabalho onde você faz modificações nos arquivos do projeto. Alterações locais são realizadas aqui antes de serem adicionadas à área de preparação.
- **Staging Area** 🧩: Uma área de preparação onde você seleciona as alterações que serão salvas no próximo commit.
- **Branches** 🌿: Ramificações que permitem trabalhar em paralelo no projeto sem afetar a ramificação principal.

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

## 📂 Comandos Essenciais do Terminal

- `pwd` 📜: Exibe o caminho completo do diretório atual.
- `ls` 📋: Lista o conteúdo do diretório atual.
- `mkdir` 🗂️: Cria um novo diretório vazio.
- `cd` 🔄: Navega entre diretórios.
- `ni` / `touch` 📝: Cria um arquivo vazio.
- `cp` 📄: Copia arquivos ou diretórios.
- `mv` 🚚: Move ou renomeia arquivos/diretórios.
- `rm` 🗑️: Remove arquivos ou diretórios.
- `code .` 💻: Abre o Visual Studio Code no diretório atual.
- `clear` ✨: Limpa a tela do terminal.
- `exit` ❌: Fecha o terminal ou finaliza uma sessão.

## ⚙️ Comandos Essenciais do Git

- `git init` 🛠️: Inicializa um repositório no diretório atual.
- `git status` 🔎: Exibe a situação atual da working tree (o que foi modificado e o que está preparado).
- `git add .` ➕: Adiciona arquivos modificados à área de preparação (staging area).
- `git rm --cached` 🗑️: Remove arquivos da área de preparação (desfaz o comando `add`).
- `git commit -m "mensagem do commit"` 💬: Salva definitivamente as alterações preparadas no histórico do repositório.
- `git log` 📜: Mostra o histórico de commits.
- `git diff` ⚡: Exibe as alterações entre diferentes commits ou entre a working tree e o repositório.
- `git restore` 🧹: Reverte as alterações em um arquivo, retornando ao estado do último commit.
- `git merge` 🔗: Combina mudanças de uma branch com a branch atual.
- `git pull` ⬇️: Atualiza a branch local com as alterações do repositório remoto.
- `git push` ⬆️: Envia as alterações da branch local para o repositório remoto.

## 📜 Padrões de Commits

De acordo com a [documentação do Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), commits semânticos são uma convenção simples para ser utilizada nas mensagens de commit. Essa convenção define um conjunto de regras para criar um histórico de commit explícito, facilitando a criação de ferramentas automatizadas e compreensão das alterações.

Esses commits ajudam você e sua equipe a entenderem de forma facilitada quais alterações foram realizadas no código. Essa identificação ocorre por meio de uma palavra que identifica se aquele commit realizado se trata de uma alteração de código, atualização de pacotes, documentação, alteração de visual, teste, entre outros.

## 📌 Tipo e Descrição
O commit semântico possui os elementos estruturais abaixo (tipos), que informam a intenção do seu commit ao utilizador(a) de seu código.

- `feat`- Commits do tipo feat indicam que seu trecho de código está incluindo um **novo recurso** (se relaciona com o MINOR do versionamento semântico).

- `fix` - Commits do tipo fix indicam que seu trecho de código commitado está **solucionando um problema** (bug fix), (se relaciona com o PATCH do versionamento semântico).

- `docs` - Commits do tipo docs indicam que houveram **mudanças na documentação**, como por exemplo no Readme do seu repositório. (Não inclui alterações em código).

- `test` - Commits do tipo test são utilizados quando são realizadas **alterações em testes**, seja criando, alterando ou excluindo testes unitários. (Não inclui alterações em código)

- `build` - Commits do tipo build são utilizados quando são realizadas modificações em **arquivos de build e dependências**.

- `perf` - Commits do tipo perf servem para identificar quaisquer alterações de código que estejam relacionadas a **performance**.

- `style` - Commits do tipo style indicam que houveram alterações referentes a **formatações de código**, semicolons, trailing spaces, lint... (Não inclui alterações em código).

- `refactor` - Commits do tipo refactor referem-se a mudanças devido a **refatorações que não alterem sua funcionalidade**, como por exemplo, uma alteração no formato como é processada determinada parte da tela, mas que manteve a mesma funcionalidade, ou melhorias de performance devido a um code review.

- `chore` - Commits do tipo chore indicam **atualizações de tarefas** de build, configurações de administrador, pacotes... como por exemplo adicionar um pacote no gitignore. (Não inclui alterações em código)

- `ci` - Commits do tipo ci indicam mudanças relacionadas a **integração contínua** (_continuous integration_).

- `raw` - Commits do tipo raw indicam mudanças relacionadas a arquivos de configurações, dados, features, parâmetros.

- `cleanup` - Commits do tipo cleanup são utilizados para remover código comentado, trechos desnecessários ou qualquer outra forma de limpeza do código-fonte, visando aprimorar sua legibilidade e manutenibilidade.

- `remove` - Commits do tipo remove indicam a exclusão de arquivos, diretórios ou funcionalidades obsoletas ou não utilizadas, reduzindo o tamanho e a complexidade do projeto e mantendo-o mais organizado.

## 🛠️ Boas Práticas e Dicas

### 📝 Nomeie Seus Commits com Cuidado
- Use mensagens claras e objetivas para descrever o que foi alterado e por quê.
- Alinhe-se aos padrões do time.

### 🔍 Revise Antes de Comitar
- Verifique mudanças com `git diff` para evitar commits incompletos ou incorretos.
- Use `git status` para confirmar o que será incluído no commit.

### 🔄 Faça Commits Pequenos e Frequentes
- Cada commit deve conter uma pequena funcionalidade ou correção.
- Isso facilita revisões, testes e reverte alterações problemáticas.

### 🎨 Use Emojis nos Commits
- Adicione um emoji no início da mensagem para representar visualmente o tipo de alteração (ex.: ✨, 🐛, 📚).
- Exemplo: `git commit -m ":sparkles: feat: Adiciona funcionalidade de login"`

## Padrões de emojis 💈

<table>
  <thead>
    <tr>
      <th>Tipo do commit</th>
      <th>Emoji</th>
      <th>Palavra-chave</th>
    </tr>
  </thead>
 <tbody>
    <tr>
      <td>Acessibilidade</td>
      <td>♿ <code>:wheelchair:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Adicionando um teste</td>
      <td>✅ <code>:white_check_mark:</code></td>
      <td><code>test</code></td>
    </tr>
    <tr>
      <td>Atualizando a versão de um submódulo</td>
      <td>⬆️ <code>:arrow_up:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Retrocedendo a versão de um submódulo</td>
      <td>⬇️ <code>:arrow_down:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Adicionando uma dependência</td>
      <td>➕ <code>:heavy_plus_sign:</code></td>
      <td><code>build</code></td>
    </tr>
    <tr>
      <td>Alterações de revisão de código</td>
      <td>👌 <code>:ok_hand:</code></td>
      <td><code>style</code></td>
    </tr>
    <tr>
      <td>Animações e transições</td>
      <td>💫 <code>:dizzy:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Bugfix</td>
      <td>🐛 <code>:bug:</code></td>
      <td><code>fix</code></td>
    </tr>
    <tr>
      <td>Comentários</td>
      <td>💡 <code>:bulb:</code></td>
      <td><code>docs</code></td>
    </tr>
    <tr>
      <td>Commit inicial</td>
      <td>🎉 <code>:tada:</code></td>
      <td><code>init</code></td>
    </tr>
    <tr>
      <td>Configuração</td>
      <td>🔧 <code>:wrench:</code></td>
      <td><code>chore</code></td>
    </tr>
    <tr>
      <td>Deploy</td>
      <td>🚀 <code>:rocket:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Documentação</td>
      <td>📚 <code>:books:</code></td>
      <td><code>docs</code></td>
    </tr>
    <tr>
      <td>Em progresso</td>
      <td>🚧 <code>:construction:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Estilização de interface</td>
      <td>💄 <code>:lipstick:</code></td>
      <td><code>feat</code></td>
    </tr>
    <tr>
      <td>Infraestrutura</td>
      <td>🧱 <code>:bricks:</code></td>
      <td><code>ci</code></td>
    </tr>
    <tr>
      <td>Lista de ideias (tasks)</td>
      <td>🔜 <code> :soon: </code></td>
      <td></td>
    </tr>
    <tr>
      <td>Mover/Renomear</td>
      <td>🚚 <code>:truck:</code></td>
      <td><code>chore</code></td>
    </tr>
    <tr>
      <td>Novo recurso</td>
      <td>✨ <code>:sparkles:</code></td>
      <td><code>feat</code></td>
    </tr>
    <tr>
      <td>Package.json em JS</td>
      <td>📦 <code>:package:</code></td>
      <td><code>build</code></td>
    </tr>
    <tr>
      <td>Performance</td>
      <td>⚡ <code>:zap:</code></td>
      <td><code>perf</code></td>
    </tr>
    <tr>
        <td>Refatoração</td>
        <td>♻️ <code>:recycle:</code></td>
        <td><code>refactor</code></td>
    </tr>
    <tr>
      <td>Limpeza de Código</td>
      <td>🧹 <code>:broom:</code></td>
      <td><code>cleanup</code></td>
    </tr>
    <tr>
      <td>Removendo um arquivo</td>
      <td>🗑️ <code>:wastebasket:</code></td>
      <td><code>remove</code></td>
    </tr>
    <tr>
      <td>Removendo uma dependência</td>
      <td>➖ <code>:heavy_minus_sign:</code></td>
      <td><code>build</code></td>
    </tr>
    <tr>
      <td>Responsividade</td>
      <td>📱 <code>:iphone:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Revertendo mudanças</td>
      <td>💥 <code>:boom:</code></td>
      <td><code>fix</code></td>
    </tr>
    <tr>
      <td>Segurança</td>
      <td>🔒️ <code>:lock:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>SEO</td>
      <td>🔍️ <code>:mag:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Tag de versão</td>
      <td>🔖 <code>:bookmark:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Teste de aprovação</td>
      <td>✔️ <code>:heavy_check_mark:</code></td>
      <td><code>test</code></td>
    </tr>
    <tr>
      <td>Testes</td>
      <td>🧪 <code>:test_tube:</code></td>
      <td><code>test</code></td>
    </tr>
    <tr>
      <td>Texto</td>
      <td>📝 <code>:pencil:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Tipagem</td>
      <td>🏷️ <code>:label:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Tratamento de erros</td>
      <td>🥅 <code>:goal_net:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Dados</td>
      <td>🗃️ <code>:card_file_box:</code></td>
      <td><code>raw</code></td>
    </tr>
  </tbody>
</table>

# 🖥️ Guia Avançado de Branches e Colaboração no Git

## 🌿 O que são Branches?

Branches são ramificações que permitem trabalhar em diferentes linhas de desenvolvimento dentro de um mesmo repositório.

### 🚀 Por que usar branches?

- **Isolamento de Trabalho**: Permite trabalhar em novas funcionalidades ou correções sem interferir na branch principal.
- **Histórico Organizado**: Mantém o histórico de desenvolvimento claro e bem estruturado.
- **Colaboração Facilitada**: Desenvolvedores podem trabalhar em suas próprias branches e integrar (merge) as mudanças quando finalizadas.

### 📂 Conceitos Fundamentais sobre Branches

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

### ❌ Quando Deletar Branches?

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

### ✏️ Renomear Branch

- **Renomear branch atual**:
  ```bash
  git branch -m novo-nome

- **Renomear branch específica**:
  ```bash
  git branch -m nome-antigo novo-nome

## 🔀 O que são Conflitos de Merge?

Conflitos de merge ocorrem quando o Git não consegue combinar automaticamente mudanças feitas em duas branches diferentes.

### ⚠️ Tipos de Conflitos

- **Alterações Conflitantes**: Mudanças incompatíveis feitas na mesma linha de um arquivo.
- **Exclusões Conflitantes**: Um desenvolvedor exclui uma linha ou arquivo que outro modificou.

### 🛠️ Como Resolver Conflitos de Merge?

1. **Identificar os arquivos em conflito**:
   - Use `git status` para listar os arquivos marcados como "both modified".

2. **Abrir os arquivos conflitantes**:
   - Arquivos em conflito terão marcações especiais, como `<<<<<<<`, `=======`, e `>>>>>>>`.

3. **Resolver os conflitos**:
   - Edite os arquivos para combinar as mudanças de forma adequada e remova as marcações de conflito.

4. **Marcar os conflitos como resolvidos**:
   ```bash
   git add nome-do-arquivo

5. **Finalizar o merge**:
   ```bash
   git commit

## 🌐 Fluxo de Trabalho Colaborativo

1. **Clonar o repositório** e configurar o ambiente inicial.
2. Criar uma **nova branch** para trabalhar em uma tarefa específica:
   ```bash
   git checkout -b nome-da-branch

3. Fazer alterações no projeto na nova branch.
4. Adicionar (`git add`) e commitar (`git commit`) as mudanças.
5. Subir a branch para o repositório remoto e abrir um **Pull Request** (PR).
6. O líder do projeto aprova o PR e integra as alterações na branch principal (`git merge`).
7. Deletar branches antigas e continuar o ciclo de desenvolvimento.

## 📜 Arquivos Especiais no Git

- **`.gitignore`** 🚫: Define arquivos e pastas que o Git deve ignorar, como arquivos temporários ou de configuração local.
- **`.gitkeep`** 📂: Um arquivo vazio usado para manter diretórios sem conteúdo no repositório (o Git não rastreia diretórios vazios por padrão).

# Glossário 📖

- `fork` - Cópia de um repositório para a sua própria conta no GitHub. Isso cria um novo repositório em sua conta que é independente do original, permitindo que você faça alterações sem afetar o repositório original.

- `issues` - Ferramenta usada para gerenciar tarefas, pedidos de novos recursos e correções de bugs em projetos de código aberto. As issues devem ser descritas e listadas, permitindo aos colaboradores discutirem e rastrearem o progresso das mesmas.

- `pull request` - Mecanismo usado para submeter alterações propostas ao repositório original. Um pull request é uma solicitação para que os mantenedores do projeto revisem e potencialmente incorporem as alterações. O pull request passará por um processo de avaliação e pode ser aceito ou rejeitado.

- `gist` - Ferramenta que permite o compartilhamento de trechos de código sem a necessidade de criar um repositório completo. Gists podem ser compartilhados publicamente ou de forma privada.

## 📚 Recursos Adicionais

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2) - Livro gratuito sobre Git
- [Guia Interativo do Git](https://rogerdudler.github.io/git-guide/index.pt_BR.html) - Prática de comandos Git com visualização interativa
