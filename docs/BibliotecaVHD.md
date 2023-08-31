# Biblioteca VHD

# Biblioteca VHD

A biblioteca vhd provê funções para manipular o [HD Virtual](<HDVirtual.md>) do plug-in, como ler um arquivo, excluir, etc...

Todas as funções estão contidas na table/variável "VHD" da unidade "vhd.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "vhd.lua"* require("vhd.lua");    *-- Agora é possível acessar as funções da biblioteca* VHD.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca vhd

&nbsp;

| **function** VHD.copyFile(srcFileName, dstFileName) |
| --- |


&nbsp;

Copy the file in the virtual HD

&nbsp;

Arguments:

* &nbsp;
  * srcFileName - String containing the path to the existing source file
  * dstFileName - String containing the path of the new file

&nbsp;

Remarks:

* &nbsp;
  * The paths are expanded using “vhd.expandFileName” before copying.
  * If the file “dstFileName” already exists, it will be replaced by the copied file.

&nbsp;

&nbsp;

| **function** VHD.expandFileName(shortFileName) |
| --- |


&nbsp;

Expande o nome curto de um arquivo a fim de ter sua localização em relação à raiz do HD virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * shortFileName – o caminho encurtado de um arquivo&nbsp; a ser expandido.

&nbsp;&nbsp; &nbsp;

Retorno:

&nbsp; &nbsp; Uma cadeia de caracteres, onde:

