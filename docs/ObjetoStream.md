# Objeto Stream

# Objeto Stream

Um objeto stream contém uma sequência de dados genéricos, possui um início e um fim e você estará sempre em algum lugar entre estes dois pontos.

Usando stream, você pode ler e/ou escrever em vários tipos de armazenamentos, como um arquivo, uma memória dinâmica, etc..

&nbsp;

Um stream representa uma sequência de BYTES que podem ser acessadas de forma sequencial ou aleatória (isto é, você pode ler o inicio de um stream, pular para seu final para ler mais dados, voltar ao meio do stream, etc..)

&nbsp;

Exemplos de operações típicas em um stream:

* &nbsp;
  * Ler 1 byte. Da próxima vez que você ler, você obterá o byte posterior, e assim por diante.
  * Ler vários bytes
  * Mover a posição atual do cursor no stream para, da próxima vez que você ler, obter os bytes à partir desta nova posição.
  * Escrever 1 byte.
  * Escrever vários bytes.

&nbsp;

### Formas de instanciar um objeto stream

Existem várias maneiras de obter um objeto stream. Algumas delas são:

&nbsp;

* &nbsp;
  * Criar um stream temporário que reside na memória RAM através da função [utils.newMemoryStream](<BibliotecaUtils.md#utils.newMemoryStream>)
  * Criar um stream temporário que reside no HD do dispositivo através da função [utils.newTempFileStream](<BibliotecaUtils.md#newTempFileStream>)
  * Abrir ou criar um arquivo no HD virtual usando a função [vhd.openFile](<BibliotecaVHD.md#vhd.openFile>)
  * Baixar um conteúdo da internet através da função [internet.download](<BibliotecaInternet.md#internet.download>)
  * Realizar uma requisição HTTP e obter a resposta através da propriedade [responseStream do objeto HTTPRequest](<ObjetoHTTPRequest.md#propriedade%20responseStream>)

&nbsp;

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **size** | Integer | Contém o tamanho atual do stream em quantidade de bytes.&nbsp; |
| **position** | Integer | A posição do cursor do stream. onde o valor 0 representa o primeiro byte do stream.&nbsp; Todas as operações de leitura e escrita são feitas nesta posição.&nbsp; |
| **remainingBytes** | Integer | Quantos bytes ainda podem ser lidos no stream à partir da posição atual.&nbsp; |
| **md5** | String | Uma cadeia de caracteres contendo o Hash MD5 de todo o conteúdo do stream. O Hash é calculado na hora de obter o valor da propriedade.&nbsp; |
| **sha1** | String | Uma cadeia de caracteres contendo o Hash SHA1 de todo o conteúdo do stream. O Hash é calculado na hora de obter o valor da propriedade.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **stream:read(destArray, qtBytes)** | Efetua a leitura de bytes à partir da [position](<ObjetoStream.md#stream.position>) atual do stream. &nbsp; Parâmetros: destArray - Uma tabela lua que receberá os bytes lidos do stream. Os valores são armazenados em índices de 1 a N, onde N = quantidade de bytes lidos. qtBytes - Um número contendo a quantidade de bytes que devem ser lidos à partir desta posição.&nbsp; Retorno: Um número contendo quantos bytes realmente foram lidos do stream e preenchidos em destArray&nbsp; Importante: A position do stream é avançada automaticamente após a chamada desta função conforme a quantidade de bytes lidos. Nem sempre é possível ler a quantidade de bytes informada no parâmetro qtBytes. Você DEVE analisar o número retornado pela função a fim de saber quantos bytes realmente foram lidos.&nbsp; |
| **stream:write(sourceArray \[, qtBytes\])** | Efetua a escrita de bytes na [position](<ObjetoStream.md#stream.position>) atual do stream.&nbsp; Parâmetros: sourceArray - Uma tabela lua que contém os bytes que devem ser escritos no stream. Os valores devem estar armazenados em índices de 1 a N, onde N = quantidade de bytes que serão escritos. (OPCIONAL) qtBytes - Quantos bytes do sourceArray devem ser escritos no stream. Se omitido, o length do array (#sourceArray) será usado.&nbsp; Retorno: Um número contendo quantos bytes realmente foram escritos no stream.&nbsp; Importante: A position do stream é avançada automaticamente após a chamada desta função conforme a quantidade de bytes escritos. Os valores em sourceArray devem ser números\! Para cada valor em sourceArray, se for menor que 0, o byte 0 será gravado e se for maior que 255, o byte 255 será gravado. Se em algum dos índices de sourceArray não contiver um número válido, o byte 0 é escrito no stream.&nbsp; |
| **stream:close()** | Fecha o stream imediatamente e libera os recursos que foram previamente alocados. Após esta chamada, nenhuma operação do stream estará mais disponível.&nbsp; |
| **stream:writeBinary(format, valor1 \[, valor2 \[, valor3 \[, valorN...\]\]\])** | Escreve um valor codificado em binário na posição atual do stream.&nbsp; Parâmetros: format - Cadeia de caracteres identificando qual formatação binária deve ser usada. Veja [Formatos Binários](<BibliotecaUtils.md#Formatos%20Binários%20utils.binaryEncode>) para saber quais são os possíveis formatos. valor1 - O valor a ser codificado e escrito (OPCIONAL) valor2, valor3, valorN, etc... - Outros valores que também devem ser codificados e escritos no stream.&nbsp; Retorno: Um número contendo quantos bytes foram escritos no stream.&nbsp; Importante: A position do stream é avançada automaticamente após a chamada desta função conforme a quantidade de bytes escritos.&nbsp; |
| **stream:readBinary(format \[, qt\])** | Efetua a leitura de valores codificados em binário na posição atual do stream.&nbsp; Parâmetros: format - Cadeia de caracteres identificando em qual formatação binária o valor está codificado. Veja [Formatos Binários](<BibliotecaUtils.md#Formatos%20Binários%20utils.binaryEncode>) para saber quais são os possíveis formatos. (OPCIONAL) qt - Um número identificando QUANTOS valores codificados devem ser lidos. Se omitido, o valor 1 será utilizado.&nbsp; Retorno: Retorna os valores decodificados ou nil se não foi possível decodificar.&nbsp; Importante: A position do stream é avançada automaticamente após a chamada desta função conforme a quantidade de bytes lidos Se especificado os formatos "ansi', "utf8" ou "utf16", todo o restando do stream é lido como uma cadeia de caracteres e o parâmetro "qt" é ignorado como se o valor 1 tivesse sido passado para ele.&nbsp; |
| **stream:readAsBase64(\[qtBytes\])** | Lê bytes do stream e retorna uma cadeia de caracteres representando os dados codificados em Base64.&nbsp; Parâmetros: (OPCIONAL) qtBytes - Um número definindo quantos bytes do stream devem ser lidos à partir da posição atual e codificados. Se omitido, o restante dos dados do stream será lido.&nbsp; Retorno: Uma cadeia de caracteres representando os dados codificados em Base64&nbsp; |
| **stream:writeBase64(str)** | Decodifica dados previamente codificados em Base64 e os escreve na posição atual do stream.&nbsp; Parâmetros: str - Uma cadeia de caracteres contendo os dados codificados em Base64.&nbsp; Retorno: Um número contendo quantos bytes foram escritos no Stream.&nbsp; |
| **stream:copyFrom(stream, qtBytes)** | Copia o conteúdo de um outro objeto stream dentro deste stream.&nbsp; Parâmetros: stream - um [objeto stream](<ObjetoStream.md>) de onde os dados serão copiados. qtBytes - um número representando quantos bytes serão copiados à partir da posição atual do parâmetro "stream".&nbsp; Retorno: Um número contendo quantos bytes realmente foram copiados para este stream.&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - .....

&nbsp;

| &nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Effortlessly upgrade your WinHelp HLP help files to CHM with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
