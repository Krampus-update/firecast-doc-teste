---
title: Macros em Lua
---
# Biblioteca para Macros em Lua
## Variáveis
### parametro / parameter
`variável parametro ou variável parameter`

`variável arg[indice]`

(Não é uma função) 
Possui os parâmetros passado para a macro, onde a variável "parametro" contém a cadeia de caracteres completa e a variável "arg" contém um arranjo, onde cada item representa um argumento separado por espaço.
!!! info "Se o usuário digitar `/minhaMacro Texto de Teste`:"


    |parametro|arg[1]|arg[2]|arg[3]|
    |---|---|---|---|
    |"Texto de Teste"|Texto|de|Teste|

    === "parametro"

        A variável "parametro" conterá "Texto de Teste"

    === "parameter"

        A variável "parameter" conterá "Texto de Teste"

    === "arg[indice]"

        A variável arg[1] conterá "Texto".
        A variável arg[2] conterá "de".
        A variável arg[3] conterá "Teste".
        E \#arg contém a quantidade de argumentos.

!!! example "Exemplo: Fazer um teste de resistência parametrizado."
    ``` lua
    local dificuldade = tonumber(parametro)
    if dificuldade == nil then
        escrever("Utilize: /macro <NÚMERO>")
        return
    end

    local resultado = rolar("1d20 + 5", "Dificuldade " .. dificuldade)
    if resultado >= dificuldade then
        enviar("Passou no teste!")
    else
        enviar("Não passou no teste")
    end
    ```

---

### meuJogador / myPlayer
`variável meuJogador/ variável myPlayer`

(Não é uma função) 
[objeto Jogador](ObjetoJogador.md) representando o usuário da macro naquela mesa.

!!! example "Exemplo 1: Escrever na tela o seu próprio login."
    ``` lua
    escrever(meuJogador.login);
    ```

---
### myCharacter
`variável myCharacter`

(Não é uma função)
[Objeto Personagem](<ObjetoPersonagem.md>) representando o personagem principal do usuário naquela mesa.

!!! note "Observações:"
    * Se o jogador não possuir nenhum personagem, acessar esta variável irá causar um erro com uma mensagem informativa de que "o jogador não possui nenhum personagem" e a macro pára de executar.

!!! example "Exemplo 1: Escrever na tela o nome do seu personagem."
    ``` lua
    write(myCharacter.nome)
    ```

---
### sheet
`variável sheet`

(Não é uma função)
O [Objeto Nodo](<ObjetoNodo.md>) raiz representando o NodeDatabase/Sheet do personagem principal do usuário logado.

!!! note "Observações:"
    - Se o jogador não possuir nenhum personagem, acessar esta variável causará um erro com uma mensagem informativa de que "o jogador não possui nenhum personagem," e a macro será interrompida.
    - A execução da macro pode ser pausada até que o NodeDatabase/Ficha seja carregado pela internet.
    - O Objeto Nodo retornado é o mesmo da variável "sheet" usada para programar as fichas/lua forms.
    - As alterações feitas no objeto nodo retornado são sincronizadas normalmente, conforme as regras de permissões do Node Database.
    - Se houver algum erro ao carregar o NodeDatabase, a macro será interrompida.

!!! example "Exemplo: Exibir a estrutura dos dados armazenados na ficha e aumentar a CA em 1 se for uma ficha D&D 5."
    ```lua
    -- Exibir no chat a estrutura dos dados armazenados na ficha
    write(utils.tableToStr(sheet, true))

    -- Se for uma ficha D&D 5, aumentar a CA em 1
    sheet.CA = (tonumber(sheet.CA) or 0) + 1

    -- Exibir no chat a quantidade de PV que o personagem tem
    write(sheet.PV)
    ```

---

### mesa / room
`variável mesa/ variável room`

(Não é uma função)
[Objeto Mesa](ObjetoMesa.md) representando a mesa em que a macro está sendo executada.

