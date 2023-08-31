# Biblioteca Firecast.Requests

# Biblioteca Firecast.Requests

A biblioteca rrpg.requests contém funções que solicitam determinadas ações ao RRPG, como, por exemplo, criar itens na biblioteca da mesa, obter informações de perfil de um usuário, etc..

&nbsp;

| *\-- Primeiro, é necessário usar a unidade "rrpgRequests.lua"* require("rrpgRequests.lua");    *-- Agora é possível acessar as funções da biblioteca* Firecast.Requests.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca Firecast.Requests

&nbsp;

| **function** Firecast.Requests.criarPersonagem(itemPai, nome, dataType, visivelATodos, dono &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \[, successCallback \[, failureCallback\]\]) |
| --- |


&nbsp;

Requisita a criação de um novo personagem na mesa.

&nbsp;

Parâmetros:

* &nbsp;
  * itemPai - Um [objeto BibliotecaItem](<ObjetoBibliotecaItem.md>) identificando onde o personagem deverá ser criado.
  * nome - Uma cadeia de caracteres identificando o nome do novo personagem.
  * dataType - Uma cadeia de caracteres identificando o dataType do personagem. dataType é uma identificação única de um template de ficha.
  * visivelATodos - true se o personagem deve ser visível a todos ou false se for ser visível apenas ao mestre e ao dono da ficha.
  * dono - Um [objeto Jogador](<ObjetoJogador.md>) identificando quem será o dono do personagem, ou **nil** se for um NPC.
  * (OPCIONAL) successCallback - Uma função que será chamada quando a criação do personagem for bem sucedida.
  * (OPCIONAL) failureCallback - Uma função que será chamada quando a criação do personagem **não** for bem sucedida. Uma cadeia de caracteres contendo o motivo da falha é passada como primeiro parâmetro da função.

&nbsp;

&nbsp;

Retorno:

&nbsp; &nbsp; A função não retorna nada. Para saber se a criação do personagem foi bem sucedida, utilize os parâmetros "successCallback' e "failureCallback".

&nbsp;

Observações:

* &nbsp;
  * Por motivo de segurança, apenas plug-ins autorizados podem alterar a estrutura da biblioteca das mesas.
  * A criação de personagens é um processo assíncrono. Sendo assim, a função não aguarda uma resposta de sucesso/falha e as funções successCallback e failureCallback serão invocadas mais tarde com o resultado.
  * Não é possível criar um personagem cujo dataType não está instalado no RRPG do usuário. Para obter uma lista de dataTypes que o usuário possui instalado, utilize a função [Firecast.Plugins.getInstaledDataTypes](<BibliotecaFirecastPlugins.md#função%20getInstaledDataTypes>)

***
_Created with the Personal Edition of HelpNDoc: [Streamline your documentation process with HelpNDoc's HTML5 template](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
