# Tag group

# Tag group

Com a&nbsp; tag **group**, o programador pode agrupar outras tags. Esta tag não faz nada além disso, não afeta a interface visual e nem a interpretação do Lua Form.

Não há propriedades e nem atributos.

&nbsp;

É especialmente útil para usar com a [tag import](<Tagimport.md>). Honestamente, sua única utilidade é essa hehehe =)

&nbsp;

## Exemplos

### Exemplo 1 - Importação de várias tags usando a Tag group

&nbsp;

Usando a [Tag import](<Tagimport.md>) conseguimos importar um grupo de tags que está em outro documento XML.

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

***
_Created with the Personal Edition of HelpNDoc: [Modernize your help files with HelpNDoc's WinHelp HLP to CHM conversion tool](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
