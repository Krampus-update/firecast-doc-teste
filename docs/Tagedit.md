# Tag edit

# Tag EDIT

A tag/componente **edit** representa uma caixa de texto na interface. Um ótimo controle para permitir a entrada de dados\!

&nbsp;

## Herança

O **edit** possui todas as características de uma tag de texto. Veja:

* [Características de todas as tags de textos](<Caracteristicasdetodasastagsdete.md>)
* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, a tag **EDIT** também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **textPrompt** | String | \<string vazio\> | Um texto que é exibido quando o edit está vazio. Normalmente é usado para orientar o usuário qual informação ele deve preencher.&nbsp; Exemplo: "Preencha com seu nome"&nbsp; |
| **transparent** | Boolean | false | Quando True, as bordas e o fundo do edit não serão exibidas, mostrando apenas o texto conteúdo e o cursor de digitação.&nbsp; |
| **isPasswordEdit** | Boolean | false | Quando true, o edit conterá uma senha e os caracteres do texto serão exibidos como um caractere coringa.&nbsp; |
| **readOnly** | Boolean | false | Quando true, o edit não permite o usuário alterar seu conteúdo (somente leitura).&nbsp; |
| **type** | Enumerado: "text" "number" "float" | "text" | Define que tipo de dados o usuário pode digitar neste edit.&nbsp; "text" - Não há restrições e o usuário pode digitar qualquer coisa.&nbsp; "number" - O usuário pode digitar um valor numérico inteiro. Veja também as propriedades [min](<Tagedit.md#propriedade%20min>) e [max](<Tagedit.md#Propriedade%20max>) do edit. A propriedade "keyboardType" é automaticamente alterada para "numberPad" se ela estiver como "default" ou "alphabet".&nbsp; "float" - O usuário pode digitar um valor numérico de ponto flutuante (números reais, "com vírgula")&nbsp; |
| **min** | Double | \-2147483648 | Quando o atributo "type" for igual a "number" ou "float", define qual o menor valor numérico que este Edit deve aceitar.&nbsp; |
| **max** | Double | &#50;147483647 | Quando o atributo "type" for igual a "number" ou "float", define qual o maior valor numérico que este Edit deve aceitar.&nbsp; |
| **decimalPlaces** | Integer | &#50; | Quando o atributo "type" for igual a "float", define quantas casas decimais pode ter o número digitado pelo usuário.&nbsp; |
| **keyboardType** | Enumerado: "default" "numbersAndPunctuation" "numberPad" "phonePad" "alphabet" "url" "email" | "default" | Quando um teclado virtual for exibido (como aquele nos smartphones e tablets), qual é o layout preferencial de teclado para este conteúdo?&nbsp; "default" e "alphabet": Um teclado alfanumérico padrão.&nbsp; "numbersAndPunctuation": Um teclado para entrada de números de símbolos de pontuação.&nbsp; "numberPad": Um teclado com apenas números.&nbsp; "phonePad": Um teclado para entrada de número telefônico.&nbsp; "url": Um teclado para preencher uma URL da internet.&nbsp; "email": Um teclado para preencher endereços de e-mail.&nbsp; |
| **enterKeyType** | Enumerado: "default" "done" "go" "next" "search" "send"&nbsp; | "default" | Quando um teclado virtual for exibido (como aqueles nos smartphones e tablets), este atributo define o ícone que aparece na tecla enter.&nbsp; "default" - sem tratamento especial.&nbsp; Observação importante: Esta propriedade **apenas** muda a aparência do botão ENTER. Caso queira dar uma funcionalidade ao enter, trate o evento [onKeyDown](<Caracteristicasdetodasastagsvisu.md#Evento%20OnKeyDown>) verificando se event.keyCode == 13&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o edit passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **frameRegion** | String | \<string vazio\> | Considerando que o componente/tag pai possui um frame (ver [Frames](<Frames.md>)), ao definir o valor desta propriedade, a posição e tamanho deste controle é automaticamente calculada para se encaixar na Região do Frame de mesmo nome.&nbsp; Veja [Frames e Regiões](<FrameseRegioes.md>)&nbsp; |
| **asNumber** | Double | &#48;.0 | Contém o texto do edit como um número de ponto flutuante (número real). Se o texto do edit não for um número real válido, a propriedade contém 0.&nbsp; |


&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando o conteúdo do edit é alterado.&nbsp; |
| **onUserChange** | Este evento é disparado quando o valor do campo do objeto Nodo associado (ver atributo "field") for alterado porque o usuário alterou o conteúdo do edit.&nbsp; Importante: Este evento é disparado APENAS se o atributo "field" estiver preenchido corretamente e se a alteração de valor ocorrer neste edit mediante ação do usuário.&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

## Exemplos:

### Exemplo 1 - Edit simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**          **\<edit** left="10" top="10"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem46.png>)

&nbsp;

### Exemplo 2 - Edit transparente

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**          **\<edit** left="10" top="10" transparent="true"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem47.png>)

&nbsp;

### Exemplo 3 - Edit que lê e salva dados no NodeDatabase

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**          **\<edit** left="10" top="10" field="Destreza" width="250"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem48.png>)

