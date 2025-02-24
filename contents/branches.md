<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=header"/>

# 🌿 O que são Branches?

Branches são ramificações que permitem trabalhar em diferentes linhas de desenvolvimento dentro de um mesmo repositório.

## 🚀 Por que usar branches?

- **Isolamento de Trabalho**: Permite trabalhar em novas funcionalidades ou correções sem interferir na branch principal.
- **Histórico Organizado**: Mantém o histórico de desenvolvimento claro e bem estruturado.
- **Colaboração Facilitada**: Desenvolvedores podem trabalhar em suas próprias branches e integrar (merge) as mudanças quando finalizadas.

## 📂 Conceitos Fundamentais sobre Branches

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

## ❌ Quando Deletar Branches?

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

## ✏️ Renomear Branch

- **Renomear branch atual**:
  ```bash
  git branch -m novo-nome

- **Renomear branch específica**:
  ```bash
  git branch -m nome-antigo novo-nome

---

[🔙 Voltar ao índice principal](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=F05032&height=120&section=footer"/>