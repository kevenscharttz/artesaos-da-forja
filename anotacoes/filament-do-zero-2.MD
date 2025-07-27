## Qual a maior dificuldade na hora de gerenciar as redes sociais?

Dentre várias coisas faladas, as mais pontuais que foram:
* Trabalhar com diferentes redes-sociais;
* Painéis de performance separados;
* Conhecimentos baixos com B.I;
* Dificuldade de unir os resultados de conteúdo especifico;

Uma que foi citada também foi a dificuldade pelo grande gerenciamento de redes-sociais, decorrentes de muitas organizações diferentes, por exemplo: Empresa 1 tem 4 redes, empresa 2 tem 3 redes, empresa 3 tem 12 redes, e por aí vai.

Outra coisa que já nos adiantamos no nosso **MVP** foi quanto ao número de conteúdos, redes, enfim, é difícil identificar performance por rede.

Leva muito tempo para programar conteúdo orgânico em todas as redes sociais, ferramentes difficiles de usar e com interface confusa.

## Qual o tipo de conteúdo geralmente postado? 

Dentre tantas opções, podemos citar: carrousel, vídeos curtos com CTA, vídeos curtos de engajamento, vídeos completos, criativos de anuncio. E não necessariamente ficamos presos a isso, podemos ir de vídeos curtos a textões no linkedin, ou seja, existe todo tipo de conteúdo.

## Quais redes sociais mais gerenciadas?

Dentre essa imensidão de redes, as mais citadas foram: Instagram, Youtube, Tiktok, Telegram, Whatsapp, Facebook, Linkedin...

## Quais ferramentas deste tipo são comumente usadas? 

Foram citadas muitas ferramentas como: mlabs, hootsuit, sendpulse, rdstation, latergram, postgrain. E o que falta muito nessas ferramentas é uma visão completa dos conteúdos, uma interface fácil de utilizar, agilizada de na publicação de conteúdo, agrupamento de empresas diferentes, múltiplos usuários por organização, publicar conteúdo de uma só vez em todas as redes...

## Criação das primeiras tabelas do nosso projeto

```SQL
TABLE organizations{
  id int [pk, INCREMENT]
  name varchar
}

TABLE users {
  id int [pk, INCREMENT]
  name varchar
  email varchar [unique]
  password varchar 
}

TABLE organization_user {
  id int [pk, increment]
  organization_id int [ref: > organizations.id]
  user_id int [ref: > users.id]
  is_admin bool
}

TABLE medias {
  id int [pk, increment]
  name varchar
}

TABLE media_organization {
  id int [pk, increment]
  organization_id int [ref: > organizations.id]
  media_id int [ref: > medias.id]
}

TABLE contents {
  id int [pk, increment]
  organization_id int [ref: > organizations.id]
  title varchar
  description text
  tags text
  url_file varchar
  type varchar
}

TABLE contents_scheduling {
  id int [pk, increment]
  media_organization_id int [ref: > media_organization.id]
  content_id int [ref: > contents.id]
  scheduling datetime

}

TABLE content_comment {
  id int [pk, increment]
  content_scheduling_id int [ref: > contents_scheduling.id]
  parent_id int [ref: > content_comment.id]
  comment text
  name varchar
  email varchar
}
```