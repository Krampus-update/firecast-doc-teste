# Tag checkBox

# Tag checkBox

A tag/componente **checkBox** representa uma caixa de marcação na interface.

&nbsp;

## Herança

O **checkBox** possui todas as características de uma tag de texto. Veja:

* [Características de todas as tags de textos](<Caracteristicasdetodasastagsdete.md>)
* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

&nbsp;

## Características

Além das características herdadas, a tag **checkBox** também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **checked** | Boolean | false | Indica se a caixa de marcação está marcada (true) ou desmarcada (false) |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o checkBox passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>) |


&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando a marcação do checkBox sofre alteração. |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos:

### Exemplo 1 - CheckBox simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                 **\<checkBox** left="10" top="20" text="Caixa de marcação"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem72.png>)&nbsp; &nbsp; ![Image](<lib/NewItem73.png>)

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Effortlessly optimize your documentation website for search engines](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
