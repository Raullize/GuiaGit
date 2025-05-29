<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🛠️ Boas Práticas e Dicas

## 📝 Mensagens de Commit

### Estrutura Ideal
```plaintext
<tipo>[escopo opcional]: <descrição>

[corpo opcional]

[rodapé opcional]
```

### Exemplos de Bons Commits
```plaintext
✅ feat(auth): adiciona autenticação com Google
✅ fix(api): corrige tratamento de erros na rota /users
✅ docs(readme): atualiza instruções de instalação
```

### Exemplos de Commits Ruins
```plaintext
❌ correção
❌ atualizando uns arquivos
❌ wip
```

### Dicas para Boas Mensagens
- Use verbos no imperativo: "adiciona", "corrige", "atualiza"
- Mantenha a primeira linha com até 50 caracteres
- Use o corpo para explicações detalhadas
- Referencie issues quando relevante

## 🌿 Organização de Branches

### Nomenclatura
```plaintext
feature/login-google
fix/memory-leak
docs/api-endpoints
refactor/auth-service
```

### Estrutura Recomendada
```plaintext
main
├── develop
│   ├── feature/user-auth
│   ├── feature/dashboard
│   └── fix/login-error
└── release/v1.2.0
```

## 🔍 Code Review

### Checklist do Autor
- [ ] Testes atualizados/adicionados
- [ ] Documentação atualizada
- [ ] Sem código comentado
- [ ] Variáveis com nomes significativos
- [ ] Commits organizados e descritivos

### Checklist do Revisor
- [ ] Código segue padrões do projeto
- [ ] Lógica está correta
- [ ] Tratamento de erros adequado
- [ ] Performance considerada
- [ ] Segurança avaliada

### Exemplo de Feedback Construtivo
```plaintext
✅ "Podemos extrair essa lógica para uma função separada para melhor reutilização"
✅ "Sugiro adicionar validação para esse input"

❌ "Esse código está ruim"
❌ "Por que fez assim?"
```

## 📂 Organização do Repositório

### Estrutura de Diretórios
```plaintext
/
├── src/
│   ├── components/
│   ├── services/
│   └── utils/
├── tests/
├── docs/
└── scripts/
```

### Arquivos Essenciais
- `README.md`: Documentação principal
- `.gitignore`: Arquivos ignorados
- `CONTRIBUTING.md`: Guia de contribuição
- `.editorconfig`: Configurações do editor

## 🔄 Fluxo de Trabalho

### Antes de Começar
1. Atualize a branch principal
   ```powershell
   git checkout main
   git pull origin main
   ```

2. Crie uma branch descritiva
   ```powershell
   git checkout -b feature/descricao-clara
   ```

### Durante o Desenvolvimento
1. Commits frequentes e atômicos
   ```powershell
   git commit -m "feat: adiciona validação de email"
   ```

2. Mantenha-se atualizado
   ```powershell
   git pull --rebase origin main
   ```

### Preparando para PR
1. Revise suas alterações
   ```powershell
   git diff main...feature/branch
   ```

2. Organize commits se necessário
   ```powershell
   git rebase -i main
   ```

## 🛡️ Segurança

### Proteção de Dados Sensíveis
- Use `.gitignore` para arquivos sensíveis
- Nunca commite credenciais
- Use variáveis de ambiente

### Exemplo de .gitignore
```plaintext
# Dependências
node_modules/
vendor/

# Ambiente
.env
.env.local

# Logs
*.log
npm-debug.log*

# Build
/dist
/build
```

## 🚀 Performance

### Otimização do Repositório
```powershell
# Limpar branches obsoletas
git remote prune origin

# Compactar repositório
git gc --aggressive

# Verificar arquivos grandes
git rev-list --objects --all | git cat-file --batch-check='%(objecttype) %(objectname) %(objectsize) %(rest)' | Select-String 'blob' | Sort-Object { [int]($_ -split '\s+')[2] } -Descending | Select-Object -First 10
```

### Arquivos Grandes
- Use Git LFS para arquivos binários grandes
- Considere ignorar arquivos de build
- Mantenha o repositório leve

## 📊 Monitoramento

### Análise de Contribuições
```powershell
# Ver estatísticas de contribuições
git shortlog -sn

# Ver alterações por autor
git log --author="nome" --oneline

# Ver mudanças em um período
git log --since="1 month ago" --oneline
```

## 🎯 Dicas Avançadas

### Aliases Úteis
```powershell
git config --global alias.st "status -sb"
git config --global alias.lg "log --oneline --decorate --graph"
git config --global alias.unstage "reset HEAD --"
```

### Hooks Úteis
```bash
#!/bin/bash
# pre-commit hook para verificar formato
npm run lint
npm run test
```

### Automação
- Use GitHub Actions para CI/CD
- Implemente verificações automáticas
- Configure releases automáticas

## ⚠️ Resolução de Problemas

### Prevenção
- Faça backup regular
- Documente decisões importantes
- Mantenha branches atualizadas

### Recuperação
```powershell
# Desfazer último commit
git reset --soft HEAD^

# Recuperar arquivo deletado
git checkout HEAD^ -- path/to/file

# Ver histórico de ações
git reflog
```

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>
