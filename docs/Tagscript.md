# Tag script

# Tag script

Esta tag especial serve para definir um bloco de códigos LUA (veja [A linguagem de programação LUA](<AlinguagemdeprogramacaoLUA.md>)) que será executado quando uma [nova instância do Lua Form ](<LuaFormeInstancias.md>)for criada.

&nbsp;

&nbsp;

Observações:&nbsp;

* &nbsp;
  * O corpo da tag contém código de programação LUA
  * Esta tag não cria nenhum controle.
  * A ordem que a tag **script** foi definida no documento Lua Form **importa**\! O código será executado logo **após** a criação da tag/controle que está acima, porém **antes** da criação da tag/controle que está abaixo. No momento exato em que o script é executado, a variável "sheet" conterá valor **nil** e será preenchido num momento posterior#8202;**.**

&nbsp;

**Importante**: Não deixe de ler as [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

## Características

### Propriedades e atributos

Esta tag não possui propriedades e atributos.

&nbsp;

## Exemplos

### Exemplo 1 - Exibindo um "olá mundo" na hora da criação de uma instância do Lua Form

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<script\>**                 showMessage("Olá mundo");         **\</script\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

Ao criar a interface:

&nbsp;

![Image](<lib/NewItem119.png>)

&nbsp;

### Exemplo 2 - Definindo funções para serem invocadas depois

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<script\>**                 local function exibirMensagem()                         local msg = "";                                                 for i = 1, 5, 1 do                                 msg = msg .. "Linha " .. i .. "\\n";                         end;                                                 showMessage(msg);                 end;         **\</script\>**&nbsp;         **\<button** text="Meu Botão" left="20" top="20" onClick="exibirMensagem();"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem120.png>)

&nbsp;

Veja também:

* &nbsp;
  * [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Effortlessly upgrade your WinHelp HLP help files to CHM with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
