# Biblioteca Firecast

# Biblioteca Firecast

A biblioteca firecast contém funções relacionadas às mesas, personagens, envio de mensagens, rolagem de dados, etc..

Todas as funções estão contidas na table/variável "Firecast" da unidade "firecast.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "firecast.lua"* require("firecast.lua");    *-- Agora é possível acessar as funções da biblioteca* Firecast.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca Firecast

&nbsp;

| **function** Firecast.asyncOpenUserNDB(name\[, options\]) |
| --- |


&nbsp;

Asynchronously open a per-user [NodeDatabase](<NodeDatabase.md>) that is physically stored in the Firecast server.

&nbsp;

Arguments:

* &nbsp;
  * name - A string identifying which remote user NodeDatabase should be opened
  * (OPTIONAL) options - A Lua table describing additional settings that may contain:
    * create - a boolean. If **true**, the NodeDatabase can be created if it does not exist. Default: **false**
    * skipLoad - a boolean. If **true**, the returned Promise will be resolved before the load process is finished. If **true**, you will receive a “Loading node” instead of a “Loaded node”. Default: **false**

&nbsp;

Return:

* &nbsp;
  * a [Promise](<Promiseobject.md>) of a [Node Object](<ObjetoNodo.md>). As default behavior, the Promise will be resolved after all data is downloaded and available to be used.

&nbsp;

Remarks:

* &nbsp;
  * The content of NodeDatabases opened by this function is stored separately per-user. Each user will have their own copy of the NodeDatabase identified by the “name” argument

&nbsp;

Example:

&nbsp;

1. local promise = Firecast.asyncOpenUserNDB("exampleNodeDatabase", {create=true});
1.  
1. promise:thenDo(
1.     function(node)
1.         *-- This function will be called when/if the *
1.         *-- load completes. The first argument, *
1.         *-- "node", contains the root node of the opened nodedatabase*
1.     end,
1.    &nbsp;
1.     function(errorMsg)
1.         *-- This function will be called when/if the *
1.         *-- load fails. The first argument, *
1.         *-- "errorMsg", contains the message explaining why*
1.         *-- it was not possible to open the nodeDatabase*
1.     end);

&nbsp;

&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.getMesas() |
| --- |


&nbsp;

Retorna a lista de [objetos mesas](<ObjetoMesa.md>) representando as mesas em que o usuário está no momento.

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um arranjo de [objeto mesa](<ObjetoMesa.md>), isto é, uma tabela lua indexada de 1 a N.

&nbsp;

&nbsp;

Exemplo - Exibindo uma mensagem contendo o nome e o sistema de todas as mesas em que o usuário está:\
&nbsp;

| **local** mesas = Firecast.getMesas(); **local** msg = "";  **for** i = 1, #mesas, 1 **do**         **local** objMesa = mesas\[i\];               msg = msg .. objMesa.nome .. " (" .. objMesa.sistema .. ")**\\n**"; **end**;  showMessage(msg); |
| --- |


&nbsp;

&nbsp;

| **function** Firecast.findMesa(codigoInterno) |
| --- |


&nbsp;

Dado o código interno de uma mesa, localiza o [objeto mesa](<ObjetoMesa.md>) de código interno correspondente.

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um [objeto mesa](<ObjetoMesa.md>) ou **nil** caso não encontre.

&nbsp;

&nbsp;

| **function** Firecast.interpretarRolagem(stringDaRolagem) |
| --- |


&nbsp;

Dado uma cadeia de caracteres representando uma rolagem de dados (Exemplos: "1d20 + 5", "1d20 + 1d10 - 5", etc..), retorna um [objeto rolagem](<ObjetoRolagem.md>) que contém as informações sobre a mesma.

&nbsp;

Parâmetros:

* &nbsp;
  * stringDaRolagem - cadeia de caracteres que deseja interpretar como um objeto rolagem.

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um [Objeto Rolagem](<ObjetoRolagem.md>) contendo a interpretação.

&nbsp;

Observação:

* &nbsp;
  * Se stringDaRolagem não possuir uma cadeia de caracteres válida, o novo objeto rolagem ainda será retornado, porém vazio.

&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.getRoomOf(object) |
| --- |


&nbsp;

Dado um objeto qualquer, a função tenta determinar à qual [objeto mesa](<ObjetoMesa.md>) ele está ligado.

&nbsp;

Parâmetros:

* &nbsp;
  * object - O objeto que deseja tentar determinar à qual objeto mesa ele pertence ou está ligado.

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um [Objeto Mesa](<ObjetoMesa.md>), caso a função consiga determinar
  * **nil**, caso a função não consiga determinar

&nbsp;

Observações:

