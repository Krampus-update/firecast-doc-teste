# Posição e Tamanho dos Controles

## Posição e Tamanho dos Controles

Toda tag/controle visual possui uma localização expressa com um par de coordenadas *left* e *top*, e duas dimensões, expressas como *width* e *height* (largura e altura), uma geometria que lembra um retângulo. A unidade destes atributos é o “ponto lógico” (Veja [Ponto Lógico vs Pixel](<PontoLogicovsPixel.md>)).

&nbsp;

A posição de cada controle é relativa à posição de seus controles/tags pais.

&nbsp;

&nbsp; &nbsp; Exemplo:

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**&nbsp;         **\<rectangle** left="20" top="30" color="white" width="300" height="300"**\>** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **\<rectangle**  left="20" top="30" color="green" width="200" height="200"**\>**                         **\<rectangle** left="0" top="40" color="red" width="50"**/\>**                 **\</rectangle\>**         **\</rectangle\>** **\</form\>**&nbsp; |
| --- |


&nbsp;

O exemplo contém 3 retângulos: Um vermelho, um verde e um branco. O form é pai do retângulo branco, que é pai do retângulo verde, que por sua vez, é pai do vermelho.

&nbsp;

![Image](<lib/NewItem19.png>)

&nbsp;

A posição top final e absoluta do quadrado vermelho é 100, pois é a soma das posições top relativas (40 + 30 + 30).


***
_Created with the Personal Edition of HelpNDoc: [Say Goodbye to Documentation Headaches with a Help Authoring Tool](<https://www.helpndoc.com/news-and-articles/2022-09-27-why-use-a-help-authoring-tool-instead-of-microsoft-word-to-produce-high-quality-documentation/>)_
