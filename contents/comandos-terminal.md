<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 📂 Comandos Essenciais do Terminal

O terminal é uma ferramenta fundamental para desenvolvedores, permitindo controle direto sobre o sistema operacional. Este guia apresenta os comandos essenciais organizados por sistema operacional, facilitando o trabalho em diferentes ambientes.

## 🖥️ Identificando seu Sistema

Antes de começar, identifique qual terminal você está usando:

- **🪟 Windows**: PowerShell, Command Prompt (cmd), ou Windows Terminal
- **🐧 Linux**: Bash, Zsh, Fish (varia por distribuição)
- **🍎 macOS**: Terminal (Bash/Zsh), iTerm2

## 📋 Tabela Comparativa de Comandos

### 🗂️ **Navegação e Listagem**

| Função | Windows (PowerShell) | Windows (CMD) | Linux/Mac | Descrição |
|--------|---------------------|---------------|-----------|-----------|
| **Diretório atual** | `Get-Location` ou `pwd` | `cd` | `pwd` | Mostra o caminho atual |
| **Listar arquivos** | `Get-ChildItem` ou `ls` | `dir` | `ls` | Lista conteúdo do diretório |
| **Listar detalhado** | `ls -la` | `dir /a` | `ls -la` | Lista com detalhes e arquivos ocultos |
| **Navegar** | `Set-Location` ou `cd` | `cd` | `cd` | Muda de diretório |
| **Voltar diretório** | `cd ..` | `cd ..` | `cd ..` | Volta um nível |
| **Ir para home** | `cd ~` | `cd %USERPROFILE%` | `cd ~` | Vai para pasta do usuário |

### 📁 **Manipulação de Diretórios**

| Função | Windows (PowerShell) | Windows (CMD) | Linux/Mac | Descrição |
|--------|---------------------|---------------|-----------|-----------|
| **Criar pasta** | `New-Item -ItemType Directory` ou `mkdir` | `mkdir` | `mkdir` | Cria novo diretório |
| **Remover pasta vazia** | `Remove-Item` ou `rmdir` | `rmdir` | `rmdir` | Remove diretório vazio |
| **Remover pasta com conteúdo** | `Remove-Item -Recurse` | `rmdir /s` | `rm -rf` | Remove diretório e conteúdo |
| **Copiar pasta** | `Copy-Item -Recurse` | `xcopy /e` | `cp -r` | Copia diretório recursivamente |

### 📄 **Manipulação de Arquivos**

| Função | Windows (PowerShell) | Windows (CMD) | Linux/Mac | Descrição |
|--------|---------------------|---------------|-----------|-----------|
| **Criar arquivo** | `New-Item` ou `ni` | `type nul >` | `touch` | Cria arquivo vazio |
| **Copiar arquivo** | `Copy-Item` ou `cp` | `copy` | `cp` | Copia arquivo |
| **Mover/Renomear** | `Move-Item` ou `mv` | `move` ou `ren` | `mv` | Move ou renomeia |
| **Remover arquivo** | `Remove-Item` ou `rm` | `del` | `rm` | Remove arquivo |
| **Ver conteúdo** | `Get-Content` ou `cat` | `type` | `cat` | Exibe conteúdo do arquivo |
| **Editar arquivo** | `notepad` ou `code` | `notepad` | `nano` ou `vim` | Abre editor |

### 🔍 **Busca e Informações**

| Função | Windows (PowerShell) | Windows (CMD) | Linux/Mac | Descrição |
|--------|---------------------|---------------|-----------|-----------|
| **Buscar arquivos** | `Get-ChildItem -Recurse -Name` | `dir /s` | `find` | Busca arquivos |
| **Buscar texto** | `Select-String` | `findstr` | `grep` | Busca texto em arquivos |
| **Tamanho do arquivo** | `Get-Item \| Select Length` | `dir` | `ls -lh` | Mostra tamanho |
| **Espaço em disco** | `Get-PSDrive` | `dir` | `df -h` | Mostra espaço disponível |

### 🛠️ **Utilitários do Sistema**

| Função | Windows (PowerShell) | Windows (CMD) | Linux/Mac | Descrição |
|--------|---------------------|---------------|-----------|-----------|
| **Limpar tela** | `Clear-Host` ou `cls` | `cls` | `clear` | Limpa o terminal |
| **Histórico** | `Get-History` | `doskey /history` | `history` | Mostra comandos anteriores |
| **Processos** | `Get-Process` | `tasklist` | `ps` | Lista processos |
| **Matar processo** | `Stop-Process` | `taskkill` | `kill` | Termina processo |
| **Variáveis ambiente** | `Get-ChildItem Env:` | `set` | `env` | Lista variáveis |

