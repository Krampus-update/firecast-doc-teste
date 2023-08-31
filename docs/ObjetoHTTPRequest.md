# Objeto HTTPRequest

# Objeto HTTPRequest

O Objeto HTTPRequest é utilizado para a troca de dados com um servidor usando protocolo HTTP ou HTTPS.

É excelente para integrar o plug-in com alguma api REST, baixar ou enviar informações para um servidor da World Wide Web.

&nbsp;

Para instanciar um Objeto HTTPRequest, utilize a função [internet.newHTTPRequest](<BibliotecaInternet.md#newHTTPRequest>)

### Restrições:

* &nbsp;
  * As requisições HTTP são permitidas apenas se o usuário do rrpg for um membro GOLD.

&nbsp;

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **url** | String | Define a URL para onde a requisição HTTP será direcionada.&nbsp; Exemplo:&nbsp; "http://www.google.com/xx/document.txt" "https://www.rrpg.com.br/apiexemplo"&nbsp; A URL deve iniciar com "http://" ou "https://"&nbsp; |
| **method** | String | Define o método/verbo HTTP que será utilizado na requisição.&nbsp; Os possíveis valores são: "GET" (padrão) "POST" "PUT" "PATCH" "TRACE" "HEAD" "OPTIONS" "DELETE"&nbsp; |
| **status** | Integer | Um número contendo o status da resposta http. (Exemplos: 200 para ok, 404 para não encontrado, etc..)&nbsp; Consulte [http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html](<http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html>) para saber quais são os possíveis status.&nbsp; |
| **statusText** | String | Uma cadeia de caracteres contendo o texto-status-resposta da requisição HTTP.&nbsp; Diferente da propriedade "status", este valor contém o texto completo da resposta (Exemplos: "200 OK", "404 NOT FOUND").&nbsp; |
| **responseText** | String | Contém o corpo da resposta interpretada como texto.&nbsp; O "charset" do cabeçalho de resposta "Content-Type" é levado em consideração antes de retornar o texto.&nbsp; |
| **responseStream** | [Objeto Stream](<ObjetoStream.md>) | Contém o corpo da resposta em um [objeto stream](<ObjetoStream.md>). Muito útil quando a resposta dada pelo servidor for binária.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **request:send(\[content\])** | Inicia o envio da requisição HTTP. Antes de chamar esta função, a URL e todos os cabeçalhos devem ser informados pela função [setRequestHeader](<ObjetoHTTPRequest.md#setRequestHeader>).&nbsp; Parâmetros: (OPCIONAL) content - Uma cadeia de caracteres ou um [objeto stream](<ObjetoStream.md>) contendo os dados que serão enviado ao servidor. Se não informado, a requisição é feita com corpo vazio.&nbsp; Observações: A requisição é assíncrona. Isto é, a função send retorna imediatamente e o código LUA continua sua execução normal enquanto a comunicação com o servidor é feita em segundo plano. Para obter a resposta, manipule os eventos onResponse e onError antes de chamar este método. Se o parâmetro content for uma cadeia de caracteres, o&nbsp; "charset" do cabeçalho de requisição "Content-Type" é levado em consideração para a codificação do texto.&nbsp; |
| **request:setRequestHeader(header, value)** | Altera o valor de um cabeçalho de requisição HTTP. Você deve enviar setRequestHeader antes de invocar o método [send](<ObjetoHTTPRequest.md#send>).&nbsp; Parâmetros: header - Cadeia de caracteres representando o nome do cabeçalho. Exemplos: "Content-Type" , "Content-Encoding", etc.. value - Cadeia de caracteres com o valor que deve ser associado ao cabeçalho.&nbsp; Observações: Para saber mais sobre os cabeçalhos HTTP, veja [http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html](<http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html>). Se este método for chamado várias vezes alterando o mesmo cabeçalho, o valor da última chamada prevalecerá.&nbsp; |
| **request:getRequestHeader(header)** | Obtém o valor de um cabeçalho de requisição HTTP.&nbsp; Parâmetros: header - cadeia de caracteres representando o nome do cabeçalho. Retorno: Uma cadeia de caracteres, contendo o valor do cabeçalho.&nbsp; |
| **request:getResponseHeader(header)** | Obtém o valor de um cabeçalho de resposta da requisição HTTP.&nbsp; Parâmetros: header - cadeia de caracteres representando o nome do cabeçalho de resposta. Retorno: Uma cadeia de caracteres, contendo o valor do cabeçalho, ou "" (cadeia de caracteres vazia) se o cabeçalho não existir na resposta. Para saber mais sobre os cabeçalhos HTTP, veja [http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html](<http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html>).&nbsp; |
| **request:getAllResponseHeaders()** | Retorna uma cadeia de caracteres contendo todos os cabeçalhos da resposta HTTP de uma só vez.&nbsp; |
| **request:abort();** | Aborta a requisição HTTP que está sendo feita.&nbsp; |
| **request:open(method, url);** | Inicializa a requisição HTTP&nbsp; Parâmetros: method - Uma cadeia de caracteres identificando o método/verbo HTTP utilizado nesta requisição. Os valores aceitos são: "GET"&nbsp; "POST" "PUT" "PATCH" "TRACE" "HEAD" "OPTIONS" "DELETE" url - A URL da requisição HTTP&nbsp; Observação: O uso deste método não é obrigatório. É apenas um "doce" para aqueles que estão acostumados com a requisição HTTP do JavaScript.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onResponse** | Este evento é invocado quando a requisição HTTP concluir sem erros. Após este evento, as propriedades de resposta estarão disponíveis no objeto (como, por exemplo, status, statusText, responseText, etc..).&nbsp; Observação: Se o servidor retornar status 4xx&nbsp; (algum erro de requisição) ou 5xx (algum erro do servidor), o evento "onError" será disparado ao invés de "onResponse"&nbsp; |
| **onError** | Este evento é disparado quando ocorrer um erro na requisição HTTP.&nbsp; Parâmetros: errorMsg - Uma cadeia de caracteres contendo informações sobre o erro.&nbsp; Observação: Se o servidor retornar status 4xx&nbsp; (algum erro de requisição) ou 5xx (algum erro do servidor), o evento "onError" será disparado ao invés de "onResponse"&nbsp; |
| **onReceiveProgress** | Evento que é disparado frequentemente a fim de informar o progresso de download da requisição HTTP.&nbsp; Parâmetros: currentBytes - Um número indicando quantos bytes já foram baixados maxBytes - Um número indicando quantos bytes serão baixados no final das contas.&nbsp; |
| **onSendProgress** | Evento que é disparado frequentemente a fim de informar o progresso de upload da requisição HTTP.&nbsp; Parâmetros: currentBytes - Um número indicando quantos bytes já foram enviados. maxBytes - Um número indicando quantos bytes serão enviados no final das contas.&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Baixar o "index.html" de um site.

&nbsp;

| require("internet.lua");  **local** requisicao = internet.newHTTPRequest("GET", "http://www.rrpg.com.br/");  requisicao.onResponse =         **function**()                 showMessage("Conteúdo: " .. requisicao.responseText);         **end**;  requisicao.onError =         **function**(errorMsg)                 showMessage("Ops\! Ocorreu algum erro: " .. errorMsg);         **end**;     requisicao:send(); |
| --- |


&nbsp;

&nbsp;

### Exemplo 2 - Fazer um upload de um arquivo, receber outro arquivo, rastreando o progresso.

&nbsp;

| require("internet.lua");  require("vhd.lua"); &nbsp; **local** requisicao = internet.newHTTPRequest("POST", "http://www.rrpg.com.br/REST\_API/URL");  requisicao.onResponse =         **function**()                 **local** streamResposta = requisicao.responseStream;                       **local** tipoRetornado = requisicao:getResponseHeader("Content-Type");                     **local** arquivoDestino;                                        **if** tipoRetornado == "image/png" **then**                         arquivoDestino = vhd.openFile("/baixado.png", "w+");                 **else**                         arquivoDestino = vhd.openFile("/baixado.outraExtensao", "w+");                 **end**;                                arquivoDestino:copyFrom(streamResposta, streamResposta.size);                 arquivoDestino:close();         **end**; requisicao.onError =         **function**(errorMsg)                 showMessage("Ops\! Ocorreu algum erro: " .. errorMsg);         **end**;           requisicao.onSendProgress =                 **function**(currentBytes, maxBytes)                         **local** porcentagem;                                                **if** maxBytes ~= 0 **then**                                 porcentagem = (currentBytes / maxBytes) \* 100;                         **else**                                 porcentagem = 0;                         **end**;                                                *--- porcentagem contém quantos % do arquivo já foram enviados*                 **end**;                requisicao.onReceiveProgress =                 **function**(currentBytes, maxBytes)                         **local** porcentagem;                                                **if** maxBytes ~= 0 **then**                                 porcentagem = (currentBytes / maxBytes) \* 100;                         **else**                                 porcentagem = 0;                         **end**;                                                *--- porcentagem contém quantos % do arquivo já foi recebido.*                 **end**;            **local** arquivoAEnviar = vhd.openFile("/arquivoExistente.png", "r");           requisicao:setRequestHeader("Content-Type", "image/png");       requisicao:send(arquivoAEnviar); |
| --- |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Revolutionize Your Documentation Output with HelpNDoc's Stunning User Interface](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
