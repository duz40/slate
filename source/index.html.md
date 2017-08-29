---
title: Documentação API

language_tabs: # must be one of https://git.io/vQNgJ
  - http

---

# API War-Room V2

**Endpoint da API:**

[https://stilingueapi.appspot.com](https://stilingueapi.appspot.com)

# Token de acesso

**Para resgatar o token de acesso:**

**1) Vá na configuração de um painel de pesquisa personalizada.**

**2) Gere o token de acesso à API (ao final do formulário).**

**3) Envie um email para [milton@stilingue.com.br](milton@stilingue.com.br) confirmando a liberação.**

# Requisições HTTPS GET

## Metadados

> Exemplo do link para GET

>metadados

```http
/wrapi/metadados/<TOKEN>
```

> Substitua `<TOKEN>` pelo seu token de acesso

Requisição responsável por trazer informações a utilização da API pelo cliente.

# Requisições HTTPS POST

**Atributos de um post:**

Atributo | Tipo | Descrição
-------- | ---- | ---------
user_url | string | link do perfil que fez a publicação.
user_image_url | string | link da imagem do perfil que fez a publicação.
uid | string | identificador do perfil.
name | string | nome do perfil que publicou.
username | string | username do perfil que publicou.
followers | int | número de seguidores do perfil que publicou.
post_url | string | link da publicação.
image_url | string | link da imagem da publicação.
interests | string[ ] | lista de interesses do war-room.
long_posted_at | long | data de postagem em milisegundos.
groups | string[ ] | lista de grupos configurados na pesquisa.
location | string | Estado e Cidade.
title | string | título da publicação.
text | string | texto da publicação.
pid | string | identificador da publicação.
channel | string | canal da publicação. Exemplo: Facebook, Twitter, Instagram, Portais, YouTube.
metrics_updated_at | string | última hora que as métricas sociais foram atualizadas.
mentions | string[ ] | lista de menções que aconteceram na publicação.
hashtags | string[ ] | lista de hashtags que aconteceram na publicação.
sentiment | int | sentimento geral do texto. Um é positivo, menos um é negativo e zero é neutro.
likes | int | número de curtidas/favoritos da publicação.
shares | int | número de compartilhamentos da publicação.
comments | string | número de comentários da publicação.
videoplays | string | número de visualizações da publicação.
spam | boolean | se a publicação foi marcada como spam.
hot | float | score customizado que representa a importância da publicação baseado no momento.
AAA_score | float | score exclusivo do stilingue que representa a importância do perfil.
favorite | boolean | publicação seja favoritada no war-room.
replied | boolean | publicação foi respondida pelo war-room.
verified | boolean | perfil verificado pela rede social.
gender | string | gênero do perfil que publicou (Marca, Homem ou Mulher).

<aside class="notice">
Para enviar vários valores em um parâmetro só, utilizar o separador “:” (dois pontos)
</aside>

##Publicações

> Exemplo dos links para POST

>publicações

```http
/wrapi/publicacoes/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | Formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
offset | Requisitar posts a partir de tal posição
limit | Quantidade de posts por requisição (máximo = 100)
channels | Twitter, Instagram, Facebook, YouTube, Google+, entre outros
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Organização
devices | Computador, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações @Brasil
annotated | `<true ou false>` para filtrar só posts anotados
order_by | date_desc, date_asc, hot, interactions, likes, shares, comments

##Influenciadores

>influenciadores

```http
/wrapi/influenciadores/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
username | 
channel | Twitter, Instagram, Facebook, YouTube, Google+, ...

##Busca Express [ACESSO RESTRITO]

>busca express

```http
/wrapi/buscaexpress/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
query | OBRIGATÓRIO
offset | Requisitar posts a partir de tal posição
limit | Quantidade de posts por requisição (máximo = 20) 
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Termos Correlacionados

>termos correlacionados

```http
/wrapi/termos/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Ranking AAA

>ranking AAA

```http
/wrapi/aaa/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Distribuição Grupos & Temas

>distribuição grupos & temas

```http
/wrapi/estatisticas/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Visão Geral

Requisições usadas no visão geral.

###Distribuição de Termos

>distribuição de termos

```http
/wrapi/estatisticas_termos/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento dos Temas

>sentimento dos temas

```http
/wrapi/sentimento_temas/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento dos Links

>sentimento dos links

```http
/wrapi/sentimento_links/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento dos Domínios

>sentimento dos dominios

```http
/wrapi/sentimento_dominios/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento em Hashtags

>sentimento nas hashtags

```http
/wrapi/sentimento_hashtags/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento em Tags

>sentimento nas tags

```http
/wrapi/sentimento_tags/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento por buscas

>sentimento por buscas

```http
/wrapi/sentimento_buscas/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento por Regiões

>sentimento por regioes

```http
/wrapi/sentimento_regioes/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Sentimento por grupos

>sentimento por grupos

```http
/wrapi/sentimento_grupos/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Gráfico de publicações no tempo

> grafico de publicacoes

```http
/wrapi/linechart/<TOKEN>
```

> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

###Visão geral

A maior parte das informações fica nesta requisição

> visao geral

```http
/wrapi/visao_geral/<TOKEN>
```

> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Onde falam

>onde falam

```http
/wrapi/onde/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Manchetes Sociais

>manchetes sociais

```http
/wrapi/manchetes/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Temas e Tópicos

>temas e topicos

```http
/wrapi/temasetopicos/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

##Top Influenciadores

>top influenciadores

```http
/wrapi/top_influenciadores/<TOKEN>
```
> Substitua `<TOKEN>` pelo seu token de acesso

**Parâmetros:**

Parâmetro | Descrição
--------- | ---------
date_range | formato `<YYYYMMDDhhmm:YYYYMMDDhhmm>`
channels | Twitter, Instagram, Facebook, YouTube, Google+, ...
interests | Lista de Interesses do War-Room
genders | Homem, Mulher ou Marca
groups | Título dos grupos disponíveis na pesquisa
themes | Temas dos grupos disponíveis na pesquisa
tags | Tags dos grupos disponíveis na pesquisa
devices | Desktop, Mobile
types | Text, Image, Video, Audio
sentiment | (-1), (0), (1)
locations | Lista de localizações do Brasil

#Observações

* Não é seguro expor a URL de acesso aos resultados em um cliente (ex: acessar via javascript). As chamadas de API devem acontecer em um ambiente fechado.
* Caso queira bloquear um token de acesso, basta ir em Editar Pesquisa Personalizada > ACESSO À API E PLUGINS DESSA PESQUISA.

<aside class="success">
Havendo necessidade de configurar mais contas / pesquisas, entrar em contato com <a href="milton@stilingue.com.br">milton@stilingue.com.br</a> para liberação (processo rápido, mas importante para garantir segurança da informação).
</aside>