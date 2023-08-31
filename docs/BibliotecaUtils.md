# Biblioteca Utils

# Biblioteca Utils

A biblioteca gui provê funções relacionadas às interfaces Lua Form.

Todas as funções estão contidas na unidade "utils.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "utils.lua"* require("utils.lua");    *-- Agora é possível acessar as funções da biblioteca* Utils.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); FUNCAO\_DA\_BIBLIOTECA2(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca utils
## &nbsp;

&nbsp;

| **function** clearInterval(intervalId) ou **function** Utils.clearInterval(intervalId) |
| --- |


&nbsp;

Cancela o temporizador que [setInterval](<BibliotecaUtils.md#função%20setInterval>) havia previamente configurado.

&nbsp;

Parâmetros:

* &nbsp;
  * intervalId - O identificador retornado pela função setInterval.

&nbsp;

&nbsp;

| **function** clearTimeout(timeoutId) ou **function** Utils.clearTimeout(timeoutId) |
| --- |


&nbsp;

Cancela o temporizador que [setTimeout](<BibliotecaUtils.md#função%20setTimeout>) havia previamente configurado.

&nbsp;

Parâmetros:

* &nbsp;
  * timeoutId - O identificador retornado pela função setTimeout.

&nbsp;

&nbsp;

| **function** Utils.compareStringPtBr(strLeft, strRight) |
| --- |


&nbsp;

Realiza comparação entre duas cadeias de caracteres de forma case-insensitive e ignorando acentuações

&nbsp;

Retorna:

* &nbsp;
  * Número **menor** que 0 se strLeft for lexicograficamente **menor** que strRight
  * &#48; se strLeft for lexicograficamente **igual** a strRight
  * Número **maior** que 0 se strLeft for lexicograficamente **maior** que strRight

&nbsp;

| **function** lowercase(str) |
| --- |


&nbsp;

Converte e retorna um string em caixa baixa (lower case)

&nbsp;

Parâmetros:

* &nbsp;
  * str - a cadeia de caracteres que deseja converter para caixa baixa.

&nbsp;&nbsp; &nbsp;

Retorno:&nbsp;

* &nbsp;
  * uma cadeia de caracteres

&nbsp;

| **function** uppercase(str) |
| --- |


&nbsp;

Converte e retorna um string em caixa alta (upper case)

&nbsp;

Parâmetros:

* &nbsp;
  * str - a cadeia de caracteres que deseja converter para caixa alta.

&nbsp;&nbsp; &nbsp;

Retorno:&nbsp;

* &nbsp;
  * uma cadeia de caracteres

&nbsp;

&nbsp;

| **function** Utils.generateUniqueString() |
| --- |


&nbsp;

Gera e retorna uma cadeia de caracteres globalmente única, isto é, um texto que nunca mais será gerado novamente por esta função

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres única, ótima para ser usada como identificador.

&nbsp;

&nbsp;

&nbsp;

| **function** isnumber(value) ou **function** isNumber(value) |
| --- |


&nbsp;

Retorna true se o parâmetro "value" for um número, senão retorna false.

&nbsp;

&nbsp;

| **function** round(value) |
| --- |


&nbsp;

Arredonda "value" para o numero inteiro mais próximo e o retorna.

&nbsp;

&nbsp;

| **function** removerAcentos(str) ou **function** Utils.removerAcentos(str) |
| --- |


&nbsp;

Retorna o texto passado em "str" sem sua acentuação.

&nbsp;

&nbsp;

| **function** Utils.removerFmtChat(str\[, removerSmileys\]) |
| --- |


&nbsp;

Retorna o texto passado em "str" sem os caracteres de formatação de cores/negrito/itálico que o RRPG aceita no chat.

&nbsp;

Parâmetros:

* &nbsp;
  * str - Cadeia de caracteres contendo o texto a ser processado
  * (OPCIONAL) removerSmileys - Booleano indicando se deve remover os smileys/memes do texto também. Se omitido, o valor padrão é false.

&nbsp;

Retorno:

* &nbsp;
  * Cadeia de caracteres sem as tags de formatação.

&nbsp;

&nbsp;

| **function** setInterval(callbackFunction, interval \[, parametersToCallbackFunction\]) ou **function** Utils.setInterval(callbackFunction, interval \[, parametersToCallbackFunction\]) |
| --- |


&nbsp;

setInterval chama uma função qualquer após em intervalos de tempo especificado em milisegundos.

&nbsp;

Parâmetros:

* &nbsp;
  * callbackFunction - A função que será chamada no intervalo definido.
  * interval - O intervalo de tempo em milisegundos que callbackFunction será chamada.
  * (OPCIONAL) parametersToCallbackFunction - Uma lista de parâmetros que serão repassados para a callbackFunction quando ela for chamada.

&nbsp;

Retorno:

* &nbsp;
  * Retorna um valor que poderá ser usado na função [clearInterval](<BibliotecaUtils.md#função%20clearInterval>) para cancelar o setInterval.

&nbsp;

Observações:

* &nbsp;
  * A função "callbackFunction" é executada inúmeras vezes até que algum dos seguintes eventos aconteça:
    * O plug-in seja descarregado.
    * A função [clearInterval](<BibliotecaUtils.md#função%20clearInterval>) seja executada passando em seu parâmetro o valor retornado por setInterval.
    * A função informada em "callbackFunction" retorne explicitamente false.
  * &nbsp;Se você deseja executar "callbackFunction" apenas uma vez após um determinado tempo, use a função [setTimeout](<BibliotecaUtils.md#função%20setTimeout>).

&nbsp;

| **function** setTimeout(callbackFunction, interval \[, parametersToCallbackFunction\]) ou **function** Utils.setTimeout(callbackFunction, interval \[, parametersToCallbackFunction\]) |
| --- |


&nbsp;

setTimeout chama uma função qualquer após uma quantidade específica de milisegundos se passarem.

&nbsp;

Parâmetros:

* &nbsp;
  * callbackFunction - A função que será chamada.
  * interval - O tempo de espera até que a função seja chamada, em milisegundos.
  * (OPCIONAL) parametersToCallbackFunction - Uma lista de parâmetros que serão repassados para a callbackFunction quando ela for chamada.

&nbsp;

Retorno:

* &nbsp;
  * Retorna um valor que poderá ser usado na função [clearTimeout](<BibliotecaUtils.md#função%20clearTimeout>) para prevenir a função "callbackFunction" de ser chamada.

&nbsp;

Observações:

* &nbsp;
  * A função "callbackFunction" é executada somente 1 vez. Se você precisar que ela seja chamada constantemente, use a função [setInterval](<BibliotecaUtils.md#função%20setInterval>)

&nbsp;

&nbsp;

&nbsp;

| **function** Utils.sortPtBrArray(array) |
| --- |


&nbsp;

Dado um array de strings (uma tabela lua indexada de 1 a n), ordena os valores lexicograficamente de forma case insensitive e ignorando acentuações.

&nbsp;

Retorno:

* &nbsp;
  * Não há retorno. O próprio array estará ordenado no fim desta função.

&nbsp;

| **function** totable(str) ou **function** strToTable(str) ou **function** Utils.strToTable(str) |
| --- |


&nbsp;

Converte o texto passado em "str" para uma tabela lua. O texto deve seguir o mesmo padrão que você usa ao declarar uma tabela lua quando está programando.&nbsp;

Exemplo: "{nome='joão', idade=10, filhos={}}"

&nbsp;

&nbsp;

| **function** tableToStr(table \[, pretty\]) ou **function** Utils.tableToStr(table \[, pretty\]) |
| --- |


&nbsp;

Converte uma tabela LUA para string.

&nbsp;

Parâmetros:

* &nbsp;
  * table - a tabela lua que deseja converter para texto
  * (OPCIONAL) pretty - se true, converte para um texto legível... Se omitido ou se false, converte para um texto que ocupa o menor espaço o possível.

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres que corresponde à tabela.

&nbsp;

&nbsp;

&nbsp;

| **function** Utils.binaryEncode(destArray, format, value \[, startIndex\]) |
| --- |


&nbsp;

Codifica um determinado valor em um formato binário.

&nbsp;

Parâmetros:

* &nbsp;
  * destArray - Uma tabela lua que receberá os BYTES da codificação binária.
  * format - Uma cadeia de caracteres identificando qual o formato binário deve ser utilizado. Veja [Formatos Binários](<BibliotecaUtils.md#Formatos%20Binários%20utils.binaryEncode>) para saber quais são os formatos disponíveis.
  * value - O valor que será codificado.
  * (OPCIONAL) startIndex - Um número identificando em qual posição de "destArray" os bytes devem ser escritos. Se omitido, o valor 1 será utilizado.

&nbsp;

Retorno:

* &nbsp;
  * Um número contendo quantos bytes foram inseridos em destArray.

&nbsp;

Observações:

* &nbsp;
  * Cada BYTE da representação binária é colocado em uma posição de "destArray". Se um determinado formato binário ocupar 4 bytes, após a chamada da função destArray\[1\] conterá o valor do primeiro byte, destArray\[2\] o valor do segundo byte, destArray\[3\] o valor do terceiro byte e destArray\[4\] o valor do quarto byte.

&nbsp;

&nbsp;

Formatos Binários:

&nbsp;

| **Formato** | Qtd. de Bytes | Descrição |
| --- | --- | --- |
| **"u8"** | &#49; | Um número entre 0 e 255 codificado como Unsigned Integer de 8 Bits (também conhecido como Byte)&nbsp; |
| **"s8"** | &#49; | Um número entre -128 a 127 codificado como Signed Integer de 8 Bits.&nbsp; |
| **"u16"** | &#50; | Um número entre 0 e 65535 codificado como Unsigned Integer de 16 bits (Também conhecido como Word) no padrão LittleEndian.&nbsp; &nbsp; |
| **"s16"** | &#50; | Um número entre -32768 e 32767 codificado como Signed Integer de 16 bits no padrão LittleEndian.&nbsp; |
| **"u32"** | &#52; | Um número entre 0 e 4294967295 codificado como Unsigned Integer de 32 bits (Também conhecido como DoubleWord) no padrão LittleEndian.&nbsp; |
| **"s32"** | &#52; | Um número entre -2147483648 e 2147483647 codificado como Signed Integer de 32 bits no padrão LittleEndian &nbsp; |
| **"u64"** | &#56; | Um número entre 0 e (2\^64) - 1 codificado como Unsigned Integer de 64 bits (Também conhecido como QuadWord) no padrão LittleEndian&nbsp; |
| **"s64"** | &#56; | Um número entre -2\^63 a (2\^63) - 1 codificado como Signed Integer de 64 bits no padrão LittleEndian.&nbsp; |
| **"float"** | &#52; | Um número de ponto flutuante de 4 bytes no padrão IEEE 754.&nbsp; |
| **"double"** | &#56; | Um número de ponto flutuante de 8 bytes no padrão IEEE 754.&nbsp; |
| **"ansi"** | Varia | Uma cadeia de caracteres codificada em ANSI sem o terminador nulo.&nbsp; |
| **"utf8"** | Varia | Uma cadeia de caracteres codificada em UTF-8 sem o terminador nulo.&nbsp; |
| **"utf16"** | Varia | Uma cadeia de caracteres codificada em UTF-16 sem o terminador nulo.&nbsp; |


&nbsp;

&nbsp;

| **function** Utils.binaryDecode(sourceArray, format \[, startIndex \[, length\]\]) |
| --- |


&nbsp;

Interpreta um valor que está codificado em um formato binário.

&nbsp;

Parâmetros:

* &nbsp;
  * sourceArray - Uma tabela lua que contém os BYTES da codificação binária.
  * format - Uma cadeia de caracteres identificando em qual formato binário o valor está codificado. Veja [Formatos Binários](<BibliotecaUtils.md#Formatos%20Binários%20utils.binaryEncode>) para saber quais são.
  * (OPCIONAL) startIndex - Um número identificando a partir de qual posição de "sourceArray" os bytes devem ser lidos para a decodificação. Se omitido, o valor 1 será utilizado.
  * (OPCIONAL) length - Quantos bytes à partir de "startIndex" devem ser usados para a decodificação. Se omitido, o valor (#sourceArray - startIndex + 1) será utilizado.

&nbsp;

&nbsp;

Retorno:

* &nbsp;
  * A função retorna 2 valores:
    * O valor decodificado ou **nil** se não foi possível decodificar
    * A quantidade de bytes usados para a decodificação do valor.

&nbsp;

Observações:

* &nbsp;
  * Cada BYTE da representação binária deve estar em uma posição de "sourceArray". Se um determinado formato binário ocupar 4 bytes, sourceArray\[1\] deve conter o valor do primeiro byte, sourceArray\[2\] o valor do segundo byte, sourceArray\[3\] o valor do terceiro byte e sourceArray\[4\] o valor do quarto byte.

&nbsp;

&nbsp;

| **function** Utils.getBinarySize(format) |
| --- |


&nbsp;

Retorna quantos bytes um determinado formato binário ocupa.

&nbsp;

Parâmetros:

* &nbsp;
  * format - Uma cadeia de caracteres identificando o formato binário que deseja consultar. Veja [Formatos Binários](<BibliotecaUtils.md#Formatos%20Binários%20utils.binaryEncode>) para saber quais são.

&nbsp;

Retorno:

* &nbsp;
  * Um número identificando a quantidade de bytes um determinado formato binário ocupa. Se um formato binário ocupar uma quantidade variada de bytes, o valor -1 é retornado.

&nbsp;

&nbsp;

| **function** Utils.zlibCompress(sourceStream, destStream, \[, level \[, qtBytesInSource\]\]) |
| --- |


&nbsp;

Lê dados de um [objeto stream](<ObjetoStream.md>) fonte e, usando a biblioteca zLib, o compacta escrevendo o resultado em outro [objeto stream](<ObjetoStream.md>).

&nbsp;

Parâmetros:

* &nbsp;
  * sourceStream - Um [objeto stream](<ObjetoStream.md>) representando os dados a serem compactados.
  * destStream - Um [objeto stream](<ObjetoStream.md>) que receberá o conteúdo compactado.
  * (OPCIONAL) level - Define o nível da compactação. Pode ser
    * "none" - Não haverá compactação no final das contas
    * "fastest" - Compactação rápida
    * "default" - Modo em que balanceia velocidade e taxa de compressão. Este é o modo padrão quando não for definido o nível.
    * "max" - Modo com maior taxa de compressão.
  * (OPCIONAL) qtBytesInSource - Quantos bytes serão lidos de "sourceStream" à partir de sua posição atual para a compactação. Quando não definido, todo o restante do sourceStream será lido para a compactação.

&nbsp;

Retorno:

* &nbsp;
  * Um número identificando quantos bytes foram escritos em destStream

&nbsp;

&nbsp;

| **function** Utils.zlibDecompress(sourceStream, destStream) |
| --- |


&nbsp;

Lê dados de um [objeto stream](<ObjetoStream.md>) fonte e, usando o a biblioteca zLib, o descompacta escrevendo o resultado em outro [objeto stream](<ObjetoStream.md>).

&nbsp;

Parâmetros:

* &nbsp;
  * sourceStream - Um [objeto stream](<ObjetoStream.md>) contendo os dados a serem descompactados.
  * destStream - Um [objeto stream](<ObjetoStream.md>) que receberá o conteúdo descompactado.

&nbsp;

Observações:

* &nbsp;
  * Esta função descompacta um "bloco compactado" por completo. Não tem como antecipar quantos bytes serão lidos de "sourceStream" nem quantos bytes serão escritos em "destStream" utilizando esta função. No fim da chamada, destStream conterá todo o dado descompactado e a posição de "sourceStream" apontará para o primeiro byte subsequente do conteúdo que foi processado.

&nbsp;

Retorno:

* &nbsp;
  * Um número identificando quantos bytes foram escritos em destStream

&nbsp;

&nbsp;

&nbsp;

| **function** Utils.zlibCompressAsync(sourceStream, destStream, level, qtBytesInSource, onFinishCallback, onErrorCallback) |
| --- |


&nbsp;

Lê dados de um [objeto stream](<ObjetoStream.md>) fonte e, usando a biblioteca zLib, o compacta escrevendo o resultado em outro [objeto stream](<ObjetoStream.md>).

A compactação se dá de forma assíncrona, isto é, em "background". Ótimo para compactar streams grandes e não "congelar" o programa durante o processo.

&nbsp;

Parâmetros:

* &nbsp;
  * sourceStream - Um [objeto stream](<ObjetoStream.md>) representando os dados a serem compactados.
  * destStream - Um [objeto stream](<ObjetoStream.md>) que receberá o conteúdo compactado.
  * level - Define o nível da compactação. Pode ser
    * "none" - Não haverá compactação no final das contas
    * "fastest" - Compactação rápida
    * "default" - Modo em que balanceia velocidade e taxa de compressão. Este é o modo padrão quando não for definido o nível.
    * "max" - Modo com maior taxa de compressão.
  * qtBytesInSource - Quantos bytes serão lidos de "sourceStream" à partir de sua posição atual para a compactação.
  * onFinishCallback - Uma função que será invocada quando a compactação finalizar.
  * onErrorCallback&nbsp; - Uma função que será invocada quando a compactação retornar um erro. A mensagem de erro é passada no primeiro parâmetro desta função.

&nbsp;

Observações:

* &nbsp;
  * IMPORTANTE: Durante a compactação assíncrona, seu código não deve fazer nenhuma operação em sourceStream e nem em destStream, senão o planeta explodirá e 2d6 erros estranhos surgirão.

&nbsp;

&nbsp;

| **function** Utils.zlibDecompressAsync(sourceStream, destStream, onFinishCallback, onErrorCallback) |
| --- |


&nbsp;

Lê dados de um [objeto stream](<ObjetoStream.md>) fonte e, usando o a biblioteca zLib, o descompacta escrevendo o resultado em outro [objeto stream](<ObjetoStream.md>).

A descompactação se dá de forma assíncrona, isto é, em "background". Ótimo para descompactar streams grandes e não "congelar" o programa durante o processo.

&nbsp;

Parâmetros:

* &nbsp;
  * sourceStream - Um [objeto stream](<ObjetoStream.md>) contendo os dados a serem descompactados.
  * destStream - Um [objeto stream](<ObjetoStream.md>) que receberá o conteúdo descompactado.
  * onFinishCallback - Uma função que será invocada quando a descompactação finalizar.
  * onErrorCallback&nbsp; - Uma função que será invocada quando a descompactação retornar um erro. A mensagem de erro é passada no primeiro parâmetro desta função.

&nbsp;

Observações:

* &nbsp;
  * Esta função descompacta um "bloco compactado" por completo. Não tem como antecipar quantos bytes serão lidos de "sourceStream" nem quantos bytes serão escritos em "destStream" utilizando esta função. No fim da chamada, destStream conterá todo o dado descompactado e a posição de "sourceStream" apontará para o primeiro byte subsequente do conteúdo que foi processado.
  * IMPORTANTE: Durante a descompactação assíncrona, seu código não deve fazer nenhuma operação em sourceStream e nem em destStream, senão o planeta explodirá e 2d6 erros estranhos surgirão.

&nbsp;

&nbsp;

| **function** Utils.newMemoryStream() |
| --- |


&nbsp;

Cria e retorna um [objeto stream](<ObjetoStream.md>) que armazena os dados na memória RAM do dispositivo.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Os dados armazenados no Memory Stream não são salvos em nenhum lugar e são perdidos quando o código não mais estiver usando o Stream ou quando o RRPG fechar.
  * Ótimo para fazer processamento de dados temporários.
  * Enquanto estiver em uso, os dados ocupam memória RAM do dispositivo.

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto stream](<ObjetoStream.md>)

&nbsp;

&nbsp;

| **function** Utils.newTempFileStream() |
| --- |


&nbsp;

Cria e retorna um [objeto stream](<ObjetoStream.md>) que armazena os dados em um arquivo temporário no dispositivo do usuário.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Um arquivo temporário é criado no dispositivo do usuário e é automaticamente apagado quando não for mais utilizado.
  * Ótimo para fazer processamento de dados temporários.
  * Enquanto estiver em uso, os dados ocupam espaço de armazenamento do dispositivo (HD, SSD, Memory Card, etc..).

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto stream](<ObjetoStream.md>)

&nbsp;

&nbsp;

&nbsp;

| **function** tryFinally(tryCallback, finallyCallback) ou **function** Utils.tryFinally(tryCallback, finallyCallback) |
| --- |


&nbsp;

LUA não possui um operador try-finally para tratamento de exceções. Esta função é uma alternativa para o comportamento try-finally que o LUA não provê nativamente.

&nbsp;

Executa a função "tryCallback", e:&nbsp;

* &nbsp;
  * Se ocorrer algum erro na execução, a função "finallyCallback" é invocada e o erro é levantado logo após.
  * Se não ocorrer erro na execução, a função "finallyCallback" é invocada e a execução continua normalmente.

&nbsp;

Parâmetros:

* &nbsp;
  * tryCallback - Uma função que será invocada.
  * finallyCallback - Uma função que sempre será invocada após a execução de "tryCallback", mesmo havendo erros de execução.

&nbsp;

&nbsp;

&nbsp;

| **function** colorToRGBA(color) ou **function** Utils.colorToRGBA(color) |
| --- |


&nbsp;

Dado uma cor no formato [string de cor](<StringdecoresnoLuaForm.md>), retorna os tons de Red, Green, Blue e Alpha da cor

&nbsp;

Parâmetros:

* &nbsp;
  * Color - um [string de cor](<StringdecoresnoLuaForm.md>) contendo a cor que deseja decompor

&nbsp;

Retorno:

* &nbsp;
  * &#52; números representando, respectivamente os tons de Red, Green, Blue e Alpha da cor. Os tons são números entre 0.0 e 1.0

&nbsp;

&nbsp;

&nbsp;

| **function** RGBAToColor(r, g, b, a) ou **function** Utils.RGBAToColor(r, g, b, a) |
| --- |


&nbsp;

Dado tons de cores Red, Green, Blue e Alpha, retorna um [string de cor](<StringdecoresnoLuaForm.md>) que representa a cor.

&nbsp;

Parâmetros:

* &nbsp;
  * r - Tom de Red, número entre 0.0 e 1.0
  * g - Tom de Green, número entre 0.0 e 1.0
  * b - Tom de Blue, número entre 0.0 e 1.0
  * a - Tom de Alpha, número entre 0.0 e 1.0. Se omitido, o valor é considerado 1.0

&nbsp;

Retorno:

* &nbsp;
  * Um [string de cor](<StringdecoresnoLuaForm.md>)

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Revolutionize Your Documentation Output with HelpNDoc's Stunning User Interface](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
