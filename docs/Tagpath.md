# Tag path

# Tag PATH

&nbsp;

A tag/componente **path** representa uma forma geométrica/shape totalmente personalizada e vetorial. Todas as formas geométricas básicas podem ser criadas usando esta tag.

&nbsp;

## Herança

O **path** possui **todas** as características de um controle shape/forma.&nbsp;

&nbsp;

Veja&nbsp;

* &nbsp;
  * [Características de tags shapes](<Caracteristicasdetagsshapes.md>)
  * [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

&nbsp;

## Características

Além das características herdadas, o **rectangle** possui também as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **data ou pathData** | String | \<String Vazio\> | Define a forma vetorial do path. Este texto deve estar no mesmo padrão do path do SVG e do XAML.&nbsp; |
| **mode ou wrapMode** | Enumerado: "fit" "original" "stretch" "tile" | "fit" | Define como a forma será desenhada na interface.&nbsp; "fit" - a forma vai ser redimensionada proporcionalmente para ocupar o tamanho da tag path.&nbsp; "original" - a forma será desenhada sem nenhum tratamento de tamanho e posição.&nbsp; "stretch" - a forma vai ser esticada para ocupar todo o tamanho da tag path.&nbsp; "tile" - a forma será desenhada várias vezes para ocupar o tamanho da tag path.&nbsp; |
| **roundToPixel** | Boolean | false | Quando true, as posições do shape serão arredondadas para ocuparem pelo&nbsp; menos 1 pixel da tela. Esta opção pode melhorar o aspecto de alguns paths e pode piorar o aspecto de outros. Teste antes\!&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Um triângulo laranja

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**        &nbsp;         **\<path** align="client" margins="{left=10, right=10, bottom=10, top=10}"               color="orange" data="M 100 100 L 300 100 L 200 300 z"**/\>**&nbsp; **\</form\>**&nbsp; |
| --- |


&nbsp;

![Image](<lib/NewItem158.png>)

&nbsp;

&nbsp;

### Exemplo 2 - Outra forma com vários modos diferentes

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**        &nbsp;         **\<path** align="client" margins="{left=10, right=10, bottom=10, top=10}" mode="fit" color="red" data="M133,31.8c-0.6,4.3,0.3,9.7,0.3,9.7c0,0,-3.1,-2.3,-6.5,-4.3c-2,-1.1,-3.8,-3.6,-4.8,-5.5c-0.8,-1.3,-1.2,-2.3,-1.2,-2.3c-4.8,5.1,-1.7,11.1,-1.7,11.1c-7.4,-1.6,-12,0.3,-12,0.3c14,9.2,6.6,9.9,-1.5,13.8c-8.1,3.8,-8.7,8.6,-8.7,8.6c9.6,-3.2,13.5,0.9,13.5,0.9c-5.2,4.9,-0.6,12.7,-0.6,12.7c5.1,9.7,17.6,13.8,28.8,15.5c11.1,1.7,21,1,21,1l-25.6,8l-22.9,5.8c0,0,-22.8,-2.5,-31.2,-21.7C71.6,66.1,86.2,50.9,84.7,49.9c-1.4,-1,-3.2,1.1,-3.3,1.4c6.3,-18.2,25.5,-18,26.2,-19.9c0.8,-2,-3.8,-2.1,-3.8,-2.1c19.4,-6.4,29.2,2.5,29.2,2.5Z"**/\>** **\</form\>** |
| --- |


&nbsp;&nbsp; &nbsp;

|  ![Image](<lib/NewItem159.png>) mode="fit" |  ![Image](<lib/NewItem160.png>) mode="original"&nbsp; |
| --- | :---: |
|  ![Image](<lib/NewItem161.png>) mode="stretch" |  ![Image](<lib/NewItem162.png>) mode="tile" |



***
_Created with the Personal Edition of HelpNDoc: [Ensure High-Quality Documentation with HelpNDoc's Hyperlink and Library Item Reports](<https://www.helpndoc.com/feature-tour/advanced-project-analyzer/>)_
