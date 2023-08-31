# Tag style

# Tag style

Esta tag especial serve para definir um estilo em cascata, muito semelhante ao CSS no HTML. Um estilo em cascata é um bloco de códigos especiais que aplica valores à propriedades de 1 ou mais controles de uma vez só, em cascata.

É especialmente útil para evitar retrabalho e para separar o formato do conteúdo principal do Lua Form.

&nbsp;

**Importante**: A sintaxe do estilo em cascata é muito semelhante ao do CSS, porém as propriedades disponíveis são diferentes..

&nbsp;

## Características

A tag **style** não possui nenhum atributo/propriedade e seu corpo contém o código do estilo em cascata.

&nbsp;

## Sintaxe

A tag **style** possui uma sintaxe muito parecida com o CSS e seu conteúdo consiste de uma lista de regras. Cada regra ou conjunto de regras consiste de um ou mais seletores e um bloco de declaração. Uma declaração de bloco é composta por uma lista de declarações entre chaves. Cada declaração em si é uma propriedade, dois pontos (:), um valor, então um ponto e vírgula (;).

&nbsp;

Exemplo que resume as regras acima:

&nbsp;

| seletor1 \[, seletor2, ...\] { &nbsp; propriedade1: valor;&nbsp; \[propriedade2: valor2; &nbsp; ...\] } |
| --- |


&nbsp;

### Seletores

Um seletor é uma regra genérica que define à quais tags/componentes o estilo será aplicado, e ele pode as seguintes aparências:

&nbsp;

| **Seletor** | Exemplo | Descrição |
| --- | --- | --- |
| **.class** | .TituloAtributo | O estilo será aplicado a todas as tags que possuam atributo "class" equivalente a "TituloAtributo".&nbsp; Exemplo de tag que receberia o estilo em cascata: \<label text="Olá Mundo" class="TituloAtributo"/\> &nbsp; |
| **\#nome** | \#edtNome | O estilo será aplicado à tag cujo atributo "name" seja igual a "edtNome"&nbsp; Exemplo de tag que receberia o estilo em cascata: \<edit name="edtNome" text="Campo de text"/\>&nbsp; |
| **\*** | \* | O estilo será aplicado a todas as tags.&nbsp; |
| **tagName** | label | O estilo é aplicado a todas as tags "tagName", neste exemplo, todos os labels.&nbsp; Exemplo de tag que receberia este estilo em cascata: \<label text="Olá mundo"/\>&nbsp; |
| **tagName.class** | layout.PainelAtributo | O estilo é aplicado a todas as tags "layou" cujo atributo "class" seja "PainelAtributo" |


&nbsp;

&nbsp;

Além disso, através da combinação dos seletores acima, é possível definir um seletor composto que analisa onde a tag está. Exemplos:

&nbsp;

| **Seletor** | Exemplo | Descrição |
| --- | --- | --- |
| **.class tagName** | .PainelAtributo label | O estilo será aplicado a todos as "label" que estão dentro de alguma tag que contenha o atributo "class" equivalente a "PainelAtributo"&nbsp; Exemplo:&nbsp; \<layout class="PainelAtributo"\>&nbsp; &nbsp; \<label text="Label de dentro"/\> \</layout\> &nbsp; \<label text="Label de fora"/\>&nbsp; Neste caso, o label de dentro receberá o estilo, porém o label de fora não.&nbsp; |
| **tagName tagName** | layout label | O estilo será aplicada a todos "labels" que estão dentro de algum "layout" &nbsp; |
| **.class .class** | .PainelAtributo .TituloAtributo | O estilo será aplicado a todas as tags que possuam atributo "class" igual a "TituloAtributo" que estão dentro de alguma tag que possuam "class" igual a "PainelAtributo";&nbsp; |
| **tagName tagName tagName** | layout layout label | O estilo será aplicado a todos "labels" que estão dentro de um "layout" que por sua vez estão dentro de outro "layout".&nbsp; |
| **etc....** | &nbsp; | &nbsp; |


&nbsp;

&nbsp;

É possível definir múltiplos seletores a um único bloco de estilo utilizando vírgula, exemplo:

&nbsp;

| .TituloAtributo, .TituloPericia, .TituloEquipamento {         fontSize: 18;         **width**: 200; } |
| --- |


&nbsp;

"fontSize: 18" e "width: 200" serão aplicados a todas as tags cuja propriedade "class" seja "TituloAtributo", "TituloPericia" e "TituloEquipamento".

&nbsp;

### Propriedades

As propriedades disponíveis são aquelas que a tag disponibiliza. Confira a documentação da TAG.&nbsp;

&nbsp;

Importante: O conjunto de propriedades é diferente daquelas que você pode usar em CSS do HTML.

&nbsp;

## Exemplos

### Exemplo 1 - Aplicando uma cor de fonte e alinhamento à todos labels de um lua form.

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<style\>**                 label {                         fontColor: lime;                         horzTextAlign: center;                         vertTextAlign: center;&nbsp;               }         **\</style\>**          **\<layout** left="20" top="20" width="100" height="100"**\>**                 **\<label** align="top" text="Label 1"**/\>**                 **\<label** align="top" text="Label 4"**/\>**                 **\<label** align="top" text="Label 5"**/\>**                 **\<label** align="top" text="Label 6"**/\>**                 **\<label** align="top" text="Label 7"**/\>**         **\</layout\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem109.png>)

&nbsp;

### Exemplo 2 - Aplicando uma cor e negrito à tags de uma determinada class

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<style\>**                 .Titulo {                         fontColor: lime;                         fontStyle: bold;                 }         **\</style\>**          **\<layout** left="20" top="20" width="100" height="100"**\>**                 **\<label** class="Titulo" align="top" text="Label 1"**/\>**                 **\<label** align="top" text="Label 4"**/\>**                                 **\<label** class="Titulo" align="top" text="Label 5"**/\>**                 **\<label** align="top" text="Label 6"**/\>**                                 **\<label** class="Titulo" align="top" text="Label 7"**/\>**                 **\<label** align="top" text="Label 8"**/\>**         **\</layout\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem110.png>)

&nbsp;

&nbsp;

### Exemplo 3 - (Avançado) Uma mini ficha, usando edits, labels, layouts e styles.

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


***
_Created with the Personal Edition of HelpNDoc: [Ensure High-Quality Documentation with HelpNDoc's Hyperlink and Library Item Reports](<https://www.helpndoc.com/feature-tour/advanced-project-analyzer/>)_