## 🚀 Exemplos Práticos por Sistema

### 🪟 **Windows (PowerShell)**

```powershell
# Navegação básica
pwd                                    # Mostra diretório atual
ls                                     # Lista arquivos
cd Documents                           # Entra na pasta Documents
cd ..                                  # Volta um nível

# Criação e manipulação
mkdir meu-projeto                      # Cria pasta
cd meu-projeto                         # Entra na pasta
ni README.md                           # Cria arquivo
code .                                 # Abre VS Code

# Operações avançadas
ls -Recurse -Filter "*.js"            # Busca arquivos .js
Get-Content README.md                  # Lê arquivo
Copy-Item *.md backup/                 # Copia arquivos .md

# Git workflow
git status                             # Status do repositório
git add .                              # Adiciona mudanças
git commit -m "feat: adiciona README"  # Commit
git push origin main                   # Push para repositório
```

### 🐧 **Linux**

```bash
# Navegação básica
pwd                                    # Mostra diretório atual
ls -la                                 # Lista com detalhes
cd ~/Documents                         # Vai para Documents
cd -                                   # Volta ao diretório anterior

# Criação e manipulação
mkdir -p projetos/meu-app             # Cria pasta (com pais se necessário)
cd projetos/meu-app                   # Entra na pasta
touch README.md                       # Cria arquivo
nano README.md                        # Edita arquivo

# Operações avançadas
find . -name "*.js" -type f           # Busca arquivos .js
grep -r "TODO" .                      # Busca texto em arquivos
chmod +x script.sh                    # Torna arquivo executável
./script.sh                           # Executa script

# Gerenciamento de processos
ps aux | grep node                    # Busca processos Node.js
kill -9 1234                         # Mata processo por PID
nohup npm start &                     # Executa em background
```

### 🍎 **macOS**

```bash
# Navegação básica (similar ao Linux)
pwd                                    # Mostra diretório atual
ls -la                                 # Lista com detalhes
cd ~/Desktop                           # Vai para Desktop
open .                                 # Abre Finder no diretório atual

# Criação e manipulação
mkdir -p projetos/meu-app             # Cria pasta
cd projetos/meu-app                   # Entra na pasta
touch README.md                       # Cria arquivo
open -a "Visual Studio Code" .        # Abre VS Code

# Operações específicas do macOS
pbcopy < README.md                    # Copia conteúdo para clipboard
pbpaste > novo-arquivo.txt            # Cola do clipboard
say "Build completed"                 # Síntese de voz
open -a Safari index.html             # Abre arquivo no Safari

# Homebrew (gerenciador de pacotes)
brew install git                      # Instala Git
brew list                             # Lista pacotes instalados
brew update && brew upgrade           # Atualiza pacotes
```

## 🎯 Comandos Específicos para Desenvolvimento

### 📦 **Gerenciadores de Pacotes**

#### Windows
```powershell
# Chocolatey
choco install git nodejs vscode      # Instala ferramentas
choco list --local-only              # Lista instalados
choco upgrade all                    # Atualiza tudo

# Winget (Windows Package Manager)
winget install Git.Git              # Instala Git
winget search nodejs                # Busca Node.js
winget upgrade --all                # Atualiza tudo
```

#### Linux (Ubuntu/Debian)
```bash
# APT
sudo apt update                      # Atualiza lista de pacotes
sudo apt install git nodejs npm     # Instala ferramentas
sudo apt upgrade                     # Atualiza sistema
sudo apt autoremove                 # Remove pacotes desnecessários

# Snap
sudo snap install code --classic    # Instala VS Code
snap list                           # Lista snaps instalados
```

#### macOS
```bash
# Homebrew
brew install git node               # Instala ferramentas
brew cask install visual-studio-code # Instala aplicações
brew services start mongodb         # Inicia serviços
brew cleanup                        # Limpa cache
```

### 🔧 **Ferramentas de Desenvolvimento**

