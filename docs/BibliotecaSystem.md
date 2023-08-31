# Biblioteca System

# Biblioteca System

Biblioteca que contém funções para lidar com o dispositivo do usuário e outras funcionalidades básicas.

Todas as funções estão contidas na unidade "system.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "system.lua"* require("system.lua");    *-- Agora é possível acessar as funções da biblioteca* System.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca System

&nbsp;

| **function** System.setClipboardText(text) |
| --- |


&nbsp;

Altera o conteúdo do Clipboard/Área de Transferência do sistema operacional (ctrl+c).

&nbsp;

Parâmetros:

* &nbsp;
  * text - Cadeia de caracteres contendo o novo conteúdo que será colocado no Clipboard do usuário.

&nbsp;

Retorno:

* &nbsp;
  * Caso consiga alterar o conteúdo do clipboard, retorna **true**, senão retorna **false.**

&nbsp;

&nbsp;

| **function** System.getClipboardText() |
| --- |


&nbsp;

Retorna o conteúdo do Clibpboard/Área de Transferência do sistema operacional (ctrl+c)

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres caso haja um texto no clipboard ou **nil**.

&nbsp;

&nbsp;

| **function** System.readClipboardAsDragNDrop(callback, \[options\]) |
| --- |


&nbsp;

Read the device clipboard as a drag-and-drop operation. Helpful to read multiple clipboard formats (such as files and images).

&nbsp;

Parameters:

* &nbsp;
  * callback - a function that will be called to handle the drag-and-drop operation. The callback will receive the following parameters:
    * drop - The [Drop Object](<ObjetoDrop.md>) that you must fill in the information so Firecast can match the drag to the drop.
    * x - The number passed in "options.x" or 0
    * y - The number passed in "options.y" or 0
    * drag - The [Drag Object](<ObjetoDrag.md>) representing the clipboard data. You must not change the properties of this object.
  * (Optional) options - a table that may contain the following attributes:
    * (Optional) x -The "x" position that the callback function will receive
    * (Optional) y -The "y" position that the callback function will receive.

&nbsp;

Returns:

* &nbsp;
  * **true** if the operation had a match or **false** instead.

&nbsp;

Remarks:

* &nbsp;
  * The callback function is called immediately. The drag object is valid only inside the callback execution.
  * The drag and drop operation works exactly in the same way the [onStartDrop](<Caracteristicasdetodasastagsvisu.md#onStartDrop>) event that all visual tags have.
  * Please read [Dragging and Dropping Information](<ArrastandoeSoltandoInformacoesDr.md>) to learn more about the drag-and-drop process.

&nbsp;

&nbsp;

| **function** System.getScreenSize() |
| --- |


&nbsp;

Retorna as dimensões da tela do dispositivo do usuário.

&nbsp;

Retorno:

* &nbsp;
  * Retorna dois números: largura e altura da tela em [pontos lógicos](<PontoLogicovsPixel.md>).

&nbsp;

Exemplo:

| **local** largura, altura = system.getScreenSize(); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** System.isMobile() |
| --- |


&nbsp;

Retorna se o plugin está rodando no Firecast Mobile.

&nbsp;

Retorno:

* &nbsp;
  * Retorna **true** se o plugin está rodando no App do FireCastMobile ou **false** se está rodando no RRPG de computador

&nbsp;

&nbsp;

| **function** System.getTickCount() |
| --- |


&nbsp;

Retorna um número contendo há quantos milisegundos o dispositivo do usuário está ligado. Ótimo para calcular o tempo decorrido entre operações.

&nbsp;

### SDK3 API Version Functions

##### Version history

| **Major** | **Minor** | **Description** |
| --- | --- | --- |
| &#56;7 | &#48; | SDK 3.6 (Firecast 8+) |
| &#56;7 | &#49; | SDK 3.6b (Firecast 8.5+) |
| &#56;7 | &#50; | SDK 3.6c (Firecast 8.6+) |
| &#56;7 | &#51; | SDK 3.6d (Firecast 8.8+) |


&nbsp;

Identical major versions possess compatibility with each other.&nbsp;

For example, you can compile a plugin using SDK3.6b (87.1), and it will still run fine on an SDK 3.6 (87.0) running API because the two have the same major version.

&nbsp;

&nbsp;

| **function** System.checkAPIVersion(major, \[minor\]) |
| --- |


&nbsp;

Checks if the current running SDK3 API version is greater or equal to a specific version.

&nbsp;

Parameters:

* &nbsp;
  * major - The major version integer to check.
  * (Optional) minor - The minor version integer to check. When omitted, 0 is used by default

&nbsp;

Returns:

* &nbsp;
  * **true** if the current running SDK3 API version is greater or equal to the specified version; **false** otherwise.

&nbsp;

Remarks:

* &nbsp;
  * You may want to check the [SDK3 API version history](<BibliotecaSystem.md#SDK3\_API\_Version\_History>).

&nbsp;

&nbsp;

| **function** System.getAPIVersion() |
| --- |


&nbsp;

Gets the current running SDK3 API version.

&nbsp;

Returns:

* &nbsp;
  * An integer number in the same format returned by the function [System.makeAPIVersionNumber](<BibliotecaSystem.md#System\_makeAPIVersion>)

&nbsp;

Remarks:

* &nbsp;
  * You may want to check the [SDK3 API version history](<BibliotecaSystem.md#SDK3\_API\_Version\_History>).

&nbsp;

&nbsp;

| **function** System.makeAPIVersionNumber(major, \[minor\]) |
| --- |


&nbsp;

Make an API version integer number that you can use to compare versions.

&nbsp;

Parameters:

* &nbsp;
  * major - The major version integer
  * (Optional) minor - The minor version integer. When omitted, 0 is used by default

&nbsp;

Returns:

* &nbsp;
  * An integer number. It's a 32 bits where the upper 16 bits contain the major version, and the lower 16 bits hold the minor version.

&nbsp;

Remarks:

* &nbsp;
  * You may want to check the [SDK3 API version history](<BibliotecaSystem.md#SDK3\_API\_Version\_History>).


***
_Created with the Personal Edition of HelpNDoc: [HelpNDoc's Project Analyzer: Incredible documentation assistant](<https://www.helpndoc.com/feature-tour/advanced-project-analyzer/>)_
