# Tag import

# Tag import

Com a&nbsp; tag **import**, o programador pode importar/incluir um outro documento XML ao Lua Form, acarretando na substituição da tag pelo conteúdo do arquivo especificado.

&nbsp;

É especialmente útil para:

* &nbsp;
  * Organizar o documento Lua form. Exemplo: Quando o arquivo ".lfm" ficar grande, é interessante dividir ele em partes menores, cada parte em seu documento XML separado.
  * Reaproveitar código. Exemplo: Se você tiver [templates](<Tagtemplate.md>) ou [styles](<Tagstyle.md>) que queira reaproveitar em outros Lua Forms, você pode criar um documento XML que contenha apenas o que queira reaproveitar e o importar nos Lua Forms.

&nbsp;

## Características

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **file** | String | \<Não há valor padrão\> | Endereço de um arquivo XML.&nbsp; Este endereço é relativo à localização do documento atual. Portanto, se o outro arquivo XML estiver na mesma pasta, você só precisa informar o nome dele. &nbsp; Exemplo: "MeuDocumento.xml" |


&nbsp;

## Exemplos

### Exemplo 1 - Importação simples

&nbsp;

| **Arquivo “ficha.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<import** file="OutroArquivo.xml"**/\>** **\</form\>**&nbsp; |


&nbsp;

&nbsp;

| **Arquivo “OutroArquivo.xml”** |
| --- |
|  **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<layout** width="100" height="100" top="20" left="20"**\>**                 **\<label** align="client" horzTextAlign="center" text="Estou em outro documento"**/\>** **\</layout\>**&nbsp; |


&nbsp;

![Image](<lib/NewItem117.png>)

&nbsp;

### Exemplo 2 - Importação de várias tags usando a Tag group

&nbsp;

Usando a [Tag group](<Taggroup.md>) conseguimos importar um grupo de tags que está em outro documento XML.

&nbsp;

&nbsp;

| **Arquivo “ficha.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<import** file="OutroArquivo.xml"**/\>**                **\<MinhaTag** titulo="Meu Botão"**/\>** **\</form\>**&nbsp; |


&nbsp;

&nbsp;

| **Arquivo “OutroArquivo.xml”** |
| --- |
|  **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<group\>**         **\<style\>**                 label {                         fontColor: lime;                 }         **\</style\>**                **\<template** name="MinhaTag"**\>**                 **\<button** left="20" top="120" text="$(titulo)"**/\>**         **\</template\>**          **\<layout** width="100" height="100" top="20" left="20"**\>**                         **\<label** align="client" horzTextAlign="center" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; text="Estou em outro documento"**/\>**         **\</layout\>** **\</group\>**&nbsp; |


&nbsp;

![Image](<lib/NewItem118.png>)

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Reach: Convert Your Word Document to an ePub or Kindle eBook](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