&nbsp;

Veja também:

* [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)
* [NodeDatabase](<NodeDatabase.md>)

&nbsp;

### Exemplo 4 - (Avançado) Uma mini ficha, usando edits, labels, layouts e styles para evitar retrabalho.

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**          **\<style\>**                 layout.LayoutCampo {                         width: 64;                         align: left;                         margins: {left=2, right=2};                 }                               layout.LayoutCampo edit {                         height:30;                         horzTextAlign: center;                         fontSize: 20;                         align: top;                 }                               layout.LayoutCampo label {                         align: top;                         horzTextAlign: center;                         vertTextAlign: leading;                         autoSize: true;                 }                       **\</style\>**                         **\<layout** left="10" top="10" width="200" height="64"**\>**                   **\<layout** class="LayoutCampo"**\>**                         **\<edit** field="combate.armadura"**/\>**                         **\<label** text="Armadura"**/\>**                                **\</layout\>**                                 **\<layout** class="LayoutCampo"**\>**                         **\<edit** field="saude.pontosDeVida"**/\>**                         **\<label** text="Pontos de Vida"**/\>**                          **\</layout\>**                                               **\<layout** class="LayoutCampo"**\>**                         **\<edit** field="equipamentos.carga"**/\>**                         **\<label** text="Carga (kg)"**/\>**                              **\</layout\>**                               **\</layout\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem49.png>)

&nbsp;

Neste exemplo, os atributos dos edits, labels e layouts foram definidos por Estilo em Cascata pela tag **style**.

&nbsp;

Foram definidos 3 blocos de estilos em cascata:

* Um com seletor "layout.LayoutCampo" (aplicado a todas as tags **layout** de class "**LayoutCampo**")
* Um com seletor "layout.LayoutCampo edit" (aplicado a todas as tags **edit** que estão dentro de uma tag **layout** de class "**LayoutCampo**")
* Um com seletor "layout.LayoutCampo label" (aplicado a todas as tags **label** que estão dentro de uma tag **layout** de class "**LayoutCampo**")

&nbsp;

&nbsp;

Veja também:

[Tag STYLE](<Tagstyle.md>)

[Tag LABEL](<Taglabel.md>)

[Tag LAYOUT](<Taglayout.md>)

&nbsp;

### Exemplo 5 - (Avançado) O mesmo do exemplo 4, porém feito com tags TEMPLATES

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                **\<template** name="LayoutUmCampo"**\>**                 **\<layout** width="64" align="left" margins="{left=2, right=2}"**\>**                         **\<edit** field="$(campo)" height="30" horzTextAlign="center" fontSize="20" align="top"**/\>**&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **\<label** text="$(titulo)" align="top" horzTextAlign="center" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; vertTextAlign="leading" autoSize="true"**/\>** &nbsp;               **\</layout\>**         **\</template\>**&nbsp;         **\<layout** left="10" top="10" width="200" height="64"**\>**                   **\<LayoutUmCampo** campo="combate.armadura" titulo="Armadura"**/\>**                 **\<LayoutUmCampo** campo="saude.pontosDeVida" titulo="Pontos de Vida"**/\>**                 **\<LayoutUmCampo** campo="equipamentos.carga" titulo="Carga (kg)"**/\>**                                 **\</layout\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem49.png>)

&nbsp;

Veja também:

[Tag TEMPLATE](<Tagtemplate.md>)

[Tag LABEL](<Taglabel.md>)

[Tag LAYOUT](<Taglayout.md>)

***
_Created with the Personal Edition of HelpNDoc: [Make Documentation Review a Breeze with HelpNDoc's Advanced Project Analyzer](<https://www.helpndoc.com/feature-tour/advanced-project-analyzer/>)_
