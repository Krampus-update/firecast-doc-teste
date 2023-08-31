# Biblioteca Internet

# Biblioteca Internet

Biblioteca que contém funções relacionadas à internet/intranet, como: downloads, requisições HTTP, etc..

Todas as funções estão contidas na unidade "internet.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "internet.lua"* require("internet.lua");    *-- Agora é possível acessar as funções da biblioteca* Internet.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca internet

&nbsp;

| **function** Internet.download(url \[, finishCallback \[, errorCallback \[, progressCallback \[, cacheMode\]\]\]\]) |
| --- |


&nbsp;

Realiza o download de um arquivo da internet.

&nbsp;

Parâmetros:

* &nbsp;
  * url&nbsp; - Cadeia de caracteres contendo a URL do arquivo (Exemplo: http://www.site.com.br/pasta/arquivo.png).&nbsp;
    * URL de arquivos que estão na internet devem começar com "http://" ou "https://"
    * Endereços de arquivos que estão localizados no [HD virtual do plug-in](<HDVirtual.md>) também são aceitos.\
&nbsp;
  * (OPCIONAL) finishCallback - Uma função que será invocada quando o download estiver terminado. Esta função recebe os seguintes 2 parâmetros:&nbsp;
    * stream - Um [objeto Stream](<ObjetoStream.md>) possuindo o conteúdo do arquivo baixado. Importante: O Firecast libera o conteúdo da stream após a chamada da função finishCallback.
    * contentType - Uma cadeia de caracteres identificando o MimeType/tipo do conteúdo.. Exemplos: "application/octet-stream", "image/png", "text/html", etc..\
&nbsp;
  * (OPCIONAL) errorCallback - Uma função que será invocada se ocorrer algum erro no download. A Mensagem de erro é passada no primeiro parâmetro desta função.\
&nbsp;
  * (OPCIONAL) progressCallback - Uma função que será invocada várias vezes para informar o progresso do download. Esta função recebe 2 parâmetros:
    * downloadedBytes - Quantos bytes já foram baixados.
    * totalBytes - Quantos bytes o arquivo possui no total.\
&nbsp;
  * (OPCIONAL) cacheMode - Pode ser passado um dos seguintes valores e significados:
    * "alwaysUseCache" - Se o arquivo já existir no cache, o Firecast irá retornar o conteúdo sem mesmo se comunicar com a internet. Este é o modo **padrão**.
    * "checkForModification" - Se o arquivo já existir no cache, o Firecast irá verificar no servidor remoto se houve alterações no conteúdo antes de decidir usar o cache local ou baixar o conteúdo.
    * "alwaysDownload" - O Firecast não usará o cache local e sempre baixará o conteúdo do servidor remoto.

&nbsp;

Retorno:

* &nbsp;
  * A função retorna um identificador de download. Este valor pode ser utilizado para invocar o método [Internet.stopDownload](<BibliotecaInternet.md#internet.stopDownload>) caso queira abortar o download.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * A função não espera o download terminar e continua a execução do código enquanto o download é feito em paralelo.
  * Para ter acesso ao conteúdo baixado, utilize o parâmetro finishCallback.
  * Invocar esta função faz com que a URL seja enfileirada no gerenciador de downloads do Firecast, e, portanto, o download pode passar por uma espera antes de realmente começar.
  * Retornar explicitamente "false" na função progressCallback faz com que o download seja abortado.
  * Este método utiliza um sistema de cache de arquivos para evitar usar a internet com arquivos que já foram recentemente baixados.
  * Se o arquivo estiver pronto no sistema de cache de arquivos, a função "finishCallback" poderá ser invocada imediatamente, antes mesmo da função "Internet.download" retornar.
  * Este método, quando possível, faz "resume", isto é, ele consegue fazer download à partir de um ponto que havia parado recentemente.

&nbsp;

&nbsp;

Exemplo 1:

| Internet.download("http://www.rrpg.com.br/arquivo.png",         **function**(stream, contentType)                 *-- esta função será chamada quando o download terminar*                 *-- o conteúdo do arquivo baixado está em stream.*         **end**,                **function** (errorMsg)                 *-- esta função será chamada quando ocorrer algum erro no download.*                 *-- errorMsg possui a msg de erro*         **end**,                **function** (downloaded, total)                 *-- esta função será chamada constantemente.*                 *-- dividir "downloaded" por "total" lhe dará uma porcentagem do download.*         **end**); |
| --- |


&nbsp;

&nbsp;

&nbsp;

Exemplo 2 - checkForModification&nbsp;

| Internet.download("http://www.rrpg.com.br/arquivo.png",         **function**(stream, contentType)                 *-- esta função será chamada quando o download terminar*                 *-- o conteúdo do arquivo baixado está em stream.*         **end**,                **function** (errorMsg)                 *-- esta função será chamada quando ocorrer algum erro no download.*                 *-- errorMsg possui a msg de erro*         **end**,                **function** (downloaded, total)                 *-- esta função será chamada constantemente.*                 *-- dividir "downloaded" por "total" lhe dará uma porcentagem do download.*         **end,** "checkForModification"); |
| --- |


&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

| **function** Internet.stopDownload(downloadId) |
| --- |


&nbsp;

Aborta um download que foi iniciado pela função [Internet.download](<BibliotecaInternet.md#internet.download>)

&nbsp;

Parâmetros:

* &nbsp;
  * downloadId - a identificação do download a ser abortado. Este valor é retornado pela função Internet.download

&nbsp;

&nbsp;

| **function** Internet.newHTTPRequest(\[method \[, url\]\]) |
| --- |


&nbsp;

Cria e retorna um [objeto HTTPRequest](<ObjetoHTTPRequest.md>), usado para troca de dados com um servidor através de protocolo HTTP ou HTTPS.

&nbsp;

Parâmetros:

* &nbsp;
  * (OPCIONAL) method - Uma cadeia de caracteres identificando o método/verbo HTTP utilizado nesta requisição. Os valores aceitos são:
    * "GET" (valor padrão, se o parâmetro for omitido)
    * "POST"
    * "PUT"
    * "PATCH"
    * "TRACE"
    * "HEAD"
    * "OPTIONS"
    * "DELETE"
  * (OPCIONAL) url - A URL da requisição HTTP. Este valor pode ser alterado posteriormente no [objeto HTTPRequest.](<ObjetoHTTPRequest.md>)

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto HTTPRequest](<ObjetoHTTPRequest.md>) representando a requisição.

&nbsp;

Observações:

* &nbsp;
  * As requisições HTTP são permitidas apenas se o usuário do Firecast for um membro Gold.
  * Esta função apenas cria o objeto HTTPRequest e não a envia. Você deve utilizar o método "send" do objeto para, de fato, enviar a requisição.

&nbsp;

&nbsp;

| **function** Internet.httpEncode(str) |
| --- |


&nbsp;

Codifica um texto para que possa ser usado como URL em requisições HTTP.&nbsp;

&nbsp;

Parâmetros:

* &nbsp;
  * str - A cadeia de caracteres que deseja codificar.

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres contendo o texto codificado.

&nbsp;

&nbsp;

&nbsp;

| **function** Internet.httpDecode(str) |
| --- |


&nbsp;

Decodifica os caracteres/códigos de URL contidas no texto passado.

&nbsp;

Parâmetros:

* &nbsp;
  * str - A cadeia de caracteres que deseja decodificar.

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres contendo o texto decodificado.

***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Convert Your Word Doc to an eBook: A Step-by-Step Guide](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
