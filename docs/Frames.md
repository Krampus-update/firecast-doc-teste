# Frames

# Frames

Algumas tags/controles do Lua Form permitem o programador definir um frame, isto é, uma moldura para ser exibida na interface visual.

Um frame é uma aparência personalizada que se adapta dinamicamente ao tamanho do controle.

&nbsp;

## Ainda não entendi o que é um frame.

Veja estes exemplos para entender melhor\!\
&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<layout** align="client" frameStyle="/frames/frame1.xml"  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; margins="{left=10, top=10, right=10, bottom=10}"**\>**&nbsp;                 **\<label** align="client" horzTextAlign="center" text="Conteudo do Layout"**/\>**                        **\</layout\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem129.png>)![Image](<lib/NewItem130.png>)![Image](<lib/NewItem131.png>)

&nbsp;

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<layout** align="client" frameStyle="/frames/meuOutroFrame.xml"  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; margins="{left=10, top=10, right=10, bottom=10}"**\>**&nbsp;                 **\<label** align="client" horzTextAlign="center" text="Conteudo do Layout"**/\>**                        **\</layout\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem132.png>)![Image](<lib/NewItem133.png>)![Image](<lib/NewItem134.png>)

&nbsp;

&nbsp;

A [tag layout](<Taglayout.md>) por si só não apresenta nada na interface, mas ao aplica um frame à ela, passou a apresentar estas bordas e backgrounds "legais".

&nbsp;

## O que eu preencho na propriedade "frameStyle"?

&nbsp;

Você deve preencher com o caminho de um arquivo [XML](<DocumentosXML.md>) que contém a definição de um frame. Saiba mais sobre este arquivo lendo [Arquivo de Definição de Frame.](<ArquivodeDefinicaodeFrame.md>)

&nbsp;

## Exemplos

Veja alguns exemplos em [Exemplos de frames](<Exemplosdeframes.md>).

***
_Created with the Personal Edition of HelpNDoc: [Benefits of a Help Authoring Tool](<https://www.helpauthoringsoftware.com>)_
