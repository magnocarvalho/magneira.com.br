---
title: "Transcrever arquivo MP3 em Texto com Python e API do Google Cloud Speech-to-Text"
description: "Um exemplo em Python para converter um arquivo MP3, dividir o áudio e gerar uma transcrição usando o Google Cloud Speech-to-Text."
slug: transcrever-arquivo-mp3-em-texto-com-python-e-google-cloud-speech-to-text
date: 2024-07-28
tags:
  - arquivo
  - python
  - google-cloud
  - speech-to-text
  - automacao
toc: true
---

> **Publicado originalmente no LinkedIn em 28 de julho de 2024.**  
> Esta versão foi migrada para o blog da Magneira a partir da publicação original:  
> <https://www.linkedin.com/pulse/transcrever-arquivo-mp3-em-texto-com-python-e-api-do-magno-fe0lf/>

Esta semana, precisei transcrever um áudio de aproximadamente duas horas, gravado durante uma aula e com qualidade de captação limitada. Depois de algumas pesquisas, montei um script em Python para automatizar o processo.

## Requisitos

- FFmpeg 7.0.1
- Python 3.12

## Configuração

O fluxo converte o MP3 para WAV, divide o áudio em trechos de 60 segundos e envia os segmentos para o Google Cloud Speech-to-Text. Ao final, a transcrição é salva em um arquivo de texto.

Instale as dependências:

```bash
pip install pydub google-cloud-speech
```

No Google Cloud Console, crie ou selecione uma Service Account, gere uma chave JSON e configure o caminho desse arquivo no código.

Também é necessário ter o FFmpeg disponível no `PATH`.

### macOS

```bash
brew install ffmpeg
```

### Linux

```bash
sudo apt update
sudo apt install ffmpeg
```

## Código

O projeto utilizado no artigo está disponível no GitHub:

<https://github.com/magnocarvalho/converter-audio-texto-py>

Ajuste no código os caminhos da credencial JSON, do arquivo MP3 de entrada e do arquivo de texto de saída.

## Custos

O uso do Google Cloud Speech-to-Text está sujeito à cobrança conforme o volume de áudio processado.
