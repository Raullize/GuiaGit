<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=180&section=header"/>

# 📌 Versionamento Semântico

O versionamento semântico segue o formato `MAJOR.MINOR.PATCH` (`X.Y.Z`), onde:

- **MAJOR (X):** Mudanças que **quebram a compatibilidade** com versões anteriores.  
  - Exemplo: `2.0.0` → Alterações estruturais na API que exigem ajustes no código.  
  - Identificado com `BREAKING CHANGE` ou `feat!`, `fix!`.  

- **MINOR (Y):** Novas funcionalidades **compatíveis** com versões anteriores.  
  - Exemplo: `1.2.0` → Adicionando um novo recurso sem afetar código existente.  
  - Identificado com `feat:`.  

- **PATCH (Z):** Correções de bugs sem alterar funcionalidades.  
  - Exemplo: `1.2.3` → Correção de erro sem impacto na API.  
  - Identificado com `fix:`.  

### Exemplo de commits convencionais:

```bash
git commit -m "fix: corrige erro na validação do formulário"
# Atualiza apenas o PATCH (ex: 1.2.3 → 1.2.4)

git commit -m "feat: adiciona suporte a login com Google"
# Atualiza o MINOR (ex: 1.2.3 → 1.3.0)

git commit -m "feat!: altera estrutura de autenticação"
# Atualiza o MAJOR (ex: 1.2.3 → 2.0.0)
```
Esse método é útil para automação de releases e organização do código. 🚀

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>