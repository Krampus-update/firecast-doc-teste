# Biblioteca Dialogs

# Biblioteca Dialogs

A biblioteca dialogs provê funções para exibir mensagens e interagir com o usuário através de diálogos.

Todas as funções estão contidas na table/variável "Dialogs" da unidade "dialogs.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "dialogs.lua"* require("dialogs.lua");    *-- Agora é possível acessar as funções da biblioteca* Dialogs.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca Dialogs

&nbsp;

| **function** Dialogs.showMessage(msg \[, callback\]) ou **function** showMessage(msg \[, callback\]) |
| --- |


&nbsp;

Exibe uma mensagem de informação para o usuário&nbsp; (um simples diálogo com o botão "OK").

&nbsp;

Parâmetros:

* &nbsp;
  * msg – Uma cadeia de caracteres contendo a mensagem que deverá ser exibida na interface.
  * (OPCIONAL) callback - uma função que será chamada após o usuário clicar em OK.

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Não retorna nenhum valor.

&nbsp;

Observações:&nbsp;

* &nbsp;
  * A função não espera o usuário responder o diálogo para continuar, Isto é, o diálogo é apresentado na interface e o código LUA continua a sua execução normal enquanto isso.
  * Se quiser executar algo após o usuário confirmar o diálogo, informe o parâmetro "callback"

&nbsp;

&nbsp;

| **function** Dialogs.alert(msg \[, callback\]) ou **function** alert(msg \[, callback\]) |
| --- |


&nbsp;

Exibe uma mensagem de alerta para o usuário&nbsp; (um simples diálogo com ícone de alerta e botão "OK").

&nbsp;

Parâmetros:

* &nbsp;
  * msg – Uma cadeia de caracteres contendo a mensagem que deverá ser exibida na interface.
  * (OPCIONAL) callback - uma função que será chamada após o usuário clicar em OK.

&nbsp;

Retorno: \
&nbsp; &nbsp; Não retorna nenhum valor.

&nbsp;

Observações:&nbsp;

* &nbsp;
  * A função não espera o usuário responder o diálogo para continuar, Isto é, o diálogo é apresentado na interface e o código LUA continua a sua execução normal enquanto isso.
  * Se quiser executar algo após o usuário confirmar o diálogo, informe o parâmetro "callback"

&nbsp;

&nbsp;

| **function** Dialogs.confirmOkCancel(question \[, callback\]) |
| --- |


&nbsp;

Exibe uma informação na interface com os botões OK e CANCEL, permitindo o usuário optar por continuar ou por cancelar alguma ação.

&nbsp;

Parâmetros:

* &nbsp;
  * question – Uma cadeia de caracteres contendo a mensagem que deverá ser exibida na interface.
  * (OPCIONAL) callback - uma função que será chamada após o usuário se decidir. Esta função receberá no primeiro parâmetro o valor **true** se o usuário tiver optado por "OK" ou **false** caso contrário.

&nbsp;

Retorno: \
&nbsp; &nbsp; Não retorna nenhum valor.

&nbsp;

Observações:&nbsp;

* &nbsp;
  * A função não espera o usuário responder o diálogo para continuar, Isto é, o diálogo é apresentado na interface e o código LUA continua a sua execução normal enquanto isso.
  * Se quiser saber qual foi a escolha do usuário, utilize o parâmetro "callback".

&nbsp;

Exemplo:

