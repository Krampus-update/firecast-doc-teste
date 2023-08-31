# Objeto Chat

# Objeto Chat

Este objeto representa uma interface de batepapo no RRPG Firecast.

&nbsp;

## Herança

O **Objeto Chat** possui todas as características de um WrappedObject. Veja:

* [Objeto WrappedObject](<ObjetoWrappedObject.md>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, o Objeto Chat também possui as seguintes características:

&nbsp;

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **room** | [Objeto Mesa](<ObjetoMesa.md>) | (Somente leitura) Contém a mesa a qual este chat pertence.&nbsp; **Importante**: Pode ser **nil** se o chat não pertencer a uma mesa. &nbsp; |


&nbsp;

### Métodos

&nbsp;

| **Método** | Descrição |
| --- | --- |
| **chat:enviarMensagem(msg)**&nbsp; | Envia uma mensagem comum para o chat, como se o usuário a tivesse digitado.&nbsp; Parâmetros: msg - a mensagem que deseja enviar no chat.&nbsp; |
| **chat:enviarAcao(acao)**&nbsp; | Enviar uma mensagem como uma ação para o chat.&nbsp; Parâmetros: acao - a mensagem que deseja enviar no chat com formatação de ação.&nbsp; |
| **chat:enviarRisada()**&nbsp; | Enviar uma típica risada do RRPG para o chat. |
| **chat:enviarMensagemNPC(npc, msg)** | Envia uma mensagem para o chat como se um NPC estivesse falando.&nbsp; Parâmetros: npc - cadeia de caracteres contendo o nome do NPC msg - a mensagem que deseja enviar no chat.&nbsp; Observação: Apenas o mestre da mesa consegue enviar mensagens como NPC.&nbsp; |
| **chat:enviarNarracao(narracao)** | Enviar uma mensagem como narrador para o chat.&nbsp; Parâmetros: narracao - a mensagem que deseja enviar no chat com formatação de narração.&nbsp; Observação: Apenas o mestre da mesa consegue enviar narrações.&nbsp; |
| **chat:rolarDados(rolagem \[, msg, calllback\])** | Envia uma rolagem de dados para o chat.&nbsp; Parâmetros: rolagem - um [Objeto Rolagem](<ObjetoRolagem.md>) ou uma cadeia de caracteres contendo a rolagem de dados. (OPCIONAL) msg - Uma mensagem para acompanhar a rolagem de dados. (OPCIONAL) callback - Uma função que será invocada após a rolagem ser executada no chat. A função recebe no primeiro parâmetro um **NOVO** [Objeto Rolagem](<ObjetoRolagem.md>) contendo o resultado da rolagem.&nbsp; Observações: Esta função tem comportamento assíncrono. Isto é, a função retorna imediatamente e o resto do código continua sendo executado enquanto a rolagem é feita em segundo plano. Depois de algum tempo, quando o RRPG já souber o resultado, é que a função "callback" será invocada. A função callback pode não ser invocada se a rolagem não for autorizada/realizada pelo RRPG. Exemplo de situações: A mesa está moderada e o usuário não possui o modo +voz para rolar dados, a conexão com o servidor caiu antes da rolagem ser realizada, etc..&nbsp; Veja também o [exemplo 2](<ObjetoChat.md#Exemplo%202>).&nbsp; |
| **chat:escrever(texto \[, quebrarLinha, permitirSmileys\])**&nbsp; | Escreve/Imprime um texto no chat. O texto não é enviado para ninguém e só é exibido para o usuário que está usando o RRPG.&nbsp; Parâmetros: texto - cadeia de caracteres contendo o texto que deve ser impresso no chat. (OPCIONAL) quebrarLinha - Booleano indicando se o RRPG deve adicionar uma quebra de linha no chat antes de escrever o texto. Se omitido, o valor padrão true é assumido. (OPCIONAL) permitirSmileys - Booleano indicando se o RRPG deve interpretar smileys neste texto. Se omitido, o valor padrão true é assumido.&nbsp; |


&nbsp;

&nbsp;

## Exemplos

### Exemplo 1 - Uma ficha enviando um Hello World para a sua mesa.

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<button\>**                 **\<event** name="onClick"**\>**                          local minhaMesa = Firecast.getRoomOf(sheet);                         local chat = minhaMesa.chat;                                                chat:enviarMensagem("Olá mundo\!\!\!\!");                 **\</event\>**         **\</button\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

**Exemplo 2 - Uma ficha fazendo um teste (de resistência, por exemplo) e postando o resultado na mesa.**

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFTeste"**\>**         **\<script\>**                 **local** **function** realizarTesteDeResistencia()                                     *-- obter a mesa do personagem*                         **local** mesaDoPersonagem = rrpg.getMesaDe(sheet);                                                 *-- se o usuário não preencheu modificador, vamos usar o valor 0*                         sheet.modificador = sheet.modificador **or** 0;                 &nbsp;                               mesaDoPersonagem.chat:rolarDados("1d20 + " .. sheet.modificador, "Teste de Resistência",                                 **function** (rolado)                                         *-- A dificuldade do teste é 15*                                                                         **if** rolado.resultado \>= 15 **then**                                                 mesaDoPersonagem.chat:enviarMensagem("SUCESSO =) você tirou " .. rolado.resultado);                                         **else**                                                 mesaDoPersonagem.chat:enviarMensagem("FALHA =/ você tirou " .. rolado.resultado);                                         **end**;                                        &nbsp;                                 **end**);                           **end**;                        **\</script\>**          **\<button** onClick="realizarTesteDeResistencia()"**/\>** **\</form\>** |
| --- |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Streamline your documentation process with HelpNDoc's WinHelp HLP to CHM conversion feature](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
