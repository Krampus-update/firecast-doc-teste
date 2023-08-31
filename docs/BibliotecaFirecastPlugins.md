# Biblioteca Firecast.Plugins

# Biblioteca Firecast.Plugins

A biblioteca Firecast.Plugins contém funções relacionadas aos plug-ins instalados no Firecast.

Todas as funções estão contidas na table/variável "Firecast.Plugins" da unidade "plugins.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "plugins.lua"* require("plugins.lua");    *-- Agora é possível acessar as funções da biblioteca* Firecast.Plugins.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

# Funções de Gerenciamento de Plugins

&nbsp;

| **function** Firecast.Plugins.getInstalledDataTypes() |
| --- |


&nbsp;

Retorna a lista de DataTypes instalados no Firecast.

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um array (uma tabela Lua indexada de 1 a N) de objetos, onde cada objeto representa um DataType instalado e possuem, cada um, os seguintes atributos:
    * moduleId - Cadeia de caracteres identificando qual plug-in instalou o dataType.
    * dataType - Cadeia de caracteres identificando o dataType
    * formType - Cadeia de caracteres identificando o formType. Veja [atributo formType da tag form](<Tagform.md#propriedade%20formType>) para saber quais são os possíveis valores deste atributo.
    * title - Cadeia de caracteres que identifica o dataType de forma intuitiva para o usuário.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.getInstalledPlugins() |
| --- |


&nbsp;

Retorna a lista de plug-ins SDK 3 instalados no Firecast.

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um array (uma tabela Lua indexada de 1 a N) de objetos, onde cada objeto representa um Plug-in instalado e possuem, cada um, os seguintes atributos:
    * moduleId - Cadeia de caracteres com a identificação única do plug-in.
    * name - Cadeia de caracteres contendo o nome do plug-in.
    * version - Cadeia de caracteres contendo a versão do plug-in.
    * description - Cadeia de caracteres contendo a descrição do plug-in.
    * author - Cadeia de caracteres contendo informações sobre o autor do plug-in.
    * site - Cadeia de caracteres contendo informações do website relacionado ao plug-in.
    * contact - Cadeia de caracteres contendo informações sober como entra em contato com o autor do plug-in.
    * fileName - Cadeia de caracteres contendo o nome do arquivo ".rpk" relacionado a este plug-in. Este atributo contém apenas o nome curto do arquivo e não descreve sua localização no HD. Exemplos: "DnD.rpk", "Vampiros.rpk", etc..
    * compilationTimestamp - A data e hora (UTC) em que o plugin foi compilado. Este atributo é representado por um número inteiro, contendo quantos **segundos** se passaram desde UNIX Epoch (01 de janeiro de 1970)
    * compilationTimestampStr - A data e hora (UTC) em que o plugin foi compilado. Este atributo é representado em uma cadeia de caracteres de tamanho fixo no formato "ddmmyyyyhhnnss" (onde "nn" são os minutos)
    * compilationDigest - Uma cadeia de caracteres contento o hash SHA-1 do conteúdo do plugin. Um plugin pode ser compilado mais de uma vez, e, por isso, compilationTimestamp pode variar sem que o conteúdo do plugin mude. É seguro afirmar que se compilationDigest não mudar, então o conteúdo do plugin não mudou. Este campo está presente em plugins compilados com o SDK 3.5+.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.getInstalledTablesDock() |
| --- |


&nbsp;

Retorna a lista de "Table's Dock"/janelas acopláveis instalados no Firecast.

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno:

* &nbsp;
  * Um array (uma tabela Lua indexada de 1 a N) de objetos, onde cada objeto representa um Table's Dock que o usuário pode utilizar em suas mesas, cada um, os seguintes atributos:
    * moduleId - Cadeia de caracteres identificando qual plug-in instalou o TablesDock.
    * name - Cadeia de caracteres contendo o nome do formulário
    * dataType - Cadeia de caracteres identificando o dataType do formulário TablesDock
    * title - Cadeia de caracteres que identifica o Table's Dock de forma intuitiva para o usuário.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.getRPKDetails(stream) |
| --- |


&nbsp;

Retorna algumas informações sobre um stream contendo um plug-in SDK3 (arquivo de extensão .rpk).

&nbsp;

Parâmetros:

* &nbsp;
  * stream - Um [objeto Stream](<ObjetoStream.md>) que possui o conteúdo do arquivo ".rpk"

&nbsp;

Retorno:

* &nbsp;
  * Se o parâmetro "stream" contiver um arquivo .rpk válido, a função retorna uma tabela lua com os seguintes atributos:
    * moduleId - Cadeia de caracteres contendo o identificador único do plug-in
    * name - Cadeia de caracteres contendo o nome do plug-in
    * version - Cadeia de caracteres contendo a versão do plug-in
    * description - Cadeia de caracteres contendo a descrição do plug-in.
    * author - Cadeia de caracteres contendo a identificação do autor do plug-in.
    * site - Cadeia de caracteres contendo informações sobre o website do plug-in.
    * contact - Cadeia de caracteres contendo informações sobre como contatar o autor do plug-in.
    * minApiVersion - Número contendo qual a versão de API do SDK3 mínima para este plug-in rodar.
    * sdkVersion - Cadeia de caracteres contendo qual a versão do SDK3 o plug-in foi compilado.
    * compilationTimestamp - A data e hora (UTC) em que o plugin foi compilado. Este atributo é representado por um número inteiro, contendo quantos **segundos** se passaram desde UNIX Epoch (01 de janeiro de 1970)
    * compilationTimestampStr - A data e hora (UTC) em que o plugin foi compilado. Este atributo é representado em uma cadeia de caracteres de tamanho fixo no formato "ddmmyyyyhhnnss" (onde "nn" são os minutos)
    * compilationDigest - Uma cadeia de caracteres contento o hash SHA-1 do conteúdo do plugin. Um plugin pode ser compilado mais de uma vez, e, por isso, compilationTimestamp pode variar sem que o conteúdo do plugin mude. É seguro afirmar que se compilationDigest não mudar, então o conteúdo do plugin não mudou. Este campo está presente em plugins compilados com o SDK 3.5+.
  * Se o parâmetro "stream" **não** contiver um arquivo rpk válido, a função retorna **nil**.

&nbsp;

Observações:

* &nbsp;
  * A função começa a ler o stream à partir da posição 0.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.installPlugin(stream \[, ignoreIfOlder\]) |
| --- |


&nbsp;

Instala um plug-in SDK3 no Firecast.

&nbsp;

Parâmetros:

* &nbsp;
  * stream - Um [objeto Stream](<ObjetoStream.md>) que possui o conteúdo do arquivo ".rpk" que deseja instalar.
  * (OPCIONAL) ignoreIfOlder - Booleano indicando se a função deve ignorar a instalação caso exista uma versão mais nova já instalada deste plug-in. Se omitido, o parâmetro possui valor false.

&nbsp;

Retorno:

* &nbsp;
  * Se a instalação for bem sucedida, a função retorna "true". Se a instalação não for bem sucedida, retorna "false" e uma cadeia de caracteres contendo o motivo da falha.

&nbsp;

Observações:

* &nbsp;
  * A função começa a ler o stream à partir da posição 0.
  * Por motivo de segurança, apenas plug-ins autorizados conseguem gerenciar os plug-ins do Firecast.
  * Se o plug-in já estiver instalado: o plug-in é descarregado, a atualização é instalada, e a nova versão é carregada novamente.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.uninstallPlugin(moduleId) |
| --- |


&nbsp;

Desinstala um plug-in SDK3 que está atualmente instalado no Firecast.

&nbsp;

Parâmetros:

* &nbsp;
  * moduleId - Cadeia de caracteres identificando qual plug-in deseja desinstalar. Cada plug-in possui um moduleId, que é uma identificação única do mesmo.

&nbsp;

Retorno:

* &nbsp;
  * Se a instalação for bem sucedida, a função retorna "true". Se a instalação não for bem sucedida, retorna "false" e uma cadeia de caracteres contendo o motivo da falha.

&nbsp;

Observações:

* &nbsp;
  * Por motivo de segurança, apenas plug-ins autorizados conseguem gerenciar os plug-ins do Firecast.

&nbsp;

&nbsp;

# Intercomunicação de plug-ins.

Os plug-ins do Firecast podem comunicar entre si afim de realizar pedidos, coordenar ações, informar algum ocorrido, etc..

&nbsp;

Todas as mensagens de plugins são compostas por:

* &nbsp;
  * identificação do plug-in destinatário.
  * nome da mensagem.
  * conteúdo da mensagem.

&nbsp;

&nbsp;Antes de receber mensagens, o plug-in deve registrar uma "escuta" através da função [Firecast.Plugins.listenPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.listenPM>) informando o nome da mensagem que ouvirá e uma função que será chamada para tratá-la.. Durante o tratamento da mensagem recebida, o plug-in receptor pode enviar uma resposta para o plug-in emissor.

&nbsp;

Para enviar uma mensagem a outro plug-in, este deve utilizar a função [Firecast.Plugins.sendPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.sendPM>) informando a identificação do plug-in destinatário, o nome da mensagem, conteúdo, uma função callback de sucesso e uma função callback de falha.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.sendPM(moduleId, pmName, data \[, callback, failureCallback\]) |
| --- |


&nbsp;

Envia uma mensagem a outro plug-in instalado no Firecast.

&nbsp;

Parâmetros:

* &nbsp;
  * moduleId - Uma cadeia de caracteres contendo a identificação única do módulo/plugin que receberá a mensagem. Este é o mesmo valor encontrado no [arquivo module.xml ](<Oarquivomodulexml.md>)de cada plug-in. Também é possível obter este valor através da função [Firecast.Plugins.getInstalledPlugins.](<BibliotecaFirecastPlugins.md#rrpg.plugins.getInstalledPlugins>)
  * pmName - Uma cadeia de caracteres contendo o nome da mensagem.&nbsp;
  * data - O corpo da mensagem, uma tabela lua que será transmitida ao plug-in destinatário.
  * (OPCIONAL) callback - Uma função que será invocada quando o plug-in destinatário responder a esta mensagem. O primeiro parâmetro da função recebe os dados enviados pelo plug-in destinatário.
  * (OPCIONAL) failureCallback - Uma função que será invocada quando ocorrer algum erro no envio e/ou processamento da mensagem. O primeiro parâmetro da função recebe os dados sobre a falha.

&nbsp;

Observações:

* &nbsp;
  * Para saber se o envio foi bem sucedido, utilize o parâmetro "callback".
  * Para saber se o envio **não** foi bem sucedido, utilize o parâmetro "failureCallback". A função failureCallback é invocada se o plugin destinatário não estiver instalado no Firecsat, se o plug-in destinatário não souber tratar mensagens de nome "pmName" ou se o ocorrer alguma falha de execução no plug-in que recebeu a mensagem.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.listenPM(pmName, callback) |
| --- |


&nbsp;

Instala uma escuta de mensagens de plugins.

&nbsp;

Parâmetros:

* &nbsp;
  * pmName - Uma cadeia de caracteres contendo o nome da mensagem que esta escuta trata.
  * callback - Uma função que será disparada quando a escuta capturar uma mensagem de nome igual a "pmName" e recebe, no primeiro parâmetro, o corpo da mensagem. Esta informação é uma tabela LUA contendo os mesmos dados que foram enviados pela função [Firecast.Plugins.sendPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.sendPM>) acrescida da propriedade "moduleId" (a identificação de qual plug-in enviou a mensagem).

&nbsp;

Observações:

* &nbsp;
  * Um plug-in só pode ter uma escuta para cada "pmName". Não é possível instalar 2 escutas para a mensagem "TESTE", por exemplo.
  * Para enviar uma resposta a quem enviou a mensagem, a função "callback" deve:
    * Se já tiver a resposta pronta, usar "return VALOR"; ... Este valor será transmitido para a função callback do plug-in emissor.
    * Se ainda não tiver a resposta pronta, deve, dentro da função "callback", invocar o método [Firecast.Plugins.setLatePMReply()](<BibliotecaFirecastPlugins.md#rrpg.plugins.setLatePMReply>) e, posteriormente, utilizar as funções [Firecast.Plugins.replyPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.replyPM>) ou [Firecast.Plugins.replyPMFailure](<BibliotecaFirecastPlugins.md#rrpg.plugins.replyPMFailure>) para enviar a resposta ao plug-in emissor.

&nbsp;

&nbsp;

| **function** Firecast.Plugins.setLatePMReply(message) |
| --- |


&nbsp;

Ao receber uma mensagem, a escuta, instalada previamente pela função [Firecast.Plugins.listenPM,](<BibliotecaFirecastPlugins.md#rrpg.plugins.listenPM>) pode invocar este método para sinalizar que ainda não tem a resposta para a mensagem e que a enviará posteriormente.

&nbsp;

Parâmetros:

* &nbsp;
  * message - A mensagem cuja resposta deseja postergar. Esta informação é a mesma que foi recebida no primeiro parâmetro da função callback da escuta (ver [Firecast.Plugins.listenPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.listenPM>)).

&nbsp;

Observações:

* &nbsp;
  * Você deve, em algum momento, invocar [Firecast.Plugins.replyPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.replyPM>) ou [Firecast.Plugins.replyPMFailure](<BibliotecaFirecastPlugins.md#rrpg.plugins.replyPMFailure>) para enviar uma resposta ao plug-in remetente. Utilizar setLatePMReply e não invocar [Firecast.Plugins.replyPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.replyPM>) e nem [Firecast.Plugins.replyPMFailure](<BibliotecaFirecastPlugins.md#rrpg.plugins.replyPMFailure>) faz com que o Firecast não libere os recursos envolvidos na comunicação, tornando seu plug-in um "devorador de memória RAM" ao longo do tempo.

&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.Plugins.replyPM(message, data) |
| --- |


&nbsp;

Envia uma resposta ao remetente da mensagem inter-plugin.

&nbsp;

Parâmetros:

* &nbsp;
  * message - A mensagem que deseja responder. Esta informação é a mesma que foi recebida no primeiro parâmetro da função callback da escuta (ver [Firecast.Plugins.listenPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.listenPM>)).
  * data - O conteúdo da resposta. Pode ser um número, uma cadeia de caracteres, um booleano ou uma tabela lua. Esta informação será repassada no primeiro parâmetro da função "callback" de quem enviou a mensagem (ver [Firecast.Plugins.sendPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.sendPM>))

&nbsp;

&nbsp;

&nbsp;

| **function** Firecast.Plugins.replyPMFailure(message, data) |
| --- |


&nbsp;

Envia uma resposta de FALHA ao remetente da mensagem inter-plugin.

&nbsp;

Parâmetros:

* &nbsp;
  * message - A mensagem que deseja responder. Esta informação é a mesma que foi recebida no primeiro parâmetro da função callback da escuta (ver [Firecast.Plugins.listenPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.listenPM>)).
  * data - O conteúdo da resposta. Pode ser um número, uma cadeia de caracteres, um booleano ou uma tabela lua. Esta informação será repassada no primeiro parâmetro da função "failureCallback" de quem enviou a mensagem (ver [Firecast.Plugins.sendPM](<BibliotecaFirecastPlugins.md#rrpg.plugins.sendPM>)

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Keep Your PDFs Safe from Unauthorized Access with These Security Measures](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
