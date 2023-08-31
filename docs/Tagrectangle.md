# Tag rectangle

# Tag RECTANGLE

&nbsp;

A tag/componente **rectangle** representa um retângulo na interface o qual você pode personalizar cores, bordas e outros aspectos da forma.

&nbsp;

## Herança

O **rectangle** possui **todas** as características de um controle shape/forma.&nbsp;

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
| **corners** | Conjunto de: "topLeft" "topRight" "bottomLeft" "bottomRight"&nbsp; | "topLeft topRight bottomLeft bottomRight" | Identifica quais quinas do controle serão customizadas pela propriedade "cornerType"&nbsp; Exemplos: Apenas as duas quinas superiores: "topLeft topRight" Apenas as duas quinas da esquerda: "topLeft bottomLeft" Todas as quinas: "topLeft topRight bottomLeft bottomRight" Nenhuma quina: "" |
| **cornerType** | Enumerado: "round" "bevel" "innerRound" "innerLine" | "round" | Especifica o tipo de formato que as quinas deste retângulo terão.&nbsp; Você deve especificar valores das propriedades "xradius" e "yradius" para o formato das quinas serem visíveis.&nbsp; Veja o [Exemplo 3](<Tagrectangle.md#Exemplo%203>) para mais detalhes. |
| **sides** | Conjunto de: "top" "left" "bottom" "right" | "top left bottom right" | Define quais bordas serão desenhadas na interface.&nbsp; Exemplos: Apenas a borda superior: "top" Apenas as bordas laterais: "left right" Todas as bordas: "top left bottom right" Nenhuma borda: "" |
| **xradius** | Float | &#48;.0 | Define a "largura" do efeito das quinas (propriedade "cornerType""&nbsp; Veja o [Exemplo 3](<Tagrectangle.md#Exemplo%203>) para mais detalhes. |
| **yradius** | Float | &#48;.0 | Define a "altura" do efeito das quinas (propriedade "cornerType""&nbsp; Veja o&nbsp; [Exemplo 3](<Tagrectangle.md#Exemplo%203>) para mais detalhes. |


&nbsp;

## Exemplos

### Exemplo 1 - Retângulo simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<rectangle** left="20" top="20" width="200" height="200" color="yellow"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem58.png>)

&nbsp;

### Exemplo 2 - Retângulo com bordas simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**               **\<rectangle** left="20" top="20" width="200" height="200" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; color="black" strokeColor="red" strokeSize="5"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem59.png>)

&nbsp;

&nbsp;

### Exemplo 3 - Retângulo com quinas variadas

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<rectangle** left="20" top="20" width="200" height="200"                    color="yellow" strokeColor="red" strokeSize="5"                    xradius="25" yradius="25" cornerType="round"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

&nbsp;

|  ![Image](<lib/NewItem61.png>) cornerType="round"&nbsp; |  ![Image](<lib/NewItem62.png>) cornerType="bevel"&nbsp; |
| --- | :---: |
|  ![Image](<lib/NewItem64.png>) cornerType="innerRound" |  ![Image](<lib/NewItem65.png>) cornerType="innerLine" |


&nbsp;

&nbsp;

### Exemplo 4 - Retângulo com quinas variadas e sem bordas

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<rectangle** left="20" top="20" width="200" height="200"                    color="yellow" xradius="25" yradius="25" cornerType="round"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

|  ![Image](<lib/NewItem66.png>) cornerType="round"&nbsp; |  ![Image](<lib/NewItem67.png>) cornerType="bevel"&nbsp; |
| --- | :---: |
|  ![Image](<lib/NewItem68.png>) cornerType="innerRound" |  ![Image](<lib/NewItem69.png>) cornerType="innerLine" |



***
_Created with the Personal Edition of HelpNDoc: [Create HTML Help, DOC, PDF and print manuals from 1 single source](<https://www.helpndoc.com/help-authoring-tool>)_