```bash
# Node.js (todos os sistemas)
node --version                       # Versão do Node.js
npm --version                        # Versão do NPM
npm init -y                         # Cria package.json
npm install express                 # Instala dependência
npm run dev                         # Executa script de desenvolvimento

# Python (todos os sistemas)
python --version                    # Versão do Python
pip install requests               # Instala biblioteca
python -m venv venv                # Cria ambiente virtual
source venv/bin/activate           # Ativa ambiente (Linux/Mac)
venv\Scripts\activate              # Ativa ambiente (Windows)

# Git (todos os sistemas)
git --version                      # Versão do Git
git config --global user.name "Nome"     # Configura nome
git config --global user.email "email"   # Configura email
git clone https://github.com/user/repo   # Clona repositório
```

## 💡 Dicas e Truques

### ⚡ **Atalhos Universais**
- **Tab**: Auto-completar comandos e nomes de arquivos
- **Ctrl + C**: Interromper comando em execução
- **Ctrl + L**: Limpar tela (alternativa ao `clear`)
- **Ctrl + R**: Buscar no histórico de comandos
- **↑/↓**: Navegar pelo histórico de comandos

### 🔍 **Wildcards e Padrões**
```bash
# Todos os sistemas
*.js                               # Todos os arquivos .js
file?.txt                          # file1.txt, file2.txt, etc.
[abc]*                            # Arquivos que começam com a, b ou c
{js,ts,jsx}                       # Múltiplas extensões
```

### 📝 **Redirecionamento**
```bash
# Salvar saída em arquivo
ls > lista-arquivos.txt           # Sobrescreve arquivo
ls >> lista-arquivos.txt          # Adiciona ao arquivo
command 2> erros.txt              # Redireciona erros
command > output.txt 2>&1         # Redireciona tudo
```

### 🔗 **Pipes e Combinações**
```bash
# Linux/Mac
ls -la | grep ".js"               # Lista apenas arquivos .js
ps aux | grep node | wc -l        # Conta processos Node.js
cat arquivo.txt | sort | uniq     # Ordena e remove duplicatas

# Windows (PowerShell)
Get-Process | Where-Object {$_.Name -like "*node*"}  # Filtra processos
Get-ChildItem | Sort-Object Name | Select-Object -First 10  # Primeiros 10
```

## 🚨 Comandos Perigosos - Use com Cuidado!

### ⚠️ **Comandos Destrutivos**
```bash
# CUIDADO! Estes comandos podem apagar dados importantes

# Linux/Mac
rm -rf /                          # ❌ NUNCA EXECUTE! Apaga tudo
sudo rm -rf /*                    # ❌ NUNCA EXECUTE! Apaga sistema
dd if=/dev/zero of=/dev/sda       # ❌ Apaga disco rígido

# Windows
del /f /s /q C:\*                 # ❌ Apaga arquivos do sistema
format C:                        # ❌ Formata disco principal
```

### ✅ **Alternativas Seguras**
```bash
# Sempre confirme antes de deletar
rm -i arquivo.txt                 # Pede confirmação (Linux/Mac)
Remove-Item -Confirm arquivo.txt  # Pede confirmação (PowerShell)

# Use lixeira quando possível
trash arquivo.txt                 # Linux (com trash-cli)
Move-Item arquivo.txt $env:RECYCLE # Windows (PowerShell)

# Faça backup antes de operações arriscadas
cp -r projeto/ projeto-backup/    # Linux/Mac
Copy-Item -Recurse projeto/ projeto-backup/  # Windows
```

## 🎓 Próximos Passos

### 📚 **Aprofundamento**
1. **Aprenda um editor de terminal**: `vim`, `nano`, ou `emacs`
2. **Domine o Git**: Controle de versão essencial
3. **Explore scripts**: Automatize tarefas repetitivas
4. **Configure aliases**: Crie atalhos personalizados
5. **Use multiplexadores**: `tmux` (Linux/Mac) ou Windows Terminal

### 🔗 **Recursos Relacionados**
- **[📜 Comandos Git](comandos-git.md)** - Comandos específicos do Git
- **[🎯 Como Usar Git](como-usar-git.md)** - Guia prático do Git
- **[🏗️ Fluxo Colaborativo](fluxo-colaborativo.md)** - Trabalho em equipe

### 🛠️ **Ferramentas Recomendadas**
- **Windows**: Windows Terminal, PowerShell 7, WSL2
- **Linux**: Zsh + Oh My Zsh, Terminator, Fish Shell  
- **macOS**: iTerm2, Oh My Zsh, Homebrew
- **Multiplataforma**: VS Code Terminal, Git Bash

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>