* &nbsp;
  * Os objetos que costumam ser passados como parâmetro à esta função, são:
    * [objeto Nodo](<ObjetoNodo.md>). Se o NodeDatabase for de um personagem ou estiver ligado à uma mesa, a função retorna o objeto mesa.
    * [objeto BibliotecaItem](<ObjetoBibliotecaItem.md>). A função retorna à qual mesa o item da biblioteca pertence.
    * [objeto Personagem](<ObjetoPersonagem.md>).
    * [objeto Jogador.](<ObjetoJogador.md>)
    * [objeto Chat](<ObjetoChat.md>)
    * [objeto form](<Tagform.md>) de formType Table's Dock
    * [objeto Scene](<ObjetoScene.md>)
    * Outros objetos que possam estar ligados à alguma mesa.
  * Também é possível passar um valor numérico para esta função. Se for passado um valor numérico, esta função se comporta como a função [rrpg.findMesa.](<BibliotecaFirecast.md#função%20rrpg.findMesa>)

&nbsp;

&nbsp;

| **function** Firecast.getBibliotecaItemDe(objeto) |
| --- |


&nbsp;

Dado um objeto qualquer, a função tenta determinar à qual [objeto BibliotecaItem](<ObjetoBibliotecaItem.md>) ele está ligado.

&nbsp;

Parâmetros:

* &nbsp;
  * objeto - O objeto que deseja tentar determinar à qual objeto BibliotecaItem ele pertence ou está ligado.

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um [Objeto BibliotecaItem](<ObjetoBibliotecaItem.md>) caso a função consiga determinar
  * **nil**, caso a função não consiga determinar

&nbsp;

Observações:

* &nbsp;
  * Os objetos que costumam ser passados como parâmetro à esta função, são:
    * [objeto Nodo](<ObjetoNodo.md>). Se o NodeDatabase for de um item na biblioteca, a função retorna o objeto biblioteca item.
    * Outros objetos que possam estar ligados à biblioteca da mesa.

&nbsp;

&nbsp;

| **function** Firecast.getPersonagemDe(object) |
| --- |


&nbsp;

Dado um objeto qualquer, a função tenta determinar à qual [objeto Personagem](<ObjetoPersonagem.md>) ele está ligado.

&nbsp;

Parâmetros:

* &nbsp;
  * object - O objeto que deseja tentar determinar à qual objeto Personagem ele pertence ou está ligado.

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um [Objeto Personagem](<ObjetoPersonagem.md>) caso a função consiga determinar
  * **nil**, caso a função não consiga determinar

&nbsp;

Observações:

* &nbsp;
  * Os objetos que costumam ser passados como parâmetro à esta função, são:
    * [objeto Nodo](<ObjetoNodo.md>). Se o NodeDatabase for de um personagem, a função retorna o objeto personagem.
    * Outros objetos que possam estar ligados aos personagens da mesa.

&nbsp;

&nbsp;

| **function** Firecast.getCurrentUser() |
| --- |


&nbsp;

Retorna uma tabela contendo informações do usuário logado atualmente no Firecast.

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um tabela LUA contendo as seguintes propriedades/atributos:
    * isLogged - Boleano (true ou false) indicando se possui um usuário logado no momento.
    * login - Se o usuário tiver logado, contém uma cadeia de caracteres contendo seu login/username.
    * isGold - Booleano (true ou false) indicando se o usuário é assinante Firecast Gold
    * isGoldPlus - Booleano (true ou false) indicando se o usuário é assinante Firecast Platinum / RRPG Gold Plus
    * isRuby - Booleano (true ou false) indicando se o usuário é assinante Firecast Ruby

&nbsp;

&nbsp;

| **function** Firecast.registerChatToolButton(params) |
| --- |


&nbsp;

Registra um botão-ferramenta que será apresentado nos chats do Firecast.

&nbsp;

Parâmetros:

* &nbsp;
  * params - Uma tabela Lua contendo as seguintes propriedades do botão:
    * "hint" - Um string que será apresentado ao usuário quando ele arrastar o mouse em cima do botão.
    * "icon" - Um string contendo o endereço da imagem que será apresentada como ícone do botão.
    * "callback" - Uma função que será chamada quando o usuário clicar no botão. Seu primeiro parâmetro recebe um [objeto Chat](<ObjetoChat.md>) representado em qual chat o usuário clicou no botão.
    * (OPCIONAL) "priority" - Se quiser sugerir a ordem dos botões, informe um número em priority. Botões com prioridade maior aparecem antes dos com prioridade menor.
    * (OPCIONAL) "group" - Um string. Se quiser vários botões ficarem juntos, você pode especificar o mesmo valor em group para eles.
    * (OPCIONAL) "groupPriority" - Se quiser sugerir a ordem do grupo de botões, informe um número nesta propriedade. Grupos de botões com maior prioridade aparecem antes dos grupos com menor prioridade.

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um identificador do botão criado. Este valor pode ser usado na função [Firecast.unregisterChatToolButton](<BibliotecaFirecast.md#unregisterChatToolButton>) se quiser remover o botão.

&nbsp;

Observações:

* &nbsp;
  * O ícone informado poderá sofrer tratamento visual para se encaixar no tema do Firecast. Use ícones com transparência e cuja "sombra" seja capaz de remeter seu significado.
  * O botão só será apresentado se:
    * O usuário for assinante Gold.
    * Ou o usuário não for pagante e estiver em mesa cujo dono seja assinante Gold+/Platina.

&nbsp;

Exemplo:

|  **local** params = {}; params.hint = "This button do @@localized.text.id"; params.icon = "/icons/myIcon.png"; params.priority = 10; params.group = "myButtonGroup";   params.callback =     **function**(chat)         *-- the param "chat" contains good information to handle =)*         showMessage("User clicked the button");     **end**;     Firecast.registerChatToolButton(params);&nbsp; |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.unregisterChatToolButton(toolButtonId) |
| --- |


&nbsp;&nbsp; &nbsp;

Desregistra um botão-ferramenta de chat previamente instalado pela função [Firecast.registerChatToolButton](<BibliotecaFirecast.md#registerCharToolButton>).&nbsp;

&nbsp;

Parâmetros:

* &nbsp;
  * toolButtonId - O identificador retornado pela função [Firecast.registerChatToolButton](<BibliotecaFirecast.md#registerCharToolButton>).&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Easily create EBooks](<https://www.helpndoc.com/feature-tour>)_