!!! example "Exemplo 1: Exibir algumas informações da mesa na tela."
    ```lua
    escrever(mesa.nome)
    escrever(mesa.sistema)
    escrever(mesa.msgStatus)
    ```

---

### jogadores / players
`variável jogadores/ variável players`

(Não é uma função)
Arranjo de [Objeto Jogador](ObjetoJogador.md), representando os usuários que estão na mesa no momento.

Forma de uso: jogadores[1] contém o primeiro jogador, jogadores[2] contém o segundo jogador, jogadores[3] contém o terceiro, jogadores[#jogadores] possui o último jogador.

!!! example "Exemplo 1: Exibir na tela o login de todos os jogadores da mesa."
    ```lua
    for i = 1, #jogadores, 1 do
        escrever(jogadores[i].login)
    end
    ```

!!! example "Exemplo 2: Dar +voz para todos os espectadores da mesa."
    ```lua
    for i = 1, #jogadores, 1 do
        if jogadores[i].isEspectador then
            jogadores[i]:requestSetVoz(true)
        end
    end
    ```

---

### inRoom
`variável inRoom`

(Não é uma função)
Booleano (1) indicando se a macro está sendo executada em algum chat associado a alguma mesa.
{ .annotate }

1. 
| true | false |
|---|---|
|1|0|

---

## Funções

| **function** escrever(texto\[, quebrarLinha, permitirSmileys\])/ **function** write(texto\[, quebrarLinha, permitirSmileys\]) |
| --- |
Escreve um texto na tela do chat. Este texto não é enviado para ninguém e aparecerá somente no chat do próprio usuário.

Parâmetros:

* 
  * texto - Cadeia de caracteres contendo o texto que deseja escrever.
- 
  - (OPCIONAL) quebrarLinha - Booleano (true/ false) indicando se o RRPG deve adicionar uma quebra de linha no chat antes de escrever o texto. Se omitido, o valor padrão true é assumido.
  - (OPCIONAL) permitirSmileys - Booleano (true/ false) indicando se o RRPG deve interpretar smileys/memes neste texto. Se omitido, o valor padrão true é assumido.

Exemplo:

| escrever("Olá mundo\!\!\!"); |
| --- |


| **function** enviar(mensagem)/ **function** send(mensagem) |
| --- |
Envia uma mensagem comum para o chat, como se o usuário a tivesse digitado.

Parâmetros:

* 
  * mensagem - Cadeia de caracteres contendo o texto que deseja enviar.

Exemplo:

| enviar("Olá, tudo bem?\!"); |
| --- |


| **function** agir(acao)/ **function** act(acao) |
| --- |


Envia uma mensagem como ação para o chat.

Parâmetros:

* 
  * acao - Cadeia de caracteres contendo a acao que deseja enviar.

Exemplo:

| agir("saca sua espada longa"); |
| --- |


| **function** narrar(narracao)/ **function** narrate(narracao) |
| --- |


Envia uma mensagem de narração para o chat.

Parâmetros:

* 
  * narracao - Cadeia de caracteres contendo a narração que deseja enviar.

Observação: Apenas o mestre consegue enviar mensagens de narração.

Exemplo:

| narrar("Após uma péssima noite de descanso, Gruumsh acorda com as mãos algemadas"); |
| --- |


| **function** enviarNPC(npc, mensagem)/ **function** sendNPC(npc, mensagem) |
| --- |


Envia uma mensagem para o chat como se um NPC estivesse falando

Parâmetros:

* 
  * npc - Cadeia de caracteres contendo o nome do NPC.
  * mensagem - Cadeia de caracteres contendo a mensagem que deseja enviar.

Observação: Apenas o mestre consegue enviar mensagens como NPC.

Exemplo:

| enviarNPC("Rei Darik", "Guardas, prendam estes infelizes\!"); |
| --- |


| **function** rolar(rolagem\[, mensagemAdicional\])/ **function** roll(rolagem\[, mensagemAdicional\]) |
| --- |


Executa uma rolagem de dados no chat.

Parâmetros:

* 
  * rolagem - Cadeia de caracteres contendo a rolagem a ser feita. Exemplo: "1d20 + 5"
- 
  - (OPCIONAL) mensagemAdicional - Uma cadeia de caracteres opcional que acompanhará a rolagem na interface.

Retorno:

* 
  * Esta função retorna um número contendo o resultado e um [objeto rolagem](<ObjetoRolagem.md>) com informações detalhadas do resultado.

Importante:

* 
  * Esta função espera a rolagem ser feita na interface para continuar a execução da Macro. Se, por algum motivo, a rolagem não puder ser feita, a macro pára de executar. Uma possível situação de exemplo é quando a mesa está moderada e o usuário não possui o modo +voz para enviar mensagens.

Exemplo 1:

| **local** resultado = rolar("1d20 + 5");  **if** resultado \>= 15 **then**         enviar("Acertou\!"); **else**         enviar("Errou\!"); **end**; |
| --- |


Exemplo 2:

| **local** resultado = rolar("1d20 + 5", "Rolagem de ataque");  **if** resultado \>= 15 **then**         rolar("1d8 + 5", "Rolagem de dano");  **end**; |
| --- |


Exemplo 3: Rolar 4d6 e selecionar os 3 maiores números da rolagem.

| **local** resultado, rolagem = rolar("4d6"); **local** dados = {};  *-- coletar os resultados individuais de cada dado* **for** i = 1, #rolagem.ops, 1 **do**         **local** op = rolagem.ops\[i\];                **if** op.tipo == "dado" **then**                 **for** j = 1, #op.resultados, 1 **do**                         dados\[#dados + 1\] = op.resultados\[j\];                 **end**;         **end**; **end**;  *-- Ordenar os resultados, menores primeiro* table.sort(dados);  **local** texto = "";  *-- Pegar os ultimos 3, isto é, os 3 maiores.. de traz para frente * **for** i = #dados, #dados - 2, -1 **do**                 texto = texto .. " " .. dados\[i\]; **end**;  enviar("Os 3 maiores números foram:" .. texto); |
| --- |




| **function** rolarLocal(rolagem)/ **function** rollLocal(rolagem) |
| --- |


Executa uma rolagem de dados local, isto é, uma rolagem que não será exibida em lugar nenhum.

Parâmetros:

* 
  * rolagem - Cadeia de caracteres contendo a rolagem a ser feita. Exemplo: "1d20 + 5"

Retorno:

* 
  * Esta função retorna um número contendo o resultado e um [objeto rolagem](<ObjetoRolagem.md>) com informações detalhadas do resultado.

Exemplos:

  O comportamento da função "rolarLocal" é igual a da função "rolar", portanto, consulte os exemplos de ["rolar"](<BibliotecaparaMacrosemLua.md#função%20rolar>).



| **function** esperar(milisegundos)/ **function** wait(milisegundos) |
| --- |


Realiza uma pausa cronometrada na execução da Macro.

Parâmetros:

* 
  * milisegundos - Um número em milisegundos representando o intervalo de tempo que a execução da Macro ficará pausada. 1000 = 1 segundo, 500 = 0,5 segundos.



| **function** load(luaCode) |
| --- |


Interpreta um código de macro escrita na linguagem LUA

Parâmetros:

* 
  * luaCode - Cadeia de caracteres contendo um código na linguagem LUA (seguindo o mesmo padrão de uma macro).

Retorno:

* 
  * Se luaCode possui um código Lua válido, retorna uma função que poderá ser invocada
  * Se lucaCode **não** possui um código Lua válido, retorna dois valores: **nil** e uma mensagem de erro.

Exemplo:

| **local** func, errorMsg = load("write(1 + 5 + 9 + 10)");   **if** func ~= nil **then**   *-- O codigo foi carregado. Vamos invocá-lo agora*   func(); **else**   write("could not load lua code: " .. errorMsg); **end** |
| --- |


| **function** Log.e(tag, msg) **function** Log.w(tag, msg) **function** Log.i(tag, msg) **function** Log.d(tag, msg) **function** Log.v(tag, msg) |
| --- |


Emmit log message to the Firecast's log file and to the Firecast's console window. Use the /console command to reveal the console

Arguments:

* 
  * tag - Used to identify the source of a log message. It usually identifies the location or activity where the log call occurs.
  * msg - The message you would like to be logged

Log severity:

| Log.e | **Error message** A situation that represents an unhandled error that may interrupt some operation |
| --- | --- |
| Log.w | **Warning message** A situation that can be handled but may cause some unintended behavior |
| Log.i | **Informational/Notice message** A normal but significant condition that may require special handling. |
| Log.d | **Debug message** A developer debug message |
| Log.v | **Verbose message** Algorithm steps message, very low priority messages. Remarks: Messages of this severity are not emitted in the Firecast’s log files In the Firecast’s console, you need to execute the command “filter add \*” to be able to see these messages. |


| **function** showMessage(msg) |
| --- |


Exibe uma janela para o usuário contendo uma mensagem.

Parâmetros:

* 
  * msg - Cadeia de caracteres contendo a mensagem que deverá ser exibida para o usuário.

Observação:

* 
  * A execução da macro é pausada até que o usuário pressione OK na janela.

| **function** alert(msg) |
| --- |


Exibe uma janela para o usuário contendo uma mensagem de alerta.

Parâmetros:

* 
  * msg - Cadeia de caracteres contendo a mensagem que deverá ser exibida para o usuário.

Observação:

* 
  * A execução da macro é pausada até que o usuário pressione OK na janela.

| **function** toast(message) |
| --- |


Show a quick informative message to the user that does not require user interaction and hides automatically after a short time

Parameters

* 
  * message - The message string to be shown

| **function** confirmOkCancel(question) |
| --- |


Exibe uma janela para o usuário onde ele deve escolher responder/ "Ok"/ "Cancelar"

Parâmetros:

* 
  * question - Cadeia de caracteres contendo a mensagem que deverá ser exibida para o usuário.

Retorno:

* 
  * **true** se o usuário responder "Ok"/ **false** se o usuário responder "Cancelar"

Observação:

* 
  * A execução da macro é pausada até que o usuário responda a janela.

Exemplo:

| **if** confirmOkCancel("Será adicionado 6 à rolagem") **then**   write("O usuario respondeu OK"); **else**   write("O usuario respondeu Cancelar"); **end** |
| --- |


| **function** confirmYesNo(question) |
| --- |


Exibe uma janela para o usuário onde ele deve escolher responder/ "Sim"/ "Não"

Parâmetros:

* 
  * question - Cadeia de caracteres contendo a pergunta que deverá ser exibida para o usuário.

Retorno:

* 
  * **true** se o usuário responder "Sim"/ **false** se o usuário responder "Não"

Observação:

* 
  * A execução da macro é pausada até que o usuário responda a janela.

Exemplo:

| **if** confirmYesNo("Deseja continuar?") **then**   write("O usuario respondeu Sim"); **else**   write("O usuario respondeu Não"); **end** |
| --- |


| **function** inputQuery(prompt\[, initialValue, allowEmptyString\]) |
| --- |


Exibe uma janela para o usuário onde ele deve digitar um valor.

Parâmetros:

* 
  * prompt - Cadeia de caracteres orientando o usuário o que ele deve preencher.
  * (OPCIONAL) initialValue - Cadeia de caracteres contendo uma sugestão de valor inicial para o usuário.
  * (OPCIONAL) allowEmptyString - true se o usuário pode informar um texto em branco. O padrão é false.

Retorno:

* 
  * Se o usuário confirmar o valor, esta função retorna o valor escrito pelo usuário
  * Se o usuário escolher cancelar na janela exibida, a macro pára de executar.

Observação:

* 
  * A execução da macro é pausada até que o usuário responda a janela.

Exemplo:

| **local** bonus = inputQuery("Bônus de Ataque"); **local** defesa = inputQuery("Defesa", "10");   **if** roll("1d20 + " .. bonus) \>= tonumber(defesa) **then**   write("Acertou"); **else**   write("Errou"); **end**; |
| --- |


| **function** selectImageURL(\[defaultURL\]) |
| --- |


Esta função exibe uma janela para o usuário escolher uma URL de uma imagem.

Parâmetros:

* 
  * (OPCIONAL) defaultURL - Texto contendo uma URL sugerida para o usuário

Retorno:

* 
  * Retorna a URL de uma imagem escolhida pelo usuário

Observação:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.

Exemplo:

| **local** url = selectImageURL(); write("Imagem escolhida: " .. url); |
| --- |


| **function** choose(prompt, options, \[defaultOptionIndex, shortCircuit\]) |
| --- |


Exibe um diálogo para que o usuário possa escolher uma opção dentre uma lista de opções.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * options - Um array/arranjo/lista de cadeias de caracteres/textos, contendo as opções que devem ser apresentadas ao usuário.
  * (OPCIONAL) defaultOptionIndex - Um número contendo um índice informado qual dos itens de "options" deve ser apresentado como a escolha padrão. Se não informado, nenhuma opção será mostrada como padrão.
  * (OPCIONAL) shortCircuit - Avaliação Curto-Circuito: Se for "true" e se houver apenas uma opção a ser mostrada ao usuario, a interface não é exibida e esta opçao é automaticamente selecionada. Se não informado, este parâmetro assume o valor false.

Retorno:

  Esta função retorna dois valores na seguinte ordem:

* 
  * 
    * index - Um número, o índice de "options" que foi escolhido pelo usuário
    * text - O texto equivalente ao índice escolhido pelo usuário, conforme "options"

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.
  * Lembre-se que indices de arrays em lua começa do número 1 ao invés de 0
- 
  - Se "options" não for válido/ se for um arranjo com 0 itens, a macro pára de executar como se o usuário tivesse cancelado a janela.

Exemplo:

| **local** indice, texto = choose("O que deseja fazer?", {"Atacar", "Defender"}, 1);   escrever("O usuário escolheu o índice: " .. indice); escrever("O usuário escolheu: " .. texto);  |
| --- |


| **function** chooseMultiple(prompt, options) |
| --- |


Exibe um diálogo para que o usuário possa escolher **uma/ mais** opções dentre uma lista de opções.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * options - Um array/lista/arranjo de textos/cadeias de caracteres, contendo as opções que devem ser apresentadas ao usuário.

Retorno:

Esta função retorna dois valores na seguinte ordem:

* 
  * 
    * indexes - Um array/arranjo/lista de números, contendo os índices de "options" que foram escolhidos pelo usuário
    * texts - Um array/arranjo/lista de textos equivalentes aos índices escolhidos pelo usuário, conforme "options"

Observação:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.
  * Lembre-se que indices de arrays em lua começa do número 1 ao invés de 0
- 
  - Se "options" não for válido/ se for um arranjo com 0 itens, a macro pára de executar como se o usuário tivesse cancelado a janela.

Exemplo:

| **local** indices, textos = chooseMultiple("Bônus ativos", {"Cobertura", "Defesa Total", "Escondido"});   **for** i = 1, #indices, 1 **do**    escrever("O usuário escolheu o índice: " .. indices\[i\]);    escrever("O usuário escolheu: " .. textos\[i\]); **end**;  |
| --- |


| **function** chooseCharacter(prompt\[, filter, shortCircuit\]) |
| --- |


Exibe um diálogo para que o usuário possa escolher um personagem da lista de personagens que estão na biblioteca da mesa.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * (OPCIONAL) filter - Uma cadeia de caracteres informando quais persnagens devem ser apresentados na interface de seleção e pode ser um dos seguintes valores:
    * "all" - Todos os personagens da mesa deverão ser apresentados na janela (Opção padrão caso não seja informado filter)
    * "pc" - Apenas os personagens de jogadores deverão ser apresentados na janela.
    * "pcOnline" - Apenas os personagens de jogadores que estão online deverão ser apresentados na janela.
    * "npc" - Apenas os personagens do mestre deverão ser apresentados.
    * "mine" - Apenas os personagens do jogador que executar a macro deverão ser apresentados.
  * (OPCIONAL) shortCircuit - Avaliação Curto-Circuito: Se for "true" e se houver apenas um personagem a ser mostrado ao usuario, a interface não é exibida e este personagem é automaticamente selecionado. Se não informado, este parâmetro assume o valor false .

Retorno:

* 
  * Um [Objeto Personagem ](<ObjetoPersonagem.md>)representando o personagem que o usuário escolheu.

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.
  * Se o filtro especificado por "filter" não for capaz de apresentar nenhum personagem para escolha, um erro será exibido para o usuário.

Exemplo:

| **local** personagem = chooseCharacter("Qual personagem deseja testar a força?", "pc"); escrever("Você selecionou: " .. personagem.nome);  |
| --- |


| **function** chooseCharacterOfPlayer(prompt, player \[, shortCircuit\]) |
| --- |


Exibe um diálogo para que o usuário possa escolher um personagens da lista de personagens de um jogador na mesa.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * player - Uma cadeia de caracteres contendo o login do usuário **ou** um [Objeto Jogador](<ObjetoJogador.md>) representando de qual jogador os personagens deverão ser apresentados na tela.
  * (OPCIONAL) shortCircuit - Avaliação Curto-Circuito: Se for "true" e se houver apenas um personagem a ser mostrado ao usuario, a interface não é exibida e este personagem é automaticamente selecionado. Se não informado, este parâmetro assume o valor false .

Retorno:

* 
  * Um [Objeto Personagem ](<ObjetoPersonagem.md>)representando o personagem que o usuário escolheu.

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.
  * Se o jogador não possuir nenhum personagem, um erro é lançado.

Exemplo:

| **local** player = choosePlayer("Selecione um jogador");   **local** personagem = chooseCharacterOfPlayer("Selecione um personagem", player); escrever(personagem.nome);   **local** personagem2 = chooseCharacterOfPlayer("Selecione um personagem", "AlyssonRPG"); escrever(personagem2.nome); |
| --- |


| **function** chooseCharacters(prompt\[, filter\]) |
| --- |


Exibe um diálogo para que o usuário possa escolher **um/ mais** personagens da lista de personagens que estão na biblioteca da mesa.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * (OPCIONAL) filter - Uma cadeia de caracteres informando quais persnagens devem ser apresentados na interface de seleção e pode ser um dos seguintes valores:
    * "all" - Todos os personagens da mesa deverão ser apresentados na janela (Opção padrão caso não seja informado filter)
    * "pc" - Apenas os personagens de jogadores deverão ser apresentados na janela.
    * "pcOnline" - Apenas os personagens de jogadores que estão online deverão ser apresentados na janela.
    * "npc" - Apenas os personagens do mestre deverão ser apresentados.
    * "mine" - Apenas os personagens do jogador que executar a macro deverão ser apresentados.

Retorno:

* 
  * Um array/arranjo/lista de [Objeto Personagem ](<ObjetoPersonagem.md>)representando os personagens que o usuário escolheu.

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.
  * Se o filtro especificado por "filter" não for capaz de apresentar nenhum personagem para escolha, um erro será exibido para o usuário.

Exemplo:

| **local** personagens = chooseCharacters("Quais personagens deseja testar a força?", "pcOnline");   **for** i = 1, #personagens, 1 **do**   escrever("Você selecionou: " .. personagens\[i\].nome); **end**; |
| --- |


| **function** choosePlayer(prompt\[, shortCircuit\]) |
| --- |


Exibe um diálogo para que o usuário possa escolher um jogador da lista de jogadores que estão na mesa.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * (OPCIONAL) shortCircuit - Avaliação Curto-Circuito: Se for "true" e se houver apenas um jogador a ser mostrado ao usuario, a interface não é exibida e este jogador é automaticamente selecionado. Se não informado, este parâmetro assume o valor false .

Retorno:

* 
  * Um [Objeto Jogador](<ObjetoJogador.md>) representando o jogador que o usuário escolheu.

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.

Exemplo:

| **local** jogador = choosePlayer("De qual jogador voce quer obter informações?") escrever("Você selecionou: " .. jogador.login);   **if** jogador.isMestre **then**    escrever("O jogador é mestre na mesa"); **end**;  |
| --- |


| **function** choosePlayers(prompt) |
| --- |


Exibe um diálogo para que o usuário possa escolher **um/ mais** jogadores da lista de jogadores que estão na mesa.

Parâmetros

* 
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.

Retorno:

* 
  * Um array/lista de [Objeto Jogador](<ObjetoJogador.md>) representando os jogadores que o usuário escolheu.

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.

Exemplo:

| **local** jogadores = choosePlayers("Selecione quais jogadores devem rolar iniciativa");   **for** i = 1, #jogadores, 1 **do**    escrever("Rolar iniciativa de " .. jogadores\[i\].login); **end**; |
| --- |


| **function** getCharacterOfPlayer(player) |
| --- |
Retorna o personagem principal de um jogador da mesa.

Parâmetros

* 
  * player - Uma cadeia de caracteres contendo o login do usuário **ou** um [Objeto Jogador](<ObjetoJogador.md>) representando de qual jogador se deve obter o personagem principal.

Retorno:

* 
  * Um [Objeto Personagem ](<ObjetoPersonagem.md>)representando o personagem principal do jogador.

Observações:

* 
  * A execução da macro é pausada até que o usuário responda a janela.
  * Se o usuário cancelar a janela, a macro pára de executar.
  * Se o jogador não possuir nenhum personagem, um erro é lançado.
  * Se o jogador possuir dois/ mais personagens, o personagem principal dele será retornado.

Exemplo:

| **local** player = choosePlayer("Escolha um jogador");   **local** personagemPrincipal = getCharacterOfPlayer(player); escrever(personagemPrincipal.nome); |
| --- |


| **function** getCharacterSheet(character) |
| --- |
Retorna o Node Database/sheet de um personagem.

Parâmetros

* 
  * character - Um [Objeto Personagem ](<ObjetoPersonagem.md>)representando o personagem de qual se deve obter o NodeDatabase/sheet

Retorno:

* 
  * O [Objeto Nodo](<ObjetoNodo.md>) raiz representando o NodeDatabase/Sheet do personagem

Observações:

* 
  * A execução da macro pode ser pausada até que o NodeDatabase/Ficha seja carregada pela internet.
  * O Objeto Nodo retornado é o mesmo daquela variável "sheet" usada para programar as fichas/lua forms.
  * As alterações feitas no objeto nodo retornado são sincronizadas normalmente, confome as regras de permissões do Node Database.
  * Se houver algum erro ao carregar o NodeDatabase, a macro pára de executar.

Exemplo:

| **local** personagem = chooseCharacter("Escolha um personagem", "pc") **local** node = getCharacterSheet(personagem);   *-- Escrever no chat a estrutura dos dados armazenados da ficha* write(utils.tableToStr(node, true));   *-- Se for a ficha D\&D 5, a linha abaixo aumenta a CA em 1* node.CA = (tonumber(node.CA) **or** 0) + 1; |
| --- |


| **function** getUserNDB(name\[, options\]) |
| --- |
Open a per-user [NodeDatabase](<NodeDatabase.md>) that is physically stored in the Firecast server.

Arguments:

* 
  * name - A string identifying which remote user NodeDatabase should be opened
  * (OPTIONAL) options - A Lua table describing additional settings that may contain:
    * create - a boolean. If **true**, the NodeDatabase can be created if it does not exist. Default: **false**

Return:

* 
  * [Node Object](<ObjetoNodo.md>)

Remarks:

* 
  * The content of NodeDatabases opened by this function is stored separately per-user. Each user will have their own copy of the NodeDatabase identified by the “name” argument



| **function** getUserRoomNDB(name\[, options\]) |
| --- |
Open a per user [NodeDatabase](<NodeDatabase.md>) in the current room that is physically stored in the Firecast server.

Arguments:

* 
  * name - A string identifying which remote user NodeDatabase in the current room should be opened
  * (OPTIONAL) options - A Lua table describing additional settings that may contain:
    * create - a boolean. If **true**, the NodeDatabase can be created if it does not exist. Default: **false**

Return:

* 
  * [Node Object](<ObjetoNodo.md>)

Remarks:

* 
  * The content of NodeDatabases opened by this function is stored separately per-user and per-room. Each user in the current room will have their own copy of the NodeDatabase identified by the “name”.

| **function** getRoomNDB(name\[, options\]) |
| --- |
Open a per room [NodeDatabase](<NodeDatabase.md>) that is physically stored in the Firecast server.

Arguments:

* 
  * name - A string identifying which remote NodeDatabase of the current room should be opened
  * (OPTIONAL) options - A Lua table describing additional settings that may contain:
    * create - a boolean. If **true**, the NodeDatabase can be created if it does not exist. Default: **false**

Return:

* 
  * [Node Object](<ObjetoNodo.md>)

Remarks:

* 
  * The content of NodeDatabases opened by this function is stored separately per-room. All users of the current room will access the same content of the NodeDatabase identified by the “name”.
  * By default, users with the +GM mode can read and modify the NodeDatabase of the room while other users can only read values.
  * To open a NodeDatabase of the room, one of the following statements must be true:
    * The current user is a Gold subscriber; or
    * The creator of the room is a Platinum subscriber.

| **function** invoke(macroName \[, parameter\]) |
| --- |


Esta função invoca/tra macro e aguarda sua execução.

Parâmetros:

* 
  * macroName - Cadeia de caracteres identificando qual macro deve ser invocada.
    * Exemplo: Se deseja invocar a macro /obterBonusAtaque, o valor "obterBonusAtaque" deverá se passado aqui, sem a barra.
  * (OPCIONAL) parameter - Cadeia de caracteres contendo os parâmetros que devem ser passados para a macro quando ela for invocada.

Retorno:

* 
  * Se a macro invocada tiver sido executada sem erros, o retorno desta função é idêntico ao "return" da macro invocada (**nil** se ela não especificou valor de return).

Observação:

* 
  * A execução desta macro é pausada até a/tra macro seja executada.
  * Se a macro invocada parar de executar (exemplo: Pois o usuário cancelou um inputQuery), esta macro também pára de executar.
Exemplo (duas macros, uma invocando a/tra):

  **Macro: ObterBonusAtaque**

| **local** attack = inputQuery("Informe o Bônus de Ataque"); **local** damageBonus = inputQuery("Informe o Bônus de Dano");   **return** attack, tonumber(damageBonus); |
| --- |
**Macro que invoca/tra macro**

| **local** bonusAttack, damage = invoke("ObterBonusAtaque") write("Ataque informado: " .. bonusAttack) write("Dano informado: " .. damage); |
| --- |

