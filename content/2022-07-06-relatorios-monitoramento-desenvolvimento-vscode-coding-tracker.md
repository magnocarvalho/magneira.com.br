---
title: "Relatórios e Monitoramento de Desenvolvimento com Visual Studio Code | Coding Tracker"
description: "Uso do Coding Tracker no Visual Studio Code para acompanhar tempo de desenvolvimento, arquivos, linguagens, branches e projetos."
slug: relatorios-monitoramento-desenvolvimento-vscode-coding-tracker
date: 2022-07-06
tags:
  - arquivo
  - vscode
  - produtividade
  - engenharia-de-software
  - metricas
---

> **Publicado originalmente no LinkedIn em 6 de julho de 2022.**  
> Esta versão foi migrada para o blog da Magneira a partir da publicação original:  
> <https://www.linkedin.com/pulse/relat%C3%B3rios-e-monitoramento-de-desenvolvimento-com-magno-/>

O Coding Tracker é uma extensão que eu utilizava no Visual Studio Code para acompanhar meu desempenho pessoal como programador.

Entre os dados monitorados estão o tempo com um arquivo em foco, o tempo efetivamente digitando código, linguagens com maior interação, arquivos que consumiram mais tempo, branches com maior esforço e duração de cada projeto.

Os dados locais ficam em:

```text
$HOME/.coding-tracker/
```

Essas informações podem formar uma base histórica de projetos. Em um fluxo como Gitflow, no qual cada branch costuma representar um escopo específico, é possível comparar estimativa e tempo realmente utilizado e melhorar estimativas futuras.

Eu também utilizava os dados para recuperar as horas de tarefas e posteriormente registrá-las em ferramentas como Jira ou Toggl.

Para abrir o relatório no VS Code, use a paleta de comandos e execute:

```text
CodingTracker: Show your coding activities report
```

A extensão continua disponível no Visual Studio Marketplace:

<https://marketplace.visualstudio.com/items?itemName=hangxingliu.vscode-coding-tracker>

Código-fonte:

<https://github.com/hangxingliu/vscode-coding-tracker>
