# Biblioteca Firecast.Messaging

# Biblioteca Firecast.Messaging

A biblioteca Firecast.Messaging contém funções que tratam as notificações que o Firecast dispara para todos os plug-ins através de mensagens.

&nbsp;

Em resumo, existem 2 tipos de eventos que o SDK 3 permite o programador "tratar":

* &nbsp;
  * Eventos de tags/controles - São eventos específicos de cada controle.
  * Mensagens do Firecast - São acontecimentos que são compartilhado com todos os plugins instalados, pois podem ser de interesse de todos. Exemplos: Quando a conexão do RRPG cai, quando o usuário entra em uma nova mesa, etc..

&nbsp;

Esta biblioteca auxilia na manipulação do segundo tipo de evento descrito acima.

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "firecast.lua"* require("firecast.lua");    *-- Agora é possível acessar as funções da biblioteca* Firecast.Messaging.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca Firecast.Messaging

&nbsp;

&nbsp;

| **function** Firecast.Messaging.newReceiver(messageName, callbackFunction \[, filters\]) |
| --- |


&nbsp;

Cria e retorna um objeto que representa a "escuta" de mensagens eventos.

&nbsp;

Parâmetros:

* &nbsp;
  * messageName - uma cadeia de caracteres definindo qual mensagem-evento a escuta deve ouvir. Para saber quais mensagens você pode escutar, veja [Lista de Mensagens Eventos do Firecast](<ListadeMensagensEventosdoRRPG.md>).
  * callbackFunction - uma função que será invocada sempre que a escuta captar uma mensagem. Quando invocada, a função recebe no primeiro parâmetro uma tabela/objeto lua contendo as propriedades da mensagem. Cada mensagem-evento possui sua própria lista de atributos e você deve, portanto, consultar [Lista de Mensagens-Eventos do Firecast](<ListadeMensagensEventosdoRRPG.md>) para mais detalhes..
  * (OPCIONAL) filters - Uma tabela/objeto Lua contendo filtros que a escuta deve verificar para decidir se deve invocar "callbackFunction" ou não. Exemplo:
    * Filters= {from="Login"}. A escuta só disparará "callbackFunction" se a mensagem possuir um atributo de nome "from" com conteúdo igual a "Login".

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um objeto representando a escuta instalada ou **nil** caso falhe

&nbsp;

Observações:

