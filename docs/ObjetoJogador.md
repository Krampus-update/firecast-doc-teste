# Objeto Jogador

# Objeto Jogador

Este objeto representa um usuário em uma mesa aberta no RRPG Firecast.

&nbsp;

Observações:

* &nbsp;
  * Se um mesmo usuário estiver em mais de 1 mesa ao mesmo tempo, existirá 1 Objeto Jogador distinto para cada mesa em que ele estiver.

&nbsp;

## Herança

O **Objeto Jogador** possui todas as características de um WrappedObject. Veja:

* [Objeto WrappedObject](<ObjetoWrappedObject.md>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, o Objeto Jogador também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **mesa** | [Objeto Mesa](<ObjetoMesa.md>) | Somente leitura, contém o [Objeto Mesa](<ObjetoMesa.md>) que representa em qual mesa este usuário está.&nbsp; |
| **login** | String | Somente leitura, contém o login do usuário.&nbsp; |
| **nick** | String | Somente leitura, contém o nick do usuário.&nbsp; |
| **avatar** | String | Somente leitura, contém a URL da imagem de seu avatar.&nbsp; |
| **capa** | String | Somente leitura, contém a URL da imagem de capa do usuário.&nbsp; |
| **isGold** | Boolean | Somente leitura, contém true se o usuário for um assinante RRPG Gold.&nbsp; |
| **isGoldPlus** | Boolean | Somente leitura, contém true se o usuário for um assinante RRPG Gold Plus.&nbsp; |
| **isRuby** | Boolean | Somente leitura, contém true se o usuário for um assinante RRPG Ruby.&nbsp; |
| **isAusente** | Boolean | Somente leitura, contém true se o usuário estiver aparentemente ausente do computador.&nbsp; |
| **isCnxDormente** | Boolean | Somente leitura, contém true se a conexão do usuário está dormente, isto é, o usuário perdeu a conexão com o RRPG e está tentando a recuperar de volta.&nbsp; |
| **isSessaoMobile** | Boolean | Somente leitura, contém true se o usuário estiver conectado usando um dispositivo móvel (celular/tablet)&nbsp; |
| **isEspectador** | Boolean | Somente leitura, contém true se o usuário está no modo Espectador na mesa.&nbsp; |
| **isJogador** | Boolean | Somente leitura, contém true se o usuário estiver com o modo +jogador na mesa.&nbsp; |
| **isMestre** | Boolean | Somente leitura, contém true se o usuário estiver com o modo +mestre na mesa.&nbsp; |
| **isJuggernaut** | Boolean | Somente leitura, contém true se o usuário estiver com o modo +juggernaut na mesa.&nbsp; |
| **isMudo** | Boolean | Somente leitura, contém true se o usuário estiver com o modo +mudo na mesa.&nbsp; |
| **isCego** | Boolean | Somente leitura, contém true se o usuário estiver com o modo +cego na mesa.&nbsp; |
| **haveVoice ou ** **haveVoz** | Boolean | Somente leitura, contém true se o usuário estiver com o modo +voz na mesa.&nbsp; |
| **codigoInterno** | Integer | Somente leitura, contém um número que identifica o jogador naquela mesa.&nbsp; |
| **personagemPrincipal** | Integer | Somente leitura, o código interno do item do personagem principal do jogador na mesa.&nbsp; Este valor é o mesmo valor da propriedade "codigoInterno" dos [objetos BibliotecaItem](<ObjetoBibliotecaItem.md>)&nbsp; O valor -1 significa que o jogador não tem personagem.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **jogador:isType(typeName)** | Retorna true se passado "jogador" como parâmetro.&nbsp; |
| **jogador:requestSetCego(cego)** | Requisita a alteração da propriedade isCego do jogador.&nbsp; Parâmetros: cego - Booleano, onde true significa colocar o modo "+cego" e false colocar o modo "-cego".&nbsp; Observações: A alteração do comportamento só ocorre após o servidor RRPG aprovar a mudança. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG.&nbsp; |
| **jogador:requestSetMudo(mudo)** | Requisita a alteração da propriedade isMudo do jogador.&nbsp; Parâmetros: mudo - Booleano, onde true significa colocar o modo "+mudo" e false colocar o modo "-mudo".&nbsp; Observações: A alteração do comportamento só ocorre após o servidor RRPG aprovar a mudança. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG.&nbsp; |
| **jogador:requestSetVoz(voz)** | Requisita a alteração da propriedade haveVoice do jogador.&nbsp; Parâmetros: voz - Booleano, onde true significa colocar o modo "+voz" e false colocar o modo "-voz".&nbsp; Observações: A alteração do comportamento só ocorre após o servidor RRPG aprovar a mudança. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG.&nbsp; |
| **jogador:requestSetJogador(isJogador)** | Requisita a alteração da propriedade isJogador do usuário.&nbsp; Parâmetros: isJogador - Booleano, onde true significa colocar o modo "+jogador" e false colocar o modo "-jogador".&nbsp; Observações: A alteração do comportamento só ocorre após o servidor RRPG aprovar a mudança. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG.&nbsp; |
| **jogador:requestKick();**&nbsp; | Requisita o kick (expulsão) do jogador da mesa.&nbsp; Observações: O kick só ocorre após o servidor RRPG aprová-lo. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG.&nbsp; |
| **jogador:requestSetBarValue(index, currentValue, maxValue)**&nbsp; | Requisita a alteração de valores em uma das barrinhas de status do jogador.&nbsp; Parâmetros: index - um número que varia de 1 a 4, indicando qual barrinha deseja-se alterar os valores. currentValue - Um número representando o novo valor atual da barrinha ou **nil** se não quiser alterar este campo. maxValue - Um número representando o novo valor máximo da barrinha ou **nil** se não quiser alterar este campo.&nbsp; Observações: A alteração só ocorre após o servidor RRPG aprová-la. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG e o dono da mesa atual não for assinante do Gold Plus.&nbsp; |
| **jogador:requestSetEditableLine(index, text)**&nbsp; | Requisita a alteração de texto de uma das linhas digitáveis do jogador.&nbsp; Parâmetros: index - um número que varia de 1 a 2, indicando de qual linha se deve alterar o texto. text - Uma cadeia de caracteres/texto contendo o novo texto que será aplicao à linha digitável especificada..&nbsp; Observações: A alteração só ocorre após o servidor RRPG aprová-la. Esta função não faz nada se o usuário do plug-in não for assinante do RRPG e o dono da mesa atual não for assinante do Gold Plus.&nbsp; |
| **jogador:getBarValue(index)** | Retorna os valores atuais de uma das barrinhas de status do jogador.&nbsp; Parâmetros: index - um número que varia de 1 a 4, indicando de qual barrinha se deseja obter informações.&nbsp; Retorno: Esta função retorna 3 valores na seguinte ordem: currentValue - Um número, valor atual da barrinha maxValue - Um número, valor máximo da barrinha percent - Um número, percentual da barrinha&nbsp; Observações: Se index indicar uma barrinha que não está ativa na mesa, os três valores retornados (currentValue, maxValue e percent) serão **nil**. Se o usuário atual não tiver permissões para ver os números da barinha (isto é, a visibilidade está protegida), currentValue e maxValue serão retornados como **nil** enquanto percent trará uma porcentagem válida.&nbsp; Exemplo: local atual, maximo, percent = player:getBarValue(1);&nbsp; |
| **jogador:getEditableLine(index)** | Retorna os o texto atual de uma das linhas digitáveis do jogador.&nbsp; Parâmetros: index - um número que varia de 1 a 2, indicando de qual linha se deseja obter informações.&nbsp; Retorno: Uma cadeia de caracteres/texto contendo o que está escrito na linha digitável especificada.&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Uma ficha que exibe uma mensagem com a lista de Login e Nick dos jogadores que estão na mesa

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<button\>**                 **\<event** name="onClick"**\>** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **local** msg = "";                         **local** mesaDoPersonagem = rrpg.getMesaDe(sheet);                         **local** jogadores = mesaDoPersonagem.jogadores;                                         **for** i = 1, #jogadores, 1 **do**                                 **local** objJogador = jogadores\[i\];                                 msg = msg .. objJogador.nick .. " (" .. objJogador.login .. ")**\\n**";                         **end**;                                                showMessage(msg);                 **\</event\>**         **\</button\>** **\</form\>** |
| --- |


&nbsp;

&nbsp; &nbsp; \
Neste exemplo, também foram usados:

* &nbsp;
  * função [rrpg.GetMesaDe](<BibliotecaFirecast.md#rrpg.getMesas>)
  * propriedade [jogadores do Objeto Mesa](<ObjetoMesa.md#propriedade%20jogadores>)

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Reach: Convert Your Word Document to an ePub or Kindle eBook](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
