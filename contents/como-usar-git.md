<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🔧 Como usar o Git?

## 🚀 Instalação e Configuração

### 1. Instalação por Sistema Operacional

#### Windows
- Download do instalador em [git-scm.com](https://git-scm.com/download/win)
- Durante a instalação:
  - Escolha editor padrão
  - Configure PATH environment
  - Selecione SSL library
  - Configure line ending conversions

#### macOS
```bash
# Via Homebrew
brew install git

# Via instalador
https://git-scm.com/download/mac
```

#### Linux
```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install git

# Fedora
sudo dnf install git
```

### 2. Configuração Inicial

#### Identidade
```powershell
# Configuração global
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"

# Configuração específica para um repositório
git config user.name "Nome Diferente"
git config user.email "outro.email@exemplo.com"
```

#### Editor
```powershell
# VS Code como editor padrão
git config --global core.editor "code --wait"

# Notepad++ como editor
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
```

#### Aliases Úteis
```powershell
# Atalhos para comandos comuns
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.st status
git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

## 🏗️ Iniciando com Git

### 1. Novo Repositório

#### Atalho Rápido - repo.new
Uma forma super rápida de criar um novo repositório no GitHub é usar o atalho:
```
repo.new
```
Digite isso na barra de endereços do seu navegador e será redirecionado diretamente para a página de criação de um novo repositório no GitHub.

#### Criar do Zero
```powershell
# Inicializar repositório
mkdir meu-projeto
cd meu-projeto
git init

# Criar arquivo inicial
New-Item README.md
Add-Content README.md "# Meu Projeto`n`nDescrição do projeto..."

# Primeiro commit
git add README.md
git commit -m "chore: commit inicial"
```

#### Clonar Existente
```powershell
# HTTPS
git clone https://github.com/usuario/repositorio.git

# SSH
git clone git@github.com:usuario/repositorio.git

# Branch específica
git clone -b develop https://github.com/usuario/repositorio.git
```

### 2. Configuração do Repositório

#### Git Ignore
```plaintext
# .gitignore
# Dependências
node_modules/
vendor/

# Ambiente
.env
.env.local

# IDE
.vscode/
.idea/

# Build
/dist
/build

# Logs
*.log
npm-debug.log*
```

#### Atributos Git
```plaintext
# .gitattributes
# Auto detect text files
* text=auto

# Força LF para scripts
*.sh text eol=lf

# Arquivos binários
*.png binary
*.jpg binary
```

## 🔄 Fluxo de Trabalho Básico

### 1. Verificando Status
```powershell
# Status detalhado
git status

# Status resumido
git status -s
```

### 2. Staging Changes
```powershell
# Adicionar arquivo específico
git add arquivo.txt

# Adicionar todos os arquivos
git add .

# Adicionar interativamente
git add -p
```

### 3. Commitando
```powershell
# Commit básico
git commit -m "feat: adiciona funcionalidade de login"

# Commit com descrição detalhada
git commit -m "feat: implementa autenticação OAuth2

- Adiciona endpoints de autorização
- Integra com provedor Google
- Implementa refresh token
- Adiciona testes de integração"
```

## 🔧 Ferramentas Úteis

### 1. GUI Clients
- GitHub Desktop
- GitKraken
- Sourcetree
- VS Code Git Integration

### 2. Git Credential Manager
```powershell
# Windows (já incluído no Git for Windows)
git config --global credential.helper manager-core

# macOS
git config --global credential.helper osxkeychain
```

### 3. Git LFS (Large File Storage)
```powershell
# Instalar Git LFS
git lfs install

# Rastrear arquivos grandes
git lfs track "*.psd"
git lfs track "*.zip"
```

## 🔒 Segurança

### 1. SSH Keys
```powershell
# Gerar nova chave SSH
ssh-keygen -t ed25519 -C "seu.email@exemplo.com"

# Iniciar ssh-agent
Start-Service ssh-agent

# Adicionar chave ao ssh-agent
ssh-add ~\.ssh\id_ed25519
```

### 2. GPG Signing
```powershell
# Gerar chave GPG
gpg --full-generate-key

# Configurar Git para usar GPG
git config --global user.signingkey [SEU-ID-GPG]
git config --global commit.gpgsign true
```

## 🔍 Diagnóstico

### 1. Verificação do Sistema
```powershell
# Verificar versão
git --version

# Verificar configurações
git config --list

# Verificar remotes
git remote -v
```

### 2. Manutenção
```powershell
# Verificar integridade
git fsck

# Limpar arquivos não rastreados
git clean -n  # dry run
git clean -fd  # forçar remoção

# Otimizar repositório
git gc
git prune
```

## 📚 Recursos Adicionais

### 1. Documentação
- [Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/pt-br/v2)
- [Git Reference](https://git-scm.com/docs)

### 2. Ferramentas Online
- [GitHub](https://github.com)
- [GitLab](https://gitlab.com)
- [Bitbucket](https://bitbucket.org)

### 3. Aprendizado
- [GitHub Learning Lab](https://lab.github.com)
- [Git Branching](https://learngitbranching.js.org)
- [Git Immersion](http://gitimmersion.com)

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>