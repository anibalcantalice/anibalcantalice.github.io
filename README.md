# Meu site em Quarto

Template inicial de site pessoal/acadêmico feito com [Quarto](https://quarto.org),
pronto para hospedar no GitHub Pages.

## Antes de começar

1. Instale o **Quarto**: https://quarto.org/docs/get-started/
2. Tenha **R** e **RStudio** atualizados.

## Como usar

1. Abra a pasta no RStudio (ou em qualquer editor).
2. Edite os arquivos `.qmd` com o seu conteúdo:
   - `index.qmd` — página inicial (foto + apresentação)
   - `sobre.qmd` — sua trajetória
   - `blog/` — posts do blog (duplique a pasta em `blog/posts/` para criar novos)
   - `projetos.qmd` e `publicacoes.qmd`
3. Ajuste o menu, o título e os links em `_quarto.yml`.
4. Troque a imagem `img/avatar.png` pela sua foto (pode manter o mesmo nome).
5. Substitua todos os `seuusuario`, `Seu Nome` e `seu@email.com`.

## Visualizar localmente

No terminal, dentro da pasta:

```bash
quarto preview
```

O site abre no navegador e atualiza sozinho enquanto você edita.

## Publicar no GitHub Pages

### Passo 1 — Criar o repositório

- Para o endereço ficar `https://seuusuario.github.io/` (sem subpasta),
  nomeie o repositório **exatamente** como `seuusuario.github.io`.
- Qualquer outro nome resulta em `https://seuusuario.github.io/nome-do-repo/`.

### Passo 2 — Enviar os arquivos

```bash
git init
git add .
git commit -m "Primeira versão do site"
git branch -M main
git remote add origin https://github.com/seuusuario/seuusuario.github.io.git
git push -u origin main
```

### Passo 3 — Publicar

**Opção A (mais simples, manual):** renderize e publique com um comando:

```bash
quarto publish gh-pages
```

Depois vá em **Settings → Pages** do repositório e confirme que a fonte é a
branch `gh-pages`.

**Opção B (automática):** este projeto já inclui um GitHub Action em
`.github/workflows/publish.yml`. A cada `git push` na branch `main`, o site
é renderizado e publicado sozinho. Em **Settings → Pages**, aponte a fonte
para a branch `gh-pages`. Se o seu site executa código R, descomente o bloco
do R dentro do arquivo do workflow.

Pronto! Em poucos minutos o site fica no ar.
