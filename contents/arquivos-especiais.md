<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📜 Arquivos Especiais no Git

## Arquivos de Configuração

- **`.gitignore`** 🚫: Define arquivos e pastas que o Git deve ignorar. Ideal para arquivos temporários, logs, arquivos de ambiente e dependências que não devem ser rastreadas.

   ```bash
   # Exemplo de .gitignore
   node_modules/      # Ignora a pasta node_modules
   *.log              # Ignora todos os arquivos de log
   .env               # Ignora arquivo de variáveis de ambiente
   build/             # Ignora diretório de build
   ```

- **`.gitattributes`** 🧩: Define atributos para caminhos específicos. Útil para configurar como o Git trata diferentes tipos de arquivo.

   ```bash
   # Exemplo de .gitattributes
   *.txt text         # Trata arquivos .txt como texto
   *.jpg binary       # Trata arquivos .jpg como binários
   *.sh text eol=lf   # Garante que scripts shell usem LF (Linux)
   ```

- **`.gitkeep`** 📂: Um arquivo vazio (sem convenção oficial) usado para manter diretórios vazios no repositório, já que o Git não rastreia diretórios vazios.

- **`.gitconfig`** ⚙️: Arquivo de configuração global do Git (não específico do repositório). Configura seu nome, email, aliases e outras preferências.

## Arquivos Especiais de Projeto

- **`.github/`** 👥: Diretório com arquivos especiais para configuração do GitHub:
  - **`ISSUE_TEMPLATE/`**: Modelos para novos issues
  - **`PULL_REQUEST_TEMPLATE.md`**: Modelo para Pull Requests
  - **`workflows/`**: Arquivos de configuração para GitHub Actions

- **`.git/`** 🗄️: Diretório oculto criado pelo Git que contém todo o banco de dados local e configurações do repositório. **Nunca edite manualmente!**

## Arquivos de Documentação

- **`README.md`** 📖: Primeira documentação que as pessoas veem ao acessar seu repositório. Deve explicar o projeto, como instalar e utilizar.

- **`CONTRIBUTING.md`** 🤝: Instruções para contribuidores do projeto, explicando como participar e enviar contribuições.

- **`CHANGELOG.md`** 📝: Documento que registra todas as mudanças significativas feitas no projeto a cada versão.

- **`LICENSE`** ⚖️: Arquivo que define como outras pessoas podem usar, modificar e distribuir seu código.

## Hooks do Git

- **`.git/hooks/`** 🪝: Diretório com scripts que o Git executa automaticamente em eventos específicos:
  - **`pre-commit`**: Executa antes de um commit ser criado
  - **`post-commit`**: Executa depois que um commit é criado
  - **`pre-push`**: Executa antes de enviar commits para o repositório remoto

## Dicas de Uso

- Para criar um `.gitignore` eficiente, use geradores como [gitignore.io](https://www.toptal.com/developers/gitignore)
- Para hooks personalizados, considere usar ferramentas como Husky para Node.js
- Padronize seus arquivos `.gitignore` e `.gitattributes` entre projetos similares para manter consistência

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>