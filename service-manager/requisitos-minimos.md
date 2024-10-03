---
icon: power-off
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

# Requisitos Mínimos

{% hint style="info" %}
As informações desse artigo tiveram como fonte a páginal da Wiki oficial da VR ([Requisitos Mínimos](https://wiki.vrsoft.com.br/wiki/index.php/Requisitos\_M%C3%ADnimos) e [VRUbuntu](https://wiki.vrsoft.com.br/wiki/index.php/VRUbuntu\_Instalacao)) e orientações internas. Em caso de informações desatualizadas ou links indisponíveis neste documento, abra uma _issue_.
{% endhint %}

## Sistema Operacional

Todas as aplicações do ecossistema VR que rodam em Docker precisam ser instaladas e configuradas no servidor do Service Manager que deve ser hospedado por uma **máquina física** com o [VRUbuntu ](https://wiki.vrsoft.com.br/wiki/index.php/VRUbuntu\_Instalacao)como único sistema operacional. A virtualização não é recomendada pelo suporte salvo os servidores especializados de nuvem homologados pela VR, tal como Skyone.

| Especificações recomendadas  | Service Manager                                                                                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| CPU                          | i5 (4ª geração +) ou equivalente                                                                                                                   |
| Memória RAM                  | 8 GB                                                                                                                                               |
| Versão (sistema operacional) | [VRXubuntu 22.04 LTS (distribuição Linux VRSoftware)](https://storage.googleapis.com/linux-pdv/gbardini/util/sm/vrxubuntu-22.04-desktop-amd64.iso) |
| HD padrão SATA (6Gb/s)       | 200 GB (mínimo)                                                                                                                                    |

{% hint style="warning" %}
O servidor do Service Manager precisa estar se comunicando com o servidor de banco de dados para funcionar.  No cenário de máquinas físicas, é recomendado que ambos os servidores permaneçam na mesma loja sob a mesma rede interna. \
&#x20;\
A formatação da máquina e sua configuração de rede é de responsabilidade do TI da loja.
{% endhint %}
