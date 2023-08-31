# Criar uma janela acoplável de mesa

# Criar uma janela acoplável de mesa

&nbsp;

Uma janela acoplável de mesa segue os **mesmos** princípios de um modelo de ficha. A única diferença é que você deve usar "tablesDock" na propriedade "formType" da [tag Form.](<Tagform.md>)

&nbsp;

Exemplo:

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmMinhaJanelaAcoplavel" formType="tablesDock"  &nbsp; &nbsp; &nbsp; dataType="RRPG.DataTypeUnico.DaMinhaJanelaAcoplavel"    &nbsp;  title="Minha Janela Acoplável"**\>**           **\<label** text="Olá Mundo"**/\>**       ... Outras tags LFM e códigos lua.....    **\</form\>** |
| --- |


&nbsp;

&nbsp;

Agora basta compilar seu plug-in que o RRPG fará o resto =)

&nbsp;

![Image](<lib/NewItem213.png>)

&nbsp;

&nbsp;

Como dito anteriormente, janelas acopláveis seguem os mesmos princípios de modelos de fichas e salvam/carregam dados em um [NodeDatabase](<NodeDatabase.md>) da mesa. A propriedade "dataType" da tag Form serve para informar ao RRPG onde os dados devem ser salvos, e, portanto, uma vez definido, é recomendado que não seja alterado.

&nbsp;

Todos da mesa que estiverem com esta janela acoplável aberta lerão e salvarão dados em um único mesmo lugar: As mudanças no NodeDatabase serão sincronizadas com todos da mesa\!

&nbsp;

Leia também:

* &nbsp;
  * [Criando um novo projeto de plug-in](<Criandoumnovoprojetodeplugin.md>)
  * [Interfaces Visuais (Lua Forms)](<InterfacesVisuaisLuaForms.md>)
  * [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)

***
_Created with the Personal Edition of HelpNDoc: [Save time and frustration with HelpNDoc's WinHelp HLP to CHM conversion feature](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
