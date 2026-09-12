---
title: "Meu TCC de 2019: uma plataforma de promoções por geolocalização"
description: "Como nasceu o Gastando Pouco, meu TCC de Engenharia de Software na UTFPR — uma plataforma MEAN Stack de promoções baseada em geolocalização."
slug: tcc-utfpr-magno
date: 2019-12-01
tags:
  - arquivo
  - tcc
  - utfpr
  - geolocalizacao
  - mongodb
---

# Meu TCC de 2019: uma plataforma de promoções por geolocalização

Em 2019, concluí minha graduação em Engenharia de Software na UTFPR com um projeto que, olhando hoje, representa bem o tipo de problema que sempre gostei de resolver: pegar uma ideia, estruturar tecnicamente e construir o produto de ponta a ponta.

Meu Trabalho de Conclusão de Curso se chamava **“Desenvolvimento de uma plataforma MEAN Stack de veiculação publicitária por geolocalização”**.

O nome era acadêmico. A ideia era mais simples.

Eu queria construir uma plataforma em que estabelecimentos pudessem publicar promoções e os usuários encontrassem ofertas próximas utilizando a própria localização.

O projeto ficou conhecido como **Gastando Pouco**.

## A ideia começou antes do TCC

A origem do projeto foi alguns anos antes, em uma competição de empreendedorismo: o **Startup Weekend Londrina de 2016**.

A proposta era aproximar estabelecimentos locais de consumidores que estivessem próximos.

Imagine uma loja publicando uma promoção e, em vez de aquela informação simplesmente aparecer para qualquer pessoa na Internet, a localização do estabelecimento fazer parte da própria lógica da aplicação.

O usuário informaria — mediante autorização — sua localização. A plataforma teria latitude e longitude das empresas cadastradas e conseguiria responder algo próximo de:

**“Quais estabelecimentos com promoções ativas existem perto de mim?”**

Essa ideia acabou virando o escopo do meu TCC.

## O projeto

A aplicação foi dividida em três partes principais.

### O sistema da empresa

Existia uma aplicação administrativa para os estabelecimentos.

A empresa podia criar sua conta, cadastrar seus dados e localização, publicar promoções, editar publicações existentes e acompanhar informações relacionadas às ofertas.

Na prática, já existia ali um pequeno painel administrativo.

Eu tinha páginas específicas para cadastro de promoções, listagem das publicações, edição, perfil da empresa e relatórios.

Uma promoção possuía informações como período de validade, empresa responsável e categoria. O sistema precisava saber não apenas **o que estava sendo anunciado**, mas também **onde aquela empresa estava localizada**.

### O sistema do cliente

Do outro lado existia o site utilizado pelo consumidor.

Ao entrar na aplicação, o usuário autorizava o acesso à sua localização. O frontend capturava latitude e longitude e enviava essas informações para a API junto com outros parâmetros da busca, como distância e categorias.

A partir disso, a aplicação apresentava as promoções disponíveis naquela região.

O usuário também podia visualizar uma empresa, consultar suas promoções, filtrar ofertas por categoria e salvar promoções como favoritas.

Era basicamente um **feed de promoções baseado em localização**.

## A parte que eu mais queria explorar: geolocalização

Um dos objetivos técnicos do trabalho era justamente experimentar o uso de coordenadas geográficas em uma aplicação completa.

Não queria apenas pegar latitude e longitude no navegador e mostrar os números na tela.

A localização precisava participar da regra de negócio.

O frontend capturava a posição do usuário e enviava para o backend parâmetros como:

`latitude`

`longitude`

`distância`

A API utilizava essas informações para consultar o MongoDB e descobrir quais empresas estavam dentro da região definida.

No backend, a consulta utilizava recursos geoespaciais do próprio MongoDB, incluindo operações como `$geoNear` e `$geoWithin`.

Depois de localizar as empresas próximas, a aplicação relacionava cada estabelecimento às promoções cadastradas e considerava também o período de validade das ofertas.

Isso transformava latitude e longitude em algo útil para o produto.

Não era apenas:

> “O usuário está nesta coordenada.”

Era:

> “Considerando esta coordenada e este raio, quais informações são relevantes para esse usuário?”

Essa diferença era uma das principais provas de conceito que eu queria construir.

## A arquitetura

Na época escolhi trabalhar com a chamada **MEAN Stack**:

**MongoDB + Express + Angular + Node.js.**

Um dos objetivos do TCC era utilizar JavaScript/TypeScript ao longo de praticamente toda a aplicação.

No frontend, Angular.

No backend, Node.js com Express.

Para persistência, MongoDB.

