# Tag textEditor

# Tag textEditor

A tag/componente **textEditor** representa uma caixa de texto de múltiplas linhas. Um ótimo controle para permitir a entrada de dados texto com quebra de linhas.

&nbsp;

## Herança

O **textEditor** possui todas as características de uma tag de texto. Veja:

* [Características de todas as tags de textos](<Caracteristicasdetodasastagsdete.md>)
* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, a tag **textEditor** também possui as seguintes características:

&nbsp;

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **readOnly** | Boolean | false | Quando true, o textEditor não permite o usuário alterar seu conteúdo (somente leitura). |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o textEditor passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>) |
| **transparent** | Boolean | false | Quando True, as bordas e o fundo do textEditor não serão exibidas, mostrando apenas o texto conteúdo e o cursor de digitação. |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando o conteúdo do textEditor é alterado. |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos:

### Exemplo 1 - Um textEditor simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                 **\<textEditor** left="10" top="10" width="150" height="250" text="Este é um textEditor\\n\\ncom multiplas linhas"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem51.png>)

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [HelpNDoc's Project Analyzer: Incredible documentation assistant](<https://www.helpndoc.com/feature-tour/advanced-project-analyzer/>)_
