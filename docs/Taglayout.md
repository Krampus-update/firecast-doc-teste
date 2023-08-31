# Tag layout

# Tag LAYOUT

&nbsp;

A tag/componente **layout** representa um componente visual “invisível”. Ele não apresenta nada na tela e é usado apenas para organizar outros componentes visuais.

As principais características do **layout** são:

* Não apresentam nada na tela, são transparentes.
* São ótimos para organizar e/ou agrupar outros componentes visuais.&nbsp;
  * Exemplo: Você pode adicionar 10 outros componentes dentro de um **layout** e alterar a posição de todos, ao mesmo tempo, alterando a apenas posição do layout.
* As tags/controles que estão dentro de **layout** mas visualmente fora de seus limites (largura e altura do layout) não são desenhadas na tela.

&nbsp;

## Herança

O **layout** possui **todas** as características de um controle qualquer. Veja [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

&nbsp;

## Características

Além das características herdadas, o **layout** possui também as seguintes características:

### Propriedades e atributos da tag LAYOUT

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **frameStyle** | String | \<string vazio\> | Aplica um frame a este layout. A string é o caminho de um arquivo frame.&nbsp; Veja [Frames](<Frames.md>) |
| **frameRegion** | String | \<string vazio\> | Considerando que o componente/tag pai possui um frame (ver [Frames](<Frames.md>)), ao definir o valor desta propriedade, a posição e tamanho deste controle é automaticamente calculada para se encaixar na Região do Frame de mesmo nome.&nbsp; Veja [Frames e Regiões](<FrameseRegioes.md>) |


&nbsp;

## Exemplos

### Exemplo 1 - Uso simples de Layout

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**         **\<layout** left="60" top="50" width="300" height="300"**\>**                 **\<button** left="0" top="0" text="Botão 1"**/\>**                 **\<button** left="0" top="32" text="Botão 2"**/\>**         **\</layout\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem20.png>)&nbsp;

&nbsp;

&nbsp;

O layout é um componente invisível, mas sua geometria neste exemplo é:

![Image](<lib/NewItem21.png>)

&nbsp;

### Exemplo 2 - Uso de layouts aninhados e alinhamento de controles

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**         **\<layout** left="60" top="50" width="250" height="300"**\>**                 **\<layout** align="left" width="125"**\>**                         **\<edit** align="top"**/\>**                         **\<edit** align="top"**/\>**                         **\<edit** align="top"**/\>**                 **\</layout\>**     &nbsp;                 **\<layout** align="right" width="125"**\>**                         **\<edit** align="top"**/\>**                         **\<edit** align="top"**/\>**                         **\<edit** align="top"**/\>**                 **\</layout\>**         **\</layout\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem22.png>)

&nbsp;

O layout é um componente invisível, mas sua geometria neste exemplo é:

![Image](<lib/NewItem23.png>)


***
_Created with the Personal Edition of HelpNDoc: [Revolutionize your documentation process with HelpNDoc's online capabilities](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
