# Mensagens de Chat

# Mensagens-Eventos a respeito de Chat no RRPG

&nbsp;

| "ChatMessage" |
| --- |


Enviada quando uma mensagem de chat for recebida ou enviada.

&nbsp;

Parâmetros da Mensagem:

* &nbsp;
  * &nbsp;
    * chat - [Objeto Chat](<ObjetoChat.md>) onde a mensagem foi recebida ou enviada.
    * mine - Booleano, onde true significa que a mensagem foi enviada pelo usuário atual do rrpg e false significa uma mensagem enviada por outro usuário.
    * type - Contém o tipo da mensagem e pode ser um dos seguintes valores:
      * "standard" - Uma mensagem de texto normal
      * "asNarrator"&nbsp; - Uma mensagem de texto como Narrador.
      * "asNPC" - Uma mensagem de texto como NPC
      * "action" - Uma mensagem de texto ação (/me)
      * "laugh" - Uma risada do RRPG (/rir)
      * "dice" - Uma rolagem de dados
    * content - Cadeia de caracteres contendo o texto principal da mensagem. Se tipo for "dice", contém a mensagem adicional que acompanha a rolagem.
    * (OPCIONAL) npc - Se o tipo da mensagem for "asNPC", contém o nome do NPC da mensagem.
    * (OPCIONAL) roll - Se o tipo da mensagem for "dice", contém o [Objeto Rolagem](<ObjetoRolagem.md>) com detalhes da rolagem feita.
    * (OPCIONAL) room - Se a mensagem foi enviada em um chat ligado a uma mesa, contém o [Objeto Mesa](<ObjetoMesa.md>) da mesma.
    * (OPCIONAL) player - Se a mensagem foi enviada em um chat ligado a uma mesa, contém o [Objeto Jogador](<ObjetoJogador.md>) de quem enviou a mensagem.
    * (OPCIONAL) pvtPlayer - Se a mensagem foi enviada em uma janela PVT, contém o [Objeto Jogador](<ObjetoJogador.md>) do PVT aberto.

&nbsp;

Observações:

* &nbsp;
  * &nbsp;
    * Se o usuário do RRPG for um usuário Silver, esta mensagem-evento não é enviada. Esta mensagem-evento só é enviada se o usuário for um assinante do RRPG.

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

| "HandleChatCommand" |
| --- |


Mensagem enviada quando o usuário digitar um comando no chat que não é conhecido pelo RRPG, dando a chance ao plug-in de tratá-lo.

&nbsp;

Por, exemplo, quando o usuário digitar no chat: "/atacar orbe de fogo", onde "atacar" é o comando e "orbe de fogo" é o parâmetro.

&nbsp;

Parâmetros da Mensagem:

* &nbsp;
  * &nbsp;
    * command - Cadeia de caracteres contendo o nome do comando que o usuário digitou.
    * parameter - Cadeia de caracteres contendo o parâmetro do comando.
    * chat - [Objeto Chat](<ObjetoChat.md>) onde o comando foi digitado.
    * (OPCIONAL) room - Se o comando for digitado em um chat ligado a uma mesa, contém o [Objeto Mesa](<ObjetoMesa.md>) da mesma, senão contém **nil**.
    * (OPCIONAL) player - Se o comando for digitado em uma janela PVT, contém o [Objeto Jogador](<ObjetoJogador.md>) com quem o usuário está conversando, senão contém **nil**.

&nbsp;

Retorno:

* &nbsp;
  * &nbsp;
    * "response = {handled = true}" para sinalizar ao RRPG que o comando foi devidamente tratado e que não precisa mais continuar sua busca por alguém que trate este comando.

&nbsp;

Observações:

* &nbsp;
  * &nbsp;
    * Se o usuário do RRPG for um usuário Silver, esta mensagem não é enviada. Esta mensagem-evento só é enviada se o usuário for um assinante do RRPG.
    * Recomendamos que trate também a mensagem evento ["ListChatCommands](<MensagensdeChat.md#%22ListChatCommands%22>)"

&nbsp;

Exemplo: Tratando o comando /versao

| rrpg.messaging.listen("HandleChatCommand",         **function** (message)                 **if** message.command == "versao" **then**                         *-- Tratar o comando /versão*                         message.chat:enviarMensagem("A Minha versão é 1.0");  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; message.chat:escrever("Este texto é só para o usuário");                                                 *-- Sinalizar ao RRPG que o comando foi tratado com sucesso*                         message.response = {handled = true};                 **end**;         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

| "ListChatCommands" |
| --- |


Mensagem enviada quando o usuário digitar "/help" ou "/?" no chat, permitindo o plug-in informar ao usuário a existência de comandos suportados.

&nbsp;

Parâmetros:

* &nbsp;
  * &nbsp;
    * chat - [Objeto Chat](<ObjetoChat.md>) onde o help será exibido.
    * (OPCIONAL) room - Se o help for ser exibido em um chat ligado a uma mesa, contém o [Objeto Mesa](<ObjetoMesa.md>) da mesma, senão contém **nil**.
    * (OPCIONAL) player - Se o help for ser exibido em uma janela PVT, contém o [Objeto Jogador](<ObjetoJogador.md>) com quem o usuário está conversando, senão contém **nil**.

&nbsp;

Retorno:

* &nbsp;
  * &nbsp;
    * response = Um arranjo de tabelas, onde cada tabela representa um comando e possui as seguintes propriedades:
      * command - Uma cadeia de caracteres contendo o comando , exemplo: "/meuComando"
      * description - Uma cadeia de caracteres contendo a descrição do comando, exemplo: "Faz isso, isso e aquilo"

&nbsp;

Observações:

* &nbsp;
  * &nbsp;
    * Este evento ocorre apenas para informar ao usuário quais comandos o plug-in possui, tornando necessário também tratara mensagem-evento ["HandleChatCommand"](<MensagensdeChat.md#HandleChatCommand>) se quiser fazer o comando realmente funcionar.
    * Se o usuário do RRPG for um usuário Silver, esta mensagem não é enviada. Esta mensagem-evento só é enviada se o usuário for um assinante do RRPG.

&nbsp;

&nbsp;

Exemplo 1: Informando, ao RRPG, a existência do comando /versao

| rrpg.messaging.listen("ListChatCommands",         **function**(message)                 message.response = {{command="/versao", description="Mostra a versão do plug-in"}};         **end**); |
| --- |


&nbsp;

&nbsp;

Exemplo 2:&nbsp; Informando, ao RRPG, vários comandos:

| rrpg.messaging.listen("ListChatCommands",         **function**(message)                 message.response = {{command="/comando1", description="Este comando faz uma coisa"},                                     {command="/comando2", description="Este comando faz duas coisas"},                                     {command="/comando3", description="Este comando faz tres coisas"}};         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

| "HandleChatTextInput" |
| --- |


Evento enviado quando o usuário confirma o envio de um comando/mensagem para um chat, dando oportunidade para o plug-in alterar ou ajustar o texto de entrada antes que seja processado pelo RRPG.

&nbsp;

Parâmetros da Mensagem:

* &nbsp;
  * &nbsp;
    * chat - [Objeto Chat](<ObjetoChat.md>) onde a mensagem será enviada.
    * text - Cadeia de caracteres contendo o texto de entrada que o usuário digitou.
    * isCommand - True se o usuário informou um texto para um comando do RRPG (aqueles que começam com o caracter "/").
    * (OPCIONAL) room - Se a mensagem estiver prestes a ser enviada a um chat ligado a uma mesa, contém o [Objeto Mesa](<ObjetoMesa.md>) da mesma.
    * (OPCIONAL) pvtPlayer - Se a mensagem estiver prestes a ser enviada em uma janela PVT, contém o [Objeto Jogador](<ObjetoJogador.md>) do PVT aberto.

&nbsp;

Retorno:

* &nbsp;
  * &nbsp;
    * Se o plug-in quiser substituir o texto por outro, o programador deverá atribuir "message.response = {newText = \<\<novo texto que será utilizado\>\>}" para sinalizar ao RRPG que o texto de entrada deve ser substítuido pelo conteudo de newText.

&nbsp;

Alerta:

* &nbsp;
  * &nbsp;
    * Tenha consciência do parametro "message.isCommand" desta mensagem\! Se o usuário digitar um comando (por exemplo "/nick NovoNick"), nem toda substituíção de texto deve ser feita, ou deve ser feita de forma consciente para não atrapalhar a experiência do usuário com o programa\!

&nbsp;

Observações:

* &nbsp;
  * &nbsp;
    * O RRPG apenas envia esta mensagem-evento se uma das duas seguintes condições forem satisfeitas:
      * O usuário logado é um assinante pago do RRPG.
      * O usuário logado não é assinante pago do RRPG, a mensagem está prestes a ser enviada em uma mesa onde o criador é Gold Plus.

&nbsp;

&nbsp;

Exemplo: Um plug-in que substitui o texto "CA" por "Categoria de Armadura" nos textos digitados pelo usuário.

&nbsp;

|  RRPG.listen('HandleChatTextInput',     **function**(message)           message.response =             {newText = string.gsub(message.text, "CA", "Categoria de Armadura") };     **end**);&nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Experience the Power and Simplicity of HelpNDoc's User Interface](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