Para comunicação entre as aplicações, uma API utilizando JSON.

Também utilizei Firebase em partes da solução, incluindo autenticação, armazenamento de imagens e hospedagem das aplicações web.

O resultado era uma arquitetura com dois frontends independentes consumindo uma mesma aplicação de backend.

Hoje isso parece uma divisão bastante natural, mas o objetivo naquele momento era justamente utilizar o projeto para estudar como essas tecnologias poderiam trabalhar juntas em uma aplicação real.

## Não era só código

Uma coisa interessante ao revisitar o projeto é perceber quanto trabalho de Engenharia de Software existia ao redor da implementação.

Eu defini requisitos funcionais separadamente para empresa e cliente, requisitos não funcionais, arquitetura, modelo de dados, backlog e processo de desenvolvimento.

Também adaptei o **Scrum Solo** para organizar o trabalho.

As sprints tinham duração de sete dias e eu registrava a evolução do projeto a cada ciclo.

Isso provavelmente parece exagerado para um projeto desenvolvido por uma única pessoa.

Mas esse também era o objetivo.

O TCC não era apenas entregar uma aplicação funcionando. Era aplicar, em um projeto relativamente completo, os conhecimentos adquiridos durante a graduação.

## O que foi entregue

No final, o projeto tinha um conjunto razoavelmente grande de funcionalidades para uma prova de conceito.

Existiam autenticação, cadastro de empresas, cadastro e edição de promoções, localização dos estabelecimentos, localização do usuário, busca por distância, categorias, favoritos, visualização das empresas, mapas, upload de imagens, frontend administrativo, frontend público e uma API responsável pelas regras de negócio.

Era um MVP.

Inclusive, foi assim que defini o projeto nas considerações finais do TCC.

O objetivo nunca foi construir um marketplace completo.

Não existiam pagamentos dentro da plataforma e também não existia uma comunicação direta entre empresa e consumidor.

O foco era validar a arquitetura e principalmente a ideia de **organizar promoções utilizando a localização como um dos principais parâmetros da busca**.

## O que eu faria diferente hoje

Sete anos é bastante tempo quando estamos falando de desenvolvimento de software.

As versões das ferramentas mudaram. Algumas bibliotecas desapareceram. Outras abordagens de arquitetura se tornaram mais comuns.

Eu certamente estruturaria várias partes desse código de outra forma hoje.

Mas é exatamente isso que torna interessante manter projetos antigos disponíveis.

O repositório é praticamente uma fotografia de como eu pensava desenvolvimento de software naquele momento.

É possível encontrar decisões boas, decisões questionáveis, código que eu provavelmente não escreveria novamente e problemas que continuam bastante atuais.

Autenticação.

APIs.

Separação entre frontend e backend.

Geolocalização.

Consultas geoespaciais.

Upload de arquivos.

Autorização.

Experiência do usuário.

Deploy.

Modelagem dos dados.

São problemas que continuam aparecendo nos sistemas que construímos atualmente, mesmo que as ferramentas tenham mudado.

## Algumas ideias que ficaram para depois

No próprio TCC deixei uma seção de trabalhos futuros.

Entre as possibilidades estavam criar aplicativos para Android e iOS, permitir compartilhamento das promoções nas redes sociais, gerar códigos de desconto e enviar notificações push para pessoas próximas quando uma empresa publicasse uma nova promoção.

Algumas dessas ideias hoje parecem bastante óbvias.

Em 2019, porém, elas representavam a continuação natural daquela prova de conceito.

## Por que estou publicando isso agora

Estou começando este blog e quero utilizar parte dele para registrar não apenas o que estou construindo atualmente, mas também alguns projetos que fizeram parte da minha trajetória.

Não pretendo atualizar o código do Gastando Pouco para fingir que ele foi escrito hoje.

A graça é justamente o contrário.

Quero preservar esses projetos como registros de uma época, explicar o problema que eu estava tentando resolver, as decisões que tomei e o que aprendi durante o processo.

Esse TCC foi um desses projetos.

Foi uma oportunidade de transformar uma ideia que surgiu em um Startup Weekend em uma aplicação funcional, passando por levantamento de requisitos, arquitetura, banco de dados, frontend, backend, deploy e documentação.

E também foi o projeto que encerrou uma etapa importante: minha graduação em Engenharia de Software.

Para quem quiser explorar o código, os diagramas, documentos e até diferentes versões do próprio TCC, o repositório continua disponível:

**github.com/magnocarvalho/tcc**

Talvez daqui a alguns anos seja interessante voltar novamente neste projeto e comparar não apenas as tecnologias, mas também como mudou minha forma de pensar software.
