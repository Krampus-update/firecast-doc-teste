# Tag button

# Tag button

A tag/componente **button** representa um botão na interface. Excelente para executar uma tarefa quando o usuário optar por ela\!

&nbsp;

## Herança

O **button possui** todas as características de uma tag de texto. Veja:

* [Características de todas as tags de textos](<Caracteristicasdetodasastagsdete.md>)
* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, a tag **button** também possui as seguintes características:

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onClick** | Este evento é invocado quando ocorre um click com o botão esquerdo do mouse no controle, ou quando ocorre um “tap touch” no controle. |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos:

&nbsp;

### Exemplo 1 - Um botão simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** fame="frmFichaTeste"**\>** &nbsp;       **\<button** left="40" top="40" text="Eu sou um botão" width="150"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem24.png>)

&nbsp;

### Exemplo 2 - Tratando o evento onClick (estilo 1)

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**          **\<button** left="40" top="40" text="Clique" onClick="showMessage('olá mundo\!');"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem25.png>)

&nbsp;

Veja também [Tratando eventos do Lua Form.](<TratandoeventosdoLuaForm.md>)

&nbsp;

### Exemplo 3 - Tratando o evento onClick (estilo 2)

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**          **\<button** left="40" top="40" text="Clique"**\>**                 **\<event** name="onClick"**\>**                         local texto = "";                                               for i = 1, 5, 1 do                                 texto = texto .. "Linha " .. i .. "\\n";                         end;                                                showMessage(texto);                 **\</event\>**         **\</button\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem26.png>)

&nbsp;

Veja também [Tratando eventos do Lua Form.](<TratandoeventosdoLuaForm.md>)

***
_Created with the Personal Edition of HelpNDoc: [Produce Kindle eBooks easily](<https://www.helpndoc.com/feature-tour/create-ebooks-for-amazon-kindle>)_
