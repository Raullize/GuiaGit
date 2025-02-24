<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>


# 🔀 O que são Conflitos de Merge?

Conflitos de merge ocorrem quando o Git não consegue combinar automaticamente mudanças feitas em duas branches diferentes.

## ⚠️ Tipos de Conflitos

- **Alterações Conflitantes**: Mudanças incompatíveis feitas na mesma linha de um arquivo.
- **Exclusões Conflitantes**: Um desenvolvedor exclui uma linha ou arquivo que outro modificou.

## 🛠️ Como Resolver Conflitos de Merge?

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

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>