* &nbsp;
  * Se a cadeia de caracteres passada pelo parâmetro shortFileName iniciar com o caractere “/”, a função simplesmente retorna o valor passado no parâmetro (pois o nome do arquivo já está expandido, isto é, já está em relação à raiz do HD virtual).
  * Caso contrário, a função procura pelo arquivo dentro de cada um dos diretórios de pesquisa (SEARCH PATHs) que foram previamente registrados (ver descrição da função “[vhd.addSearchPath](<BibliotecaVHD.md#addSearchPath>)”).&nbsp;
    * Caso encontre dentro de algum dos diretórios de pesquisa, a função retorna o caminho completo (expandido, com relação à raiz do HD virtual) do arquivo.&nbsp;
    * Caso não encontre o arquivo, a função retorna o mesmo valor passado pelo parâmetro shortFileName.
  * Esta função leva em consideração os aliases registrados pela função [VHD.registerAlias](<BibliotecaVHD.md#VHD.registerAliases>), traduzindo o apelido e retornando o nome real do arquivo.

&nbsp;

&nbsp;

| **function** VHD.addSearchPath(directory) |
| --- |


&nbsp;

Adiciona um diretório à lista de "diretórios de pesquisa" (SEARCH PATH) do HD Virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * directory - cadeia de caracteres contendo o caminho **expandido** (isto é, em relação à raiz do HD Virtual) do diretório.

&nbsp;

A função "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)" utiliza estes diretórios de pesquisas na hora de expandir o nome curto de um arquivo.

&nbsp;

&nbsp;

| **function** VHD.removeSearchPath(directory) |
| --- |


&nbsp;

Remove um diretório da lista de "diretórios de pesquisa" (SEARCH PATH) que havia sido previamente registrado através a função "[vhd.addSearchPath](<BibliotecaVHD.md#addSearchPath>)".

&nbsp;

Parâmetros:

* &nbsp;
  * directory - cadeia de caracteres contendo o caminho **expandido** (isto é, em relação à raiz do HD Virtual) do diretório.

&nbsp;

| **function** VHD.registerAlias(aliases) |
| --- |


&nbsp;

Registra aliases/apelidos para arquivos no VHD.

&nbsp;

Parâmetros:

* &nbsp;
  * aliases - uma tabela lua contendo os aliases, onde cada par de chave-valor da tabela representa:
    * chave - uma cadeia de caracteres representando o aliases/apelido a ser criado
    * valor - o nome do arquivo no VHD que o alias deve traduzir.

&nbsp;

Observações:

* &nbsp;
  * O alias funciona com a função [VHD.expandFileName](<BibliotecaVHD.md#expandFileName>) e com a função **require** do Lua.
  * O alias é case-sensitive, isto é, "myFile" é diferente de "MyFile".
  * O alias não pode começar com o caracter "/". O nome traduzido pode começar com "/"

&nbsp;

Exemplo:

| **local** aliases = {}; aliases\["mylua"\] = "init.lua"; aliases\["myFile2"\] = "secondFile.lua";   VHD.registerAlias(aliases);&nbsp; require("myFile2");&nbsp; |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** VHD.fileExists(fileName) |
| --- |


&nbsp;

Verifica se um arquivo existe no HD virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * fileName - cadeia de caracteres contendo o caminho&nbsp; a verificar.

&nbsp;

Retorno:

&nbsp; &nbsp; Retorna **true** caso o arquivo exista ou **false** se não existir.

&nbsp;

Observação:

&nbsp; &nbsp; Esta função expande o nome do arquivo (através de "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)") antes de realizar a verificação.

&nbsp;

| **function** VHD.directoryExists(path) |
| --- |


&nbsp;

Verifica se um diretório existe no HD virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * path - cadeia de caracteres contendo o caminho&nbsp; a verificar.

&nbsp;

Retorno:

&nbsp; &nbsp; Retorna **true** caso o diretório exista ou **false** se não existir.

&nbsp;

Observação:

&nbsp; &nbsp; Esta função expande o caminho (através de "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)") antes de realizar a verificação.

&nbsp;

&nbsp;

| **function** VHD.openFile(fileName \[, mode\]) |
| --- |


&nbsp;

Esta função abre um arquivo do HD virtual no modo especificado.

&nbsp;

Parâmetros:

* &nbsp;
  * fileName - cadeia de caracteres contendo o nome do arquivo a abrir.
  * (OPCIONAL) mode - cadeia de caracteres definindo o modo em que o arquivo será aberto.Pode ser um dos seguintes valores:
    * "r" - modo somente leitura (padrão se omitido). A função falhará se o arquivo não existir.
    * "w" - modo escrita/leitura preservando o contendo do arquivo (se existir). Se o arquivo não existir, a função cria o arquivo.
    * "a" - modo append. Equivalente ao modo "w", porém o objeto stream retornado é posicionado no fim do arquivo.
    * "w+" - modo escrita/leitura, o conteúdo do arquivo é apagado se ele existir. Se o arquivo não existir, a função cria o arquivo.

&nbsp;

Retorno:

* &nbsp;
  * Caso a função obtenha êxito, retorna um [Objeto Stream](<ObjetoStream.md>) representando o conteúdo do arquivo. Qualquer alteração feita no objeto stream é refletida no arquivo.
  * Caso a função falhe, retorna **nil** e a mensagem de erro.

&nbsp;

Observações:

* &nbsp;
  * Esta função expande o nome do arquivo (através de "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)") antes de realizar a abertura.
  * Para fechar o arquivo que foi aberto, você deve invocar o [método close do objeto stream](<ObjetoStream.md#função%20stream:close>) retornado. Se o objeto stream for coletado pelo coletor de lixo, o arquivo também é fechado automaticamente.
  * Exceto para o modo "a", o objeto stream retornado aponta para o inicio do arquivo.
  * Apenas o modo "r" é aceito para abrir arquivos que originalmente vieram no plug-in. Não é possível alterar o conteúdo destes arquivos

&nbsp;

&nbsp;

| **function** VHD.forceDirectory(directoryPath) |
| --- |


&nbsp;

Esta função cria, se necessário, um ou mais diretórios especificado por directoryPath no HD virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * directoryPath - cadeia de caracteres contendo o caminho do diretório a ser "forçado".

&nbsp;

Retorno:

* &nbsp;
  * Caso o diretório já exista e não foi preciso fazer nada, a função retorna **false**.
  * Caso o diretório não existia e a função conseguiu criá-lo, retorna **true**.
  * Caso o diretório não exista mas a função também não consiga criá-lo, um erro é levantado.

&nbsp;

Observações:

* &nbsp;
  * O valor de "directoryPath" deve ser um caminho absoluto no VHD (isto é, deve começar com o caracter "/")
  * A criação de diretório ocorre de forma recursiva. Isto é, ao especificar "/diretorioNaoExistente1/diretorioA/diretorioB", a função irá criar "/diretorioNaoExistente1" primeiro, depois "diretorioA" dentro de "/diretorioNaoExistente1/", e, por fim, "diretorioB" dentro de "/diretorioNaoExistente1/diretorioA/".

&nbsp;

&nbsp;

| **function** VHD.deleteFile(fileName) |
| --- |


&nbsp;

Esta função remove um arquivo do HD virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * fileName - cadeia de caracteres contendo o caminho do arquivo a ser excluído.

&nbsp;

Observações:

* &nbsp;
  * Esta função expande o nome do arquivo (através de "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)") antes de realizar a remoção.
  * Esta função não pode ser usada para remover diretórios.
  * Não é possível apagar um arquivo que originalmente veio no plug-in. Não é possível alterar o conteúdo destes arquivos

&nbsp;

&nbsp;

| **function** VHD.deleteDirectory(directoryPath) |
| --- |


&nbsp;

Esta função remove um diretório e todo seu conteúdo do HD virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * directoryPath - cadeia de caracteres contendo o caminho do diretório que será excluído.

&nbsp;

Observações:

* &nbsp;
  * Esta função expande o caminho do diretório (através de "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)") antes de realizar a remoção.
  * Não é possível apagar um arquivo que originalmente veio no plug-in. Não é possível alterar o conteúdo destes arquivos.
  * Esta função apaga o diretório e todo seu conteúdo recursivamente.

&nbsp;

&nbsp;

&nbsp;

| **function** VHD.enumerateContent(directoryPath) |
| --- |


&nbsp;

Esta função retorna quais arquivos e diretórios estão dentro de um diretório no HD Virtual.

&nbsp;

Parâmetros:

* &nbsp;
  * directoryPath - cadeia de caracteres contendo o caminho do diretório que terá seu conteúdo enumerado.

&nbsp;

Retorno:

* &nbsp;
  * Se "directoryPath" não conter um caminho válido de diretório, um erro será lançado.
  * Senão, um array de strings será retornado, onde cada posição do arranjo contém o nome do diretório/arquivo.

&nbsp;

Observações:

* &nbsp;
  * Esta função expande o caminho de directoryPath (através de "[vhd.expandFileName](<BibliotecaVHD.md#expandFileName>)") antes de realizar a enumeração..
  * Esta função **não** enumera o conteúdo de forma recursiva. Isto é, se existirem sub-diretórios, seus conteúdos não serão enumerados neste retorno, apenas os itens que estão diretamente dentro de "directoryPath".
  * O texto retornado no arranjo contém o nome do arquivo/diretório sem incluir "barras" ou outra forma de expressar o diretório que se encontra.
    * Exemplo: Se existirem dois arquivos (a.txt e b.txt) e um subdiretório ("/textos/histórias/") na pasta "/textos/", o retorno será:
      * {'a.txt', 'b.txt', 'histórias'}
  * Para saber se um item do arranjo retornado é diretório ou é arquivo, utilize as funções [VHD.fileExists](<BibliotecaVHD.md#fileExists>) e [VHD.directoryExists](<BibliotecaVHD.md#directoryExists>)


***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Productivity with HelpNDoc's Efficient User Interface](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