| Dialogs.confirmOkCancel("Continuar irá acontecer X coisa",         **function** (confirmado)                 **if** confirmado **then**                         *-- usuario escolheu OK*                 **else**                         *-- usuário escolheu CANCEL*                 **end**;         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.confirmYesNo(question \[, callback\]) |
| --- |


&nbsp;

Exibe uma informação na interface com os botões YES e NO, permitindo o usuário responder "sim" ou "não" a alguma pergunta.

&nbsp;

Parâmetros:

* &nbsp;
  * question – Uma cadeia de caracteres contendo a pergunta que deverá ser exibida na interface.
  * (OPCIONAL) callback - uma função que será chamada após o usuário se decidir. Esta função receberá no primeiro parâmetro o valor **true** se o usuário tiver optado por "SIM" ou **false** caso contrário.

&nbsp;

Retorno: \
&nbsp; &nbsp; Não retorna nenhum valor.

&nbsp;

Observações:&nbsp;

* &nbsp;
  * A função não espera o usuário responder o diálogo para continuar, Isto é, o diálogo é apresentado na interface e o código LUA continua a sua execução normal enquanto isso.
  * Se quiser saber qual foi a escolha do usuário, utilize o parâmetro "callback".

&nbsp;

Exemplo:

| Dialogs.confirmYesNo("Deseja realmente apagar este item?",         **function** (confirmado)                 **if** confirmado **then**                         *-- usuario escolheu SIM*                 **else**                         *-- usuário escolheu NAO*                 **end**;         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.showMessageDlg(message, dialogType, dialogButtons \[, callback\]) |
| --- |


&nbsp;

Exibe um diálogo customizado pelo programador na interface.

&nbsp;

Parâmetros:

* &nbsp;
  * message – Uma cadeia de caracteres contendo a mensagem que será exibida na interface
  * dialogType - O tipo de diálogo. Pode ser um dos seguintes valores:
    * dialogs.DT\_INFORMATION&nbsp; - uma informação
    * dialogs.DT\_ERROR - um erro
    * dialogs.DT\_WARNING - um alerta
    * dialogs.DT\_CONFIRMATION - uma confirmação
  * dialogButtons - Quais botões serão exibidos na interface. É um arranjo/tabela lua contendo a combinação dos seguintes valores:
    * dialogs.DB\_YES
    * dialogs.DB\_NO
    * dialogs.DB\_OK
    * dialogs.DB\_CANCEL
    * dialogs.DB\_ABORT
    * dialogs.DB\_RETRY
    * dialogs.DB\_IGNORE
    * dialogs.DB\_CLOSE
  * (OPCIONAL) callback - uma função que será chamada após o usuário se decidir. Esta função receberá no primeiro parâmetro qual botão foi pressionado. (Este valor é um daqueles informados no parâmetro dialogButtons).

&nbsp;

Retorno: \
&nbsp; &nbsp; Não retorna nenhum valor.

&nbsp;

Observações:&nbsp;

* &nbsp;
  * A função não espera o usuário responder o diálogo para continuar, Isto é, o diálogo é apresentado na interface e o código LUA continua a sua execução normal enquanto isso.
  * Se quiser saber qual foi a escolha do usuário, utilize o parâmetro "callback".
  * Nem toda combinação de botões são válidas. As combinações de botões válidas são:
    * {dialogs.DB\_OK}
    * {dialogs.DB\_OK, dialogs.DB\_CANCEL}
    * {dialogs.DB\_YES, dialogs.DB\_NO}
    * {dialogs.DB\_YES, dialogs.DB\_NO, dialogs.DB\_CANCEL}
    * {dialogs.DB\_ABORT, dialogs.DB\_IGNORE, dialogs.DB\_RETRY}
    * {dialogs.DB\_ABORT, dialogs.DB\_IGNORE}

&nbsp;

Exemplo:

|  Dialogs.showMessageDlg("O que fazer?", dialogs.DT\_WARNING,                        {dialogs.DB\_ABORT, dialogs.DB\_IGNORE, dialogs.DB\_RETRY},    &nbsp;                                          &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   **function** (escolha)                        &nbsp; &nbsp; **if** escolha == dialogs.DB\_ABORT **then**                            &nbsp; &nbsp; *-- usuario escolheu ABORT*                            **elseif** escolha == dialogs.DB\_IGNORE **then**                                *-- usuário escolheu IGNORE*                            **elseif** escolha == dialogs.DB\_RETRY **then**                               *-- usuário escolheu RETRY                                                     *                            **end**;                         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.inputQuery(caption, prompt\[, initialValue \[, confirmCallback \[, cancelCallback, \[, allowEmptyString\]\]\]\]) |
| --- |


&nbsp;

Exibe um diálogo para que o usuário preencha alguma informação.

&nbsp;

Parâmetros:

* &nbsp;
  * caption – Cadeia de caracteres contendo o título do diálogo
  * prompt - Cadeia de caracteres que contém uma orientação para que o usuário saiba o que deve digitar. Exemplo: "Informe seu nome".
  * (OPCIONAL) initialValue - Cadeia de caracteres contendo o valor que já virá preenchido no diálogo.
  * (OPCIONAL) confirmCallback - Uma função que será invocada após o usuário confirmar o preenchimento. O valor que foi informado pelo usuário é passado no primeiro parâmetro desta função.
  * (OPCIONAL) cancelCallback - Uma função que será invocada se o usuário cancelar o diálogo.
  * (OPCIONAL) allowEmptyString - Um booleano indicando se o usuário pode informar uma cadeia de caracteres vazia. Se omitido, este parâmetro é interpretado como **false**.

&nbsp;

Retorno: \
&nbsp; &nbsp; Não retorna nenhum valor.

&nbsp;

Observações:&nbsp;

* &nbsp;
  * A função não espera o usuário responder o diálogo para continuar, Isto é, o diálogo é apresentado na interface e o código LUA continua a sua execução normal enquanto isso.
  * Se quiser saber qual foi a informação preenchida pelo usuário, utilize os parâmetros "confirmCallback" e/ou "cancelCallback".

&nbsp;

&nbsp;

Exemplo:

&nbsp;

| Dialogs.inputQuery("Cadastro", "Informe Seu Nome", "",         **function** (valorPreenchido)                 showMessage("O usuario preencheu: " .. valorPreenchido);         **end**,                **function**()                 showMessage("O usuário cancelou");         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.openFile(prompt\[, accept \[, multiple \[, callback \[, cancelCallback\]\]\]\]) |
| --- |


&nbsp;

Exibe um diálogo para que o usuário escolha um ou mais arquivos do seu computador/dispositivo para abrir.&nbsp;

&nbsp;

Parâmetros:

* &nbsp;
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre qual arquivo ele deve selecionar. Exemplo: "Escolha uma imagem".
  * (OPCIONAL) accept - Uma cadeia de caracteres usada para filtrar quais arquivos o usuário pode selecionar. Você pode passar aqui:
    * ".\<EXTENSÃO\>" para filtrar arquivos de uma determinada extensão. Exemplo: ".txt", ".mp3", ".png", etc..
    * "\<MIME\_TYPE\>" para filtrar arquivos pelo Media/Mime Type. Exemplos: "image/png", "application/xml", "text/plain", etc..
    * "image/\*" para filtrar todos os formatos de imagens suportados pelo RRPG.
    * "\*.\*" ou nil - Para aceitar qualquer tipo de arquivo.
    * Uma lista das opções anteriores separadas por vírgula. Exemplos:
      * ".png, .txt, .bmp" - para aceitar arquivos de extensões PNG, TXT e BMP
      * ".html, text/plain, image/\*" - para aceitar arquivos HTML, arquivos de media type text/plain e também qualquer imagem.
  * (OPCIONAL) multiple - true para permitir o usuário selecionar mais de um arquivo ao mesmo tempo ou false para permitir selecionar apenas um arquivo. Se omitido este valor, o padrão é "false".
  * (OPCIONAL) callback - Uma função que será invocada quando o usuário confirmar a seleção do(s) arquivo(s). Esta função recebe em seu primeiro parâmetro um array de tabelas luas que contém cada uma:
    * name - Uma propriedade contendo o nome curto do arquivo selecionado. Exemplos: "Arquivo.txt", "Minha imagem de férias.png", etc..
    * stream - Um [objeto stream](<ObjetoStream.md>) somente leitura contendo os dados do arquivo selecionado.
  * (OPCIONAL) cancelCallback - Uma função que será invocada quando o usuário cancelar a seleção de arquivos.

&nbsp;

Observações:

* &nbsp;
  * Esta é a única maneira que o plug-in tem de obter acesso a arquivos do dispositivo do usuário.
  * Se o parâmetro "multiple" for false, a função "callback" sempre receberá um array contendo 1 tabela lua descrevendo o arquivo selecionado. Se o parâmetro "multiple" for true, o número de tabelas neste array varia conforme a quantidade de arquivos selecionados.
  * No FirecastMobile: Esta função só consegue abrir imagens da galeria do celular/tablet do usuário. Se o conteúdo do parâmetro "accept" não aceitar imagens, o evento "cancelCallback" será chamado imediatamente depois.

&nbsp;

&nbsp;

Exemplos:

* &nbsp;
  * Selecionando múltiplos arquivos de extensão .txt e .html:

| Dialogs.openFile("Selecione os arquivos", ".txt, .html", true,         **function**(arquivos)                 **for** i = 1, #arquivos, 1 **do**                         **local** arq = arquivos\[i\];                         *-- arq.name possui o nome do arquivo*                         *-- arq.stream possui o objeto stream do conteúdo*                 **end**;         **end**); |
| --- |


&nbsp;

* &nbsp;
  * Selecionando 1 arquivo de imagem:

| Dialogs.openFile("Selecione o arquivo de imagem", "image/\*", false,         **function**(arquivos)                 **local** arq = arquivos\[1\];                 *-- arq.name possui o nome do arquivo*                 *-- arq.stream possui o objeto stream do conteúdo              *         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.saveFile(prompt, stream, \[suggestedFileName \[, mimeType \[, callback \[, cancelCallback\]\]\]\]) |
| --- |


&nbsp;

Exibe um diálogo para que o usuário possa salvar um arquivo em seu dispositivo.

&nbsp;

Parâmetros

* &nbsp;
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre qual arquivo ele vai salvar. Exemplo: "Salvar imagem do personagem".
  * stream - Um Um [objeto stream](<ObjetoStream.md>) contendo o que será salvo no dispositivo do usuário.
  * (OPCIONAL) suggestedFileName - Uma cadeia de caracteres contendo uma **sugestão** de nome de arquivo para o usuário. Exemplo: "novoArquivo.txt"
  * (OPCIONAL) mimeType - Uma cadeia de caracteres usada para definir o tipo de conteúdo que "stream" possúi.
    * Exemplos:&nbsp;
      * "text/plain"
      * "image/png"
      * "image/jpeg"
      * "application/octet-stream"
  * (OPCIONAL) callback - Uma função que será invocada quando o usuário confirmar a gravação do arquivo
  * (OPCIONAL) cancelCallback - Uma função que será invocada quando o usuário cancelar a gravação do arquivo.

&nbsp;

Alerta:

* &nbsp;
  * Após chamar saveFile, não altere e nem feche o objeto "stream" antes que "callback" ou "cancelCallback" seja invocado. O SDK mantém uma referência ao stream até que o usuário decida gravar o arquivo e não é seguro alterá-lo neste meio tempo.

&nbsp;

Observações:

* &nbsp;
  * Esta é a única maneira de salvar um arquivo no dispositivo do usuário.
  * Recomenda-se informar os parâmetros "mimeType" e "suggestedFileName" quando possível para que o SDK possa interagir com o usuário da melhor forma possível.
    * Se você **não** informar mimeType, o SDK automaticamente o sugere conforme a extensão de suggestedFileName.
    * Se você **não** informar suggestedFileName, o SDK automaticamente sugere a extensão do arquivo conforme mimeType.
  * No Android:
    * Esta função apresenta aquela clássifca interface de "compartilhar" do sistema operacional.
    * A função "callback" é invocada imediatamente, não sendo possível saber se o usuário compartilhou ou não o conteúdo de stream.

&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.selectImageURL(defaultURL, \[, callback \[, cancelCallback\]\]) |
| --- |


&nbsp;

Exibe um diálogo para que o usuário possa escolher uma URL de uma imagem.

&nbsp;

Parâmetros

* &nbsp;
  * defaultURL - Uma cadeia de caracteres contendo uma URL que será sugerida para o usuário. Pode ser **nil** ou vazia.
  * (OPCIONAL) callback - Uma função que será invocada quando o usuário confirmar a seleção de uma imagem. O primeiro parâmetro desta função contém a URL escolhida pelo usuário.
  * (OPCIONAL) cancelCallback - Uma função que será invocada quando o usuário cancelar a seleção de imagem.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Esta função abre a tradicional interface de escolha de imagens do RRPG.
  * Esta função é assíncrona. Ou seja, o código continua sua execução enquanto o usuário escolhe a imagem. A única maneira de obter a URL escolhida pelo usuário é através do parâmetro "callback".

&nbsp;

Exemplo:

| Dialogs.selectImageURL("http://www.google.com/imagem\_sugerida.png",     **function**(url)         showMessage("Imagem selecionada: " .. url);     **end**,         **function**()         showMessage("O usuário cancelou a janela");     **end**);&nbsp; |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** Dialogs.choose(prompt, options, callback \[, defaultOptionIndex, shortCircuit\]) |
| --- |


&nbsp;

Exibe um diálogo para que o usuário possa escolher uma opção dentre uma lista de opções.

&nbsp;

Parâmetros

* &nbsp;
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * options - Um array/arranjo de cadeias de caracteres, contendo as opções que devem ser apresentadas ao usuário.
  * callback - Uma função que será invocada quando o usuário fizer a escolha ou quando ele cancelar a escolha.
    * A função recebe três parâmetros na seguinte ordem:
      * selected - Um valor booleano (true ou false) indicando se o usuário selecionou alguma opção ou se cancelou o diálogo
      * selectedIndex - Se o usuário selecionou alguma opção, este parâmetro recebe um número representando o índice do array "options" que representa qual opção o usuário escolheu. Lembre-se que em Lua o índice de arrays começa do número 1 ao invés de 0. Se o usuário cancelou o diálogo, este parâmetro conterá **nil**.
      * selectedText - Se o usuário selecionou alguma opção, este parâmetro recebe o texto da opção escolhida conforme o parâmetro "options". Se o usuário cancelou o dialogo, este parâmetro conterá **nil**.
  * (OPCIONAL) defaultOptionIndex - Um número contendo um índice informado qual dos itens de "options" deve ser apresentado como a escolha padrão. Se não informado, nenhuma opção será mostrada como padrão.
  * (OPCIONAL) shortCircuit - Avaliação Curto-Circuito: Se for "true" e se houver apenas uma opção a ser mostrada ao usuario, a interface não é exibida e esta opçao é automaticamente selecionada. Se não informado, este parâmetro assume o valor false.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Esta função é assíncrona. Ou seja, o código continua sua execução enquanto o usuário escolhe. A única maneira de obter a resposta escolhida pelo usuário é através do parâmetro "callback".
  * Se "options" não for válido ou se for um arranjo com 0 itens, a função callback será imediatamente chamada como se o usuário tivesse cancelado a escolha.

&nbsp;

Exemplo:

| Dialogs.choose("Selecione uma das opções", {"Opção 1", "Opção 2", "Opção 3"},                **function**(selected, selectedIndex, selectedText)                   **if** selected **then**                     showMessage("O usuário selecionou índice " .. tostring(selectedIndex) .. ": " .. selectedText);                   **else**                     showMessage("O usuário cancelou");                   **end**;                **end**)&nbsp; |
| --- |


&nbsp;

&nbsp;

| **function** Dialogs.chooseMultiple(prompt, options, callback) |
| --- |


&nbsp;

Exibe um diálogo para que o usuário possa escolher **uma ou mais** opções dentre uma lista de opções.

&nbsp;

Parâmetros

* &nbsp;
  * prompt - Uma cadeia de caracteres contendo uma orientação ao usuário sobre o que ele deve selecionar.
  * options - Um array/arranjo de cadeias de caracteres, contendo as opções que devem ser apresentadas ao usuário.
  * callback - Uma função que será invocada quando o usuário fizer a escolha ou quando ele cancelar a escolha.
    * A função recebe três parâmetros na seguinte ordem:
      * selected - Um valor booleano (true ou false) indicando se o usuário selecionou ao menos uma opção ou se cancelou o diálogo
      * selectedIndexes - Se o usuário selecionou alguma opção, este parâmetro recebe um array de números representando os índices do array "options" que representa quais opções o usuário escolheu. Lembre-se que em Lua o índice de arrays começa do número 1 ao invés de 0. Se o usuário cancelou o diálogo, este parâmetro conterá **nil**.
      * selectedText - Se o usuário selecionou alguma opção, este parâmetro recebe um array de textos das opções escolhida conforme o parâmetro "options". Se o usuário cancelou o dialogo, este parâmetro conterá **nil**.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Esta função é assíncrona. Ou seja, o código continua sua execução enquanto o usuário escolhe. A única maneira de obter a resposta escolhida pelo usuário é através do parâmetro "callback".
  * Se "options" não for válido ou se for um arranjo com 0 itens, a função callback será imediatamente chamada como se o usuário tivesse cancelado a escolha.

&nbsp;

Exemplo:

| Dialogs.chooseMultiple("Selecione uma ou mais opções", {"Opção 1", "Opção 2", "Opção 3"},                **function**(selected, selectedIndexes, selectedTexts)                   **if** selected **then**                     showMessage("O usuário selecionou os índices " ..                                 tableToStr(selectedIndexes) .. ": " ..                                 tableToStr(selectedTexts));                   **else**                     showMessage("O usuário cancelou");                   **end**;                **end**)&nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Effortlessly create a professional-quality documentation website with HelpNDoc](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
