---
description: Uma introdução da ferramenta.
icon: info
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Introdução

***

## Docker

É uma plataforma aberta criada para facilitar o desenvolvimento, a implantação e a execução de aplicações em ambientes isolados. Foi desenhada especialmente para disponibilizar uma aplicação da forma mais rápida possível.

Utilizando o Docker como ferramente é possível desenvolver aplicações em um _ambiente_ controlado e totalmente configurável e criar imagens idênticas deste ambiente para serem distribuídas e replicadas em diferentes máquinas para fins de produção do cliente final.

{% hint style="info" %}
Para compreender melhor como o Docker funciona é importante conhecer sua terminologia. Ao decorrer do documento você se deparará diversas vezes com estes termos então é importante ter uma ideia teórica para aprender a identificá-los e entendê-los no final.
{% endhint %}

{% tabs %}
{% tab title="Container" %}
Um _container, ou contêiner,_ é uma instância em tempo de execução de uma imagem Docker.

Um container Docker consiste em:

* Uma **imagem Docker**
* Um **ambiente de execução**
* Um conjunto padrão de **instruções**

O conceito é emprestado dos contêineres de transporte marítimo, que definem um padrão para enviar mercadorias globalmente. O Docker define um padrão para enviar software.

{% hint style="info" %}
**Se você está familiarizado com o conceito de Máquina Virtual o **_**container**_** tem suas semelhanças, pois também conseguem isolar seu ambiente de execução do restante do sistema operacional.**
{% endhint %}
{% endtab %}

{% tab title="Images" %}
_Images_, ou imagens, são a base dos containers. Uma imagem é uma coleção ordenada de alterações no sistema de arquivos raiz e os parâmetros de execução correspondentes para uso dentro de um ambiente de execução de _containers_. Uma imagem geralmente contém uma união de sistemas de arquivos em **camadas** empilhados uns sobre os outros.
{% endtab %}

{% tab title="Layer" %}
Em uma imagem, uma _layer_, ou camada, é uma modificação na imagem, representada por uma instrução no Dockerfile. As camadas são aplicadas em sequência à imagem base para criar a imagem final. Quando uma imagem é atualizada ou reconstruída, apenas as camadas que mudaram precisam ser atualizadas, e as camadas que não foram alteradas são armazenadas em cache localmente. Isso faz parte do motivo pelo qual as imagens Docker são tão rápidas e leves. Os tamanhos de cada camada somam-se para formar o tamanho da imagem final.
{% endtab %}
{% endtabs %}

