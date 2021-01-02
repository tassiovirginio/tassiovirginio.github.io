---
title:  "Tendências dos Repositórios do Archlinux"
date:   2021-01-02 19:00
categories: [linux, arch]
tags: [linux,arch, kde, plasma]
published: true
---

O Archlinux é uma distro muito conhecida, e de certa forma temida para os novatos no mundo linux. É uma distribuição Rolling Release, o que significa que sempre vai ter as mais novas versões das suas bibliotecas “em teoria”. Como qualquer outra distro os pacotes do Archlinux passam por um processo para poder entrar na sua versão “stable”, sendo um dos mais rápidos das distribuições existentes “se não for a mais rápida”.

O Arch o seu gerenciamento de pacotes bem aberto, no site https://archlinux.org/packages/ você pode realizar a busca por qualquer pacote que queira, nele vai ter as informações sobre o pacote como: nome do pacote, qual a versão atual, o mantenedor, a última pessoa que fez o envio do pacote, tamanho do pacote, entre outras informações (figura abaixo).

![Image01](/images/artigo_arch/image01.png)

Outra característica é que o pacote pode ser marcado como desatualizado, como pode ser visto no exemplo na figura a baixo.

![Image02](/images/artigo_arch/image02.png)

Outro ponto de destaque do Archlinux é seu repositório dos usuários “AUR”, onde qualquer usuário pode postar seu pacote, que na verdade é um arquivo PKGBUILD, com todas as instruções para instalar a aplicação/biblioteca no arch.

![Image03](/images/artigo_arch/image03.png)

O sistema de pacotes do Arch utiliza do git para gerenciar seus pacotes, qualquer pessoa pode criar uma conta no site do AUR e enviar seu pacote através do git. Ou pode baixar um pacote existente e atualizar o mesmo.

![Image04](/images/artigo_arch/image04.png)

Como visto na figura acima temos a opção de escrever um comentário sobre o pacote, essa ação envia uma notificação para o mantenedor do pacote, o qual pode “ou não” responder seu comentário. Boa parte da comunidade Archlinux gosta de iteração, não que eles sejam muito cordiais, mas pela minha experiência são bem metódicos. 

Finalmente cheguei a parte que dá tema a esse artigo, com todo esse controle sobre seus pacotes, o Archlinux consegue gerar estatísticas dos seus utilizadores. E com esses dados existe um site (https://pkgstats.archlinux.de/fun) que nos dá uma visão interessante sobre seus utilizadores.

![Image05](/images/artigo_arch/image05.png)

Esse site nos trás os informações sobre: Navegadores, Editores, Desktops, Gerenciadores de Arquivos, Gerenciador de Janelas, Shells, entre outros. A partir disso podemos notar as caracteristicas (da maioria) dos usuários do Archlinux, iniciando pelo navegador, o qual se destaca o Firefox, seguido pelo Chromium, depois o Google-Chrome, como podemos ver na figura abaixo. Achei interessante o Chromium esta sem segundo lugar, sempre tive a impressão que ele não era muito utilizado (uma boa surpresa).

![Image06](/images/artigo_arch/image06.png)

Agora vamos ver os editores de texto, o qual se destaca o Nano, seguido pelo VI, e depois o Vim. Algo a se notar é a queda que o Nano e Vi estão tendo, e a subida do Vim.

![Image07](/images/artigo_arch/image07.png)

E finalmente os dados dos Desktop Environments, algo interessante a se notar é que o GNOME SHELL 3 teve uma alta utilização desde o seu lançamento (2011), e de certa forma ficou estável até os dias de hoje, o XFCE teve um crescimento na época do lançamento do GNOME SHELL, ficou estável por um tempo e começou a cair ultimamente. O KDE Plasma 5 foi lançado em 2014 e desde seu lançamento não para de crescer, se destacando no gráfico, tendo a curva mais proeminente, ultrapassando o GNOME SHELL e o XFCE.

![Image08](/images/artigo_arch/image08.png)

Esses dados são somente de uma distribuição, mas o Archlinux é uma distribuição que deixa na mão do usuário quais aplicativos ele vai querer utilizar, claro que os dados dessa mesma maneira de uma distribuição Ubuntu ou Pop-OS trariam dados provavelmente bem diferentes, mas são distribuições “prontas”. O que os dados do Archlinux trás são as escolhas dos seus usuários de forma crua, mostrando as preferências de cada tipo de pacote que eles querem utilizar. Não vejo muitas distribuições da moda utilizarem o Plasma, e ficamos sempre com a impressão que poucas pessoas utilizam, mas pelo visto, pelo menos nos usuários do Archlinux, ela é bem utilizada. 
Queria lembrar que os repositórios do Archlinux são utilizados por várias outras distribuições, como o Manjaro, Endeavour e outros.

Como será que vai esta esses dados nesse ano de 2021? Vamos ter surpresas?

Até a próxima…

Tássio Virgínio


