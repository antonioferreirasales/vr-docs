---
icon: wrench
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

# Instalação e configuração inicial

O VRXubuntu, por padrão, já vem instalado com algumas aplicações e scripts necessárias para um servidor Linux do sistema VR, especialmente para o Service Manager.

#### Aplicativos e ferramentas instaladas

{% tabs %}
{% tab title="Java 8" %}
O Java 8 já vem instalado, pronto para executar as aplicações .jar do sistema como VRMaster, VRFrente, etc.\


<figure><img src="../.gitbook/assets/image (13) (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Anydesk" %}
O aplicativo Anydesk para acesso remoto já vem instalado no sistema operacional e seu atalho fica na área de trabalho, porém é recomendado algumas configurações para facilitar o suporte diário.

1.  Permitir a solicitação de acesso a qualquer momento para que a mensagem de **Aceitar** e **Recusar** a conexão sempre aparece na tela para o cliente.\


    <figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>
2.  Adicionar o Anydesk na inicialização do sistema.

    <figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption><p>Procure por Sessão e inicialização.</p></figcaption></figure>

    <figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption><p>Adicione um aplicativo com o comando "anydesk".</p></figcaption></figure>

    <figure><img src="../.gitbook/assets/image (12) (1).png" alt=""><figcaption><p>O aplicativo deve ter como gatilho o login.</p></figcaption></figure>
{% endtab %}

{% tab title="Docker" %}
O Docker CLI e o Docker Compose já estão instalados também, não sendo necessário instalar mais nenhum utilitário da ferramenta.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="VRConfig" %}
O VRConfig é um script bash para executar comandos de funções selecionáveis por terminal.&#x20;

<figure><img src="../.gitbook/assets/image (15).png" alt="" width="563"><figcaption><p>Script VRConfig aberto.</p></figcaption></figure>

Porém, esse script não está atualizado assim que o sistema operacional é instalado. Então é recomendado baixar um script atualizado direto do repositório. Para isso, abra um terminal (por padrão ele abrirá na pasta home do usuário logado e é lá que o baixaremos e executaremos) e execute o seguinte script:

```bash
curl https://storage.googleapis.com/linux-pdv/gbardini/util/sm/atalhos.sh -o atalhos.sh
chmod +x atalhos.sh
./atalhos.sh
```
{% endtab %}

{% tab title="VRUtil" %}
Um utilitário da VR para conectar a máquina a pasta compartilhada do servidor para criar atalhos de aplicações jar.&#x20;

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption><p>VRUtil no canto inferior direito.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption><p>Clique com o botão esquerdo para abrir as opções.</p></figcaption></figure>
{% endtab %}
{% endtabs %}

## Instalação do Service Manager e Service Container pelo script

{% hint style="warning" %}
Antes de seguir com a instalação, confirme com o cliente a senha do usuário logado na máquina, pois será necessário executar comandos com permissões elevadas e para isso é necessário autenticar com a senha.\
Padrões de senha da VR: vrserver, vr123456, vrsoftw@re.
{% endhint %}

1. O primeiro passo é abrir o terminal na pasta home do usuário. Por padrão, o terminal já abrirá neste exato diretório, mas você pode confirmar com os comandos:

```bash
echo $USER #para retornar o nome do usuário atual
pwd #para retornar o diretório atual do terminal
```

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption><p>A esquerda, em verde, você pode identificar usuário@nomeDaMáquina.</p></figcaption></figure>

2. Confirmando seu diretório atual, você pode seguir com os próximos 3 comandos para, respectivamente, baixar, dar permissões e executar o script. Para executar o script é necessário inserir a senha do usuário logado.

```bash
curl https://storage.googleapis.com/linux-pdv/gbardini/util/sm/atalhos.sh -o atalhos.sh
chmod +x atalhos.sh
./atalhos.sh
```

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption><p>É necessário digitar o número da opção desejada e apertar Enter. Caso encerre por acidente o script, rode apenas ./atalhos.sh para executar novamente.</p></figcaption></figure>

3.  Ao iniciar o script, digite **2** que corresponde a opção “Service Manager” e aperte a tecla _Enter_ para seguir.&#x20;

    <figure><img src="../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption><p>Escolha a opção Service Manager no menu de funções.</p></figcaption></figure>


4.  Digite o número da lista que corresponde a versão do VRMaster do cliente.

    <figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption><p>Geralmente 4.2. Em caso de dúvidas confirmar no servidor de aplicativos.</p></figcaption></figure>
5.  Na pergunta seguinte, escolha a opção 1, pois estamos instalando pela primeira vez e não apenas atualizando.\


    <figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p>Uma vez instalado, a opção 2 pode ser utilizada para atualizar as aplicações.</p></figcaption></figure>
6. Insira cada informação solicitada pelo script para gerar os arquivos de configuração corretos (_vr.properties_ e _docker-compose-sm-sc.yml_).

{% tabs %}
{% tab title="IP do Ubuntu" %}
É o IP interno da máquina que você está instalando agora.

```bash
ifconfig #para identificar o IP da máquina
```

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>Script do lado esquerdo, novo terminal no lado direito para conferir o IP.</p></figcaption></figure>

Ao inserir o IP da máquina, o script faz um teste de conexão e, se correta, a mensagem seguinte é retornada: _O endereço informado corresponde ao IP do Ubuntu, continuando com o script_.
{% endtab %}

{% tab title="Informações do Banco de Dadas" %}
Insira o restante das informações conforme o banco de dados do cliente. Para confirmar as informações, você pode conferir o vr.properties do servidor de aplicativos do cliente e copiar.\


<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>Na direita, o vr.properties aberto com as propriedades correspondes às perguntas do script marcadas por ordenação numérica.</p></figcaption></figure>

{% hint style="danger" %}
Não há um teste no script para confirmar a conexão com o banco de dados a partir dos dados fornecidos. Em casos de erros é necessário editar os arquivos manualmente depois.
{% endhint %}
{% endtab %}
{% endtabs %}

7. Acompanhe a criação da estrutura de pastas e download dos arquivos e aplicações.

{% tabs %}
{% tab title="Pastas" %}
<figure><img src="../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption><p>Limpa a pasta .vr e cria a estrutura de pastas novamente.</p></figcaption></figure>
{% endtab %}

{% tab title="Arquivos de configuração" %}
<figure><img src="../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption><p>vr.properties, script de particionamento e arquivos yml.</p></figcaption></figure>
{% endtab %}

{% tab title="Service Container" %}
<div align="center">

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption><p>Download das últimas versões disponíveis no link do script.</p></figcaption></figure>

</div>

Os arquivos serão baixados na pasta \~/.vr/servicecontainer/service/

<figure><img src="../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption><p>Arquivos das aplicações que rodarão no Service Container.</p></figcaption></figure>
{% endtab %}

{% tab title="Service Manager" %}
<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption><p>Download das últimas versões disponíveis no link do script.</p></figcaption></figure>

Os arquivos serão baixados na pasta \~/.vr/servicemanager/service/

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption><p>Arquivos das aplicações que serão executadas pelo Service Manager.</p></figcaption></figure>
{% endtab %}
{% endtabs %}

8. Após o script finalizar, suba os _containers_ das aplicações através do arquivo de configuração docker-compose-sm-sc.yml.

```bash
docker-compose -f ~/.vr/docker-compose-sm-sc.yml up -d
```

{% embed url="https://vimeo.com/1015688764?share=copy" %}
