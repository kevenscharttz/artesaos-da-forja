## Construindo um SAAS de gestão de redes Sociais: Overview

A ideia principal do projeto é a construção de um **SAAS** para a gestão de redes sociais, a principal dor que será enfrentada é o agendamento e publicação de conteúdos em diversas redes de uma única vez. Outra coisa é a automatização de legendas, descrições e demais funções, com o uso do **chatGPT**. O primeiro passo pensado é o **cadastro**, que terá um login social ou um e-mail e senha, com um requisito de autenticação de dois fatores, e isso é primordial para a questão de segurança.

No primeiro acesso o usuário deve ser redirecionado para um onboarding, que pega o usuário com a mão para fazer a integração de suas redes sociais, como instagram, tiktok e youtube. E isso é interessante para que com isso feito o usuário já caia em um dashboard, onde ele terá acesso a relatórios de performance geral, por rede e por conteúdo.

O processo de publicação é o seguinte, que deve ser muito simplificado tem que agendar em todas as redes de uma única vez, com um formulário apenas para todas, e também o chatGPT para automatizar a descrição, hashtags e títulos. 

## Modelagem base do banco

Primeiro um campo de **users**, onde vamos ter o nome, email e senha, os **tenants** que serão as empresas que vão usar a plataforma, com seu id e nome e as **medias** que serão as redes-sociais com seu id e nome, que de começo será lidado apenas com tiktok, youtube e instagram. Uma tabela auxiliar será gerada ligando de muitos para muitos as **tenants** com as **medias**, com o id dessa tabela, as chaves estrangeiras e um token.

Também existirá uma tabela de **contents**, com os conteúdos que estarão ligados com cada **tenant**, com título, descrição e tags. Vamos ter também a tabela de **content_scheduling**, responsável pelo agendamento, com o id, a chave estrangeira de **contents**, a chave estrangeira de **media_tenant_id**, porém mesmo que seja um vídeo postado na hora, faz sentido essa tabela existir pois estará ligada com o **content_comment**, para termos uma ideia de quantas views, likes, comentários, enfim, dados interessantes, com comment, name e email.