* &nbsp;
  * Mantenha referência ao objeto retornado enquanto a escuta for necessária. Se o objeto for liberado da memória pelo coletor de lixo, a escuta será desinstalada automaticamente.
  * A função não falha se você informar, no parâmetro "messageName", uma identificação de mensagem não esteja na lista [Lista de Mensagens-Eventos do Firecast,](<ListadeMensagensEventosdoRRPG.md>) mas, provavelmente, a escuta nunca irá disparará a função "callbackFunction".
  * É possível cancelar a escuta de 3 maneiras:
    * Invocar a função receiverObj:disable() do objeto retornado, conforme exemplo abaixo
    * Retornar explicitamente **false** na "callbackFunction"
    * Deixar o coletor de lixo do Lua coletar o objeto, eventualmente.
  * A diferença básica entre [Firecast.Messaging.newReceiver](<BibliotecaFirecastMessaging.md#functionNewReceiver>) e [Firecast.Messaging.listen](<BibliotecaFirecastMessaging.md#função%20listen>) é a forma de gerenciar o ciclo de vida da escuta.

&nbsp;

&nbsp;

Exemplo:

| require("firecast.lua");   **local** receiverObj = Firecast.Messaging.newReceiver("SessionLost",                         **function** (msg)                                 *-- This function will be called when the Firecast connection is lost*                                 showMessage("The connect was lost\!");                         **end**);   *-- To disable the receiver:* receiverObj:disable(); *-- disable right now* receiverObj = nil;  *-- let the garbage collector disable the receiver* |
| --- |


&nbsp;

&nbsp;

|  **function** Firecast.listen(messageName, callbackFunction \[, filters\]) ou **function** Firecast.Messaging.listen(messageName, callbackFunction \[, filters\]) |
| --- |


&nbsp;

Instala uma "escuta" de mensagens eventos.

&nbsp;

Parâmetros:

* &nbsp;
  * messageName - uma cadeia de caracteres definindo qual mensagem-evento a escuta deve ouvir. Para saber quais mensagens você pode escutar, veja [Lista de Mensagens Eventos do Firecast](<ListadeMensagensEventosdoRRPG.md>).
  * callbackFunction - uma função que será invocada sempre que a escuta captar uma mensagem. Quando invocada, a função recebe no primeiro parâmetro uma tabela/objeto lua contendo as propriedades da mensagem. Cada mensagem-evento possui sua própria lista de atributos e você deve, portanto, consultar [Lista de Mensagens-Eventos do Firecast](<ListadeMensagensEventosdoRRPG.md>) para mais detalhes..
  * (OPCIONAL) filters - Uma tabela/objeto Lua contendo filtros que a escuta deve verificar para decidir se deve invocar "callbackFunction" ou não. Exemplo:
    * Filters= {from="Login"}. A escuta só disparará "callbackFunction" se a mensagem possuir um atributo de nome "from" com conteúdo igual a "Login".

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um número identificando a escuta instalada ou **nil** caso falhe. Você pode utilizar este valor na função [Firecast.Messaging.unlisten](<BibliotecaFirecastMessaging.md#função%20unlisten>) para cancelar a escuta .

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * A função não falha se você informar, no parâmetro "messageName", uma identificação de mensagem não esteja na lista [Lista de Mensagens-Eventos do Firecast,](<ListadeMensagensEventosdoRRPG.md>) mas, provavelmente, a escuta nunca irá disparará a função "callbackFunction".
  * É possível cancelar a escuta de 2 maneiras:
    * Invocar a função [Firecast.Messaging.unlisten](<BibliotecaFirecastMessaging.md#função%20unlisten>) passando o valor retornado por esta função (rrpg.messaging.listen) como parâmetro;
    * Retornar explicitamente **false** na "callbackFunction"
  * A diferença básica entre [Firecast.Messaging.newReceiver](<BibliotecaFirecastMessaging.md#functionNewReceiver>) e [Firecast.Messaging.listen](<BibliotecaFirecastMessaging.md#função%20listen>) é a forma de gerenciar o ciclo de vida da escuta.

&nbsp;

&nbsp;

Exemplo:

| require("firecast.lua");  Firecast.Messaging.listen("SessionLost",         **function** (detalhesDaMensagem)                 *-- Esta função será chamada quando a conexão do RRPG for perdida*                 showMessage("A conexão foi perdida\!");         **end**); |
| --- |


&nbsp;

&nbsp;

| **function** Firecast.listenOnce(messageName, callbackFunction \[, filters\]) ou **function** Firecast.Messaging.listenOnce(messageName, callbackFunction \[, filters\]) |
| --- |


&nbsp;

Instala uma "escuta" de mensagens eventos. O funcionamento é idêntico à da função [Firecast.Messaging.listen](<BibliotecaFirecastMessaging.md#função%20listen>), porém a escuta é automaticamente desinstalada após captar 1 mensagem.

&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.unlisten(listenerId) ou **function** Firecast.Messaging.unlisten(listenerId) |
| --- |


&nbsp;

Desinstala uma "escuta" que foi previamente instalada pela função [Firecast.Messaging.listen](<BibliotecaFirecastMessaging.md#função%20listen>) ou pela função [Firecast.Messaging.listenOnce](<BibliotecaFirecastMessaging.md#função%20listenOnce>).

&nbsp;

Parâmetros:

* &nbsp;
  * listenerId - Identificação da escuta a ser desinstalada. A identificação da escuta é retornada pela função que instala escutas ([Firecast.Messaging.listen](<BibliotecaFirecastMessaging.md#função%20listen>) ou [Firecast.Messaging.listenOnce](<BibliotecaFirecastMessaging.md#função%20listenOnce>))

&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.groupOnceListeners(listenerId1 \[, listenerId2 \[, listenerId3 \[, listenerIdN...\]\]\]) ou **function** Firecast.Messaging.groupOnceListeners(listenerId1 \[, listenerId2 \[, listenerId3 \[, listenerIdN...\]\]\]) |
| --- |


&nbsp;

Agrupa "escuta" de mensagens-eventos do tipo once (àquela que capta somente 1 mensagem). Quando OnceListeners são agrupados, a característica de se desinstalar automaticamente após receber a primeira mensagem é "expandida" para o grupo. Isto é, quando o Listener1 captar uma mensagem e se desinstalar, o Listener2, Listener3 e ListenerN são automaticamente desinstalados juntos.

&nbsp;

Esta função é especialmente útil em situações que possam resultar 2 ou mais mensagens-eventos distintas. Exemplo: O código requisitou a criação de 1 novo personagem em uma mesa... duas coisas podem acontecer: O servidor pode responder à requisição ou a conexão com o rrpg pode cair. Nesta situação, devemos instalar uma escuta "Quando o servidor responder", uma escuta "Quando a conexão cair" e agrupá-las. Note que se o servidor responder, não estaremos mais interessados se a conexão cair e vice-versa.

&nbsp;

Parâmetros:

* &nbsp;
  * listenerId1, listenerId2, listenerId3, listenerId4, listenerId5, listenerIdN... As identificações de escuta que queira agrupar. Este valor é retornado pela função [Firecast.Messaging.listenOnce](<BibliotecaFirecastMessaging.md#função%20listenOnce>).&nbsp;
    * Este é um parâmetro "vararg", isto é, você pode passar quantos valores quiser. Exemplo de chamadas válidas: Firecast.Messaging.groupOnceListeners(id1, id2) ou rrpg.messaging.groupOnceListeners(id1, id2, id3, id4, id5, id7, id8).

***
_Created with the Personal Edition of HelpNDoc: [Make your documentation accessible on any device with HelpNDoc](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
