# magneira.com.br

Site pessoal de **Magno Carvalho dos Santos**, publicado sob a marca **Magneira** — engenharia de software, tecnologia e inteligência artificial.

Gerado com [Marmite](https://marmite.blog/) e publicado no GitHub Pages a cada push na branch `main`.

## Estrutura

```text
content/            páginas (about.md, projects.md) e posts do blog
static/brand/       logotipos e assets de marca publicados no site
static/CNAME        domínio customizado (magneira.com.br)
brand/              material-fonte da identidade visual (guia de marca, conceitos)
marmite.yaml        configuração do site (menu, autor, tema)
custom.css/js       identidade visual da Magneira sobre o tema padrão do Marmite
```

## Build local

```console
$ cargo install marmite
$ marmite . site
```

O site gerado fica em `site/`.

## Deploy

O workflow [.github/workflows/main.yaml](.github/workflows/main.yaml) builda e publica automaticamente no GitHub Pages a cada push em `main`. O domínio customizado é definido em `static/CNAME` e mapeado para a raiz do site via `file_mapping` no `marmite.yaml`.
