# Mensagens de Estado das Mesas

# Mensagens-Eventos a respeito do Estado das Mesas no RRPG

&nbsp;

| "MesaJoined" |
| --- |


Enviada quando alguém entrar em alguma mesa no RRPG.

&nbsp;

Parâmetros da Mensagem:

* &nbsp;
  * &nbsp;
    * room - [Objeto Mesa](<ObjetoMesa.md>) representando a mesa onde o jogador entrou.
    * me - Booleano, onde true significa que o usuário atual do RRPG foi quem entrou na mesa.
    * player - [Objeto Jogador](<ObjetoJogador.md>) representando quem entrou na mesa.

&nbsp;

&nbsp;

| "MesaParted" |
| --- |


Enviada quando alguém sair de alguma mesa do RRPG.

&nbsp;

Parâmetros da Mensagem:

* &nbsp;
  * &nbsp;
    * room - [Objeto Mesa](<ObjetoMesa.md>) representando a mesa que o jogador saiu.
    * me - Booleano, onde true significa que o usuário atual do RRPG foi quem saiu da mesa.
    * player - [Objeto Jogador](<ObjetoJogador.md>) representando quem saiu da mesa.
    * (OPCIONAL) text - Cadeia de caracteres contendo, opcionalmente, um texto deixada pelo usuário no momento da saída.
    * isKick - Booleano, onde true significa que o jogador saiu da mesa por causa de um kick.
    * (OPCIONAL) responsible - Quando "isKick" for true, este campo contem o [Objeto Jogador](<ObjetoJogador.md>) representando quem realizou o kick. Observação: Se este atributo vier **nil** durante um kick, significa que o sistema RRPG kickou o usuário.

***
_Created with the Personal Edition of HelpNDoc: [Revolutionize your documentation process with HelpNDoc's online capabilities](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
