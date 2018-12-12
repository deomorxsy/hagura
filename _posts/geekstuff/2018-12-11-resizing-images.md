---
layout: post
title:  "Image Resizing"
date:   2018-12-11 15:40:50
categories: technology
tags:
- shellscript
---

Postar imagens na internet é bem fácil, porém, dependendo da plataforma que você utilizar, pode encontrar problemas de visualização prévia como imagens que não cabem no espaço visualizado por serem grandes demais ou pequenas demais. zZz

De antemão, você precisará dos seguintes conhecimentos básicos para entender o código apresentado:

 - Comandos básicos de linha de comando / Bash
 - Formatos de Imagem
 - Estrutura básica de diretórios
 - Edição básica de imagem, crop

Vamos tomar como exemplo o **Stories do Instagram**, onde a resolução é sempre **1080 x 1920** e sua proporção **9:16**.

_PS: é prudente que antes de seguir os passos à seguir você **edite** a imagem que você quer o mais próximo da proporção 9:16, já que o script apenas redimensiona, e não [cropa](https://en.wikipedia.org/wiki/Cropping_(image))._

Podemos então construir um pequeno script pela linha de comando que vai redimensionar as resoluções da imagem que você quer upar.

Primeiramente, vá até o diretório onde as imagens que você quer redimensionar estão, crie a pasta de destino após o processo (que no caso é **final**), e o arquivo do script **arquivo.sh** com os comandos abaixo

![]( https://i.imgur.com/iJBSyjm.jpg )

Copie o resultado do List, abra o arquivo .sh no seu editor de código ou texto, cole o nome dos arquivos entre os apóstrofos na variável l1 do código abaixo e, lembrando que todas as imagens devem estar em um mesmo formato (.jpg ou .png), edite retirando todos aqueles nomes de arquivo que não são imagens ou você não quer.

{% highlight bash %}
#!/bin/bash

l1=('cole aqui o código')

for l1 in *.jpg; do convert $l1 -resize 1080x1920! final/$l1; done

{% endhighlight %}

Por fim, rode o programa com

{%highlight bash%}

sh ./script.sh 

{% endhighlight%}

<p>Confira o arquivo do código no repositório github!</p>