# Tag radioButton

# Tag radioButton

A tag/componente **radioButton** representa uma caixa de marcação na interface que, quando usada em grupo, permite apenas uma esteja marcada por vez.

&nbsp;

## Herança

O **radioButton** possui todas as características de uma tag de texto. Veja:

* [Características de todas as tags de textos](<Caracteristicasdetodasastagsdete.md>)
* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

&nbsp;

## Características

Além das características herdadas, a tag **radioButton** também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **checked** | Boolean | false | Indica se a caixa de marcação está marcada (true) ou desmarcada (false)&nbsp; |
| **groupName** | String | \<string vazio\> | Um texto qualquer usado pelo programador programador para especificar grupos de radioButton.&nbsp; Quando um radioButton é marcado, todos os outros radioButtons que possuírem o mesmo valor de groupName são desmarcados.&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o radioButton passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Ao preencher este campo, é recomendado que você também preencha o atributo "fieldValue" abaixo.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **fieldValue** | String | \<string contendo o mesmo name do controle/tag\> | Quando usado com o NodeDatabase através do "field", este atributo contém o valor que é salvo no campo do NodeDatabase quando o radioButton estiver selecionado.&nbsp; Na prática, existirão vários radioButtons ligados ao **mesmo** field, porém cada um com um "fieldValue" diferente.&nbsp; |


&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando a marcação do radioButton sofre alteração. |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos:

### Exemplo 1 - RadioButtons simples

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFTeste"**\>**                 **\<radioButton** text="Força" groupName="grupoDeRadios1" field="atributoBasico" fieldValue="for"&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; top="10" left="20"**/\>**                                         **\<radioButton** text="Destreza" groupName="grupoDeRadios1" field="atributoBasico" fieldValue="des"&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; top="32" left="20" **/\>**                                          **\<radioButton** text="Inteligência" groupName="grupoDeRadios1" field="atributoBasico" fieldValue="int"&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; top="54" left="20"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem186.png>)&nbsp; ![Image](<lib/NewItem187.png>)&nbsp; ![Image](<lib/NewItem188.png>)

&nbsp;

&nbsp;

&nbsp;&nbsp; 
***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Reach: Convert Your Word Document to an ePub or Kindle eBook](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
