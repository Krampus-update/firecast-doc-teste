# Tag tab

# Tag TAB

A tag/componente **tab** representa uma aba dentro de um grupo de abas (Ver [Tag tabControl](<TagtabControl.md>)). Excelente para dividir controles em duas ou mais abas.

&nbsp;

**IMPORTANTE**: Para usar abas, você **deve** usar uma [Tag tabControl.](<TagtabControl.md>)

&nbsp;

## Herança

O **tab** possui todas as características de uma tag visual. Veja:

* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

&nbsp;

## Características

Além das características herdadas, a tag **tab** também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **text ou title** | string | \<string vazio\> | Representa o título da aba. |


&nbsp;

&nbsp;

### Métodos

É possível invocar métodos dos controles usando código LUA.

| **Método** | Descrição |
| --- | --- |
| **tab:activate()**&nbsp; | Ativa a aba no tabControl.&nbsp; |


## Exemplos

### Exemplo 1 - Uma aba simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<tabControl** left="20" top="20"**\>**                 **\<tab** title="Minha aba"**\>**                 **\</tab\>**         **\</tabControl\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem52.png>)

&nbsp;

### Exemplo 2 - Duas abas com conteúdos distintos

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                **\<tabControl** left="20" top="20" width="250"**\>**                 **\<tab** title="Primeira Aba"**\>**                         **\<label** text="Olá Mundo, texto na primeira aba" align="client"                                vertTextAlign="center" horzTextAlign="center"**/\>**                 **\</tab\>**                                 **\<tab** title="Segunda Aba"**\>**                         **\<edit** text="Edit na segunda aba" width="200" left="25" top="10"**/\>**                 **\</tab\>**         **\</tabControl\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem53.png>) &nbsp; &nbsp; &nbsp; ![Image](<lib/NewItem55.png>)

&nbsp;

Observação: Foram usadas neste exemplo a [Tag label](<Taglabel.md>) e a [Tag edit](<Tagedit.md>)

***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Convert Your Word Doc to an eBook: A Step-by-Step Guide](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
