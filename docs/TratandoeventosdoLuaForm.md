# Tratando eventos do Lua Form

# Eventos do Lua Form

&nbsp;

Um evento é um acontecimento específico de alguma tag. É possível definir códigos LUA (veja [A linguagem de programação LUA](<AlinguagemdeprogramacaoLUA.md>)) que serão executados toda vez que determinado evento ocorrer em uma tag\!

&nbsp;

A maioria das tags/controles do Lua Form disparam eventos, mas cada uma possui seu próprio conjunto de eventos. Você deve consultar a documentação\!

&nbsp;

# Manipulando eventos

Existem duas maneiras de manipular eventos do Lua Form:

* &nbsp;
  * Associando uma única linha de código ao evento;
  * Usando a [tag event](<Tagevent.md>) para associar várias linhas de códigos ao evento.

&nbsp;

**Importante**: Não deixe de ler as [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

&nbsp;

## Modo 1 - Associando uma única linha de código ao evento.

Esta é a forma mais simples de manipular eventos, porém não é possível associar um código de mais de 1 linha aos eventos por este modo.&nbsp;

&nbsp;

Dado um evento de nome NOME\_EVENTO de uma tag de nome NOME\_TAG, você pode associar um código Lua assim:

&nbsp;

| **\<NOME\_TAG** NOME\_EVENTO="\<CODIGO\_LUA\_DE\_UMA\_LINHA\>"/\> |
| --- |


&nbsp;

&nbsp;

### Modo 1, Exemplo 1 - OnClick de button

&nbsp;

A[ tag button](<Tagbutton.md>) possui o evento "onClick".&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste""\>                  **\<button** text="Meu Botão" onClick="showMessage('Cliquei no botão');"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem121.png>)

&nbsp;

### Modo 1, Exemplo 2 - OnMouseEnter e OnMouseLeave de button

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<button** name="btnMeuBotao" text="Meu Botão" left="20" top="20" width="200"                         onMouseEnter="self.btnMeuBotao.text = 'Mouse dentro do botão'"                         onMouseLeave="self.btnMeuBotao.text = 'Meu Botão'"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem122.png>)&nbsp; ----\> ![Image](<lib/NewItem123.png>) ----\> ![Image](<lib/NewItem122.png>)

&nbsp;

### Modo 1, Exemplo 3 - Definindo função e a chamando no evento OnClick de button

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<script\>**                 local function exibirMensagem()                                 local texto = "";&nbsp;                         for i = 1, 5, 1 do                                 texto = texto .. "Linha " .. i .. "\\n";                         end;                                                showMessage(texto);                 end;         **\</script\>**          **\<button** name="btnMeuBotao" text="Meu Botão" onClick="exibirMensagem()"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

&nbsp;

![Image](<lib/NewItem124.png>)

&nbsp;

Foi usada a [Tag script](<Tagscript.md>) neste exemplo.&nbsp;

&nbsp;

## Modo 2 - Usando a tag event para manipular eventos.

Saiba como usar a tag event e exemplos em: [Tag event.](<Tagevent.md>)


***
_Created with the Personal Edition of HelpNDoc: [Create help files for the Qt Help Framework](<https://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework>)_
