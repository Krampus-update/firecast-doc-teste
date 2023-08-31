# Orientações ao usar código LUA em um Lua Form

# Usando código LUA em um Lua Form.

&nbsp;

Você pode usar códigos LUA (veja [A linguagem de programação LUA](<AlinguagemdeprogramacaoLUA.md>)) em seus Lua Forms de 2 maneiras:

&nbsp;

* &nbsp;
  * Manipulando eventos das tags - Saiba mais como em [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>).
  * Usando a [Tag script](<Tagscript.md>).

&nbsp;

Mas para usar de forma adequada é importante você saber as características e comportamento do código LUA em um Lua Form.

&nbsp;

## &#49; - Instâncias

&nbsp;

Um Lua Form pode ser instanciado várias vezes (veja [Lua Form e Instâncias](<LuaFormeInstancias.md>)), isto é, é perfeitamente possível existir mais de 1 "cópia" de um Lua Form rodando ao mesmo tempo. Seu código deve estar apto a lidar com esta situação\!

&nbsp;

A variável "self" representa a instância do Lua Form em que o código está executado.

## &#50; - Acessando as tags/controles via programação.

&nbsp;

Cada instância do Lua Form possui sua própria "cópia viva" das tags e, se você quiser acessar uma tag/controle via programação, você precisará identificar de qual Lua Form é o controle que deseja ter acesso.

&nbsp;

Para identificar um controle do próprio Lua Form, você deve usar "self.". \
Em 99% dos casos que precisar acessar as tags via programação, você provavelmente usará "self.".

&nbsp;

Exemplo:

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<label** name="labMeuLabel" left="20" top="20" text="Meu Texto\!" **/\>**          **\<button** text="Clique" left="20" top="50"                 onClick="self.labMeuLabel.text = 'Cliquei no Botão'"**/\>** **\</form\>** |
| --- |


&nbsp;

**Importante:** Um erro ocorrerá se tentar acessar uma tag/controle sem usar "self." (ou outra forma de identificar o Lua Form).

&nbsp;

## &#51; - Declarando funções

&nbsp;

Você pode usar a [tag script](<Tagscript.md>) para declarar funções, mas você deve usar o modificador "local" nestas funções para que não haja confusão entre as diversas instâncias do Lua Form.

Não usar o modificador "local" nas declarações de funções causa confusão entre as instâncias do form, já que se trataria de uma função global a todas as instâncias.

&nbsp;

Exemplo de declaração:

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<script\>**                 local function exibirMensagem()                                 local texto = "";&nbsp;                         for i = 1, 5, 1 do                                 texto = texto .. "Linha " .. i .. "\\n";                         end;                                                showMessage(texto);                 end;         **\</script\>**          **\<button** name="btnMeuBotao" text="Meu Botão" onClick="exibirMensagem()"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

Você também pode declarar funções ligadas à instância para evitar os mesmos problemas:

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<script\>**                 function self.exibirMensagem()                         showMessage('Olá Mundo');                 end;         **\</script\>**          **\<button** onClick="self.exibirMensagem();"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

## &#52; - Acessando o Nodo do NodeDatabase associado à instância do LuaForm

Cada instância de LuaForm pode estar associada a um [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase (ver [NodeDatabase](<NodeDatabase.md>) e [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)).&nbsp;

A variável "sheet" contém este [objeto nodo](<ObjetoNodo.md>) associado e você pode usá-lo via programação.

&nbsp;

Exemplo de uso:

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<button** onClick="sheet.campoDeForca = 8;"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Streamline your documentation process with HelpNDoc's WinHelp HLP to CHM conversion feature](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
