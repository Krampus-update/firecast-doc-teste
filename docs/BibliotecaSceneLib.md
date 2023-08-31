# Biblioteca SceneLib

# Biblioteca SceneLib

Biblioteca que contém funções relacionadas ao Scene 3/Tabuleiro de combate do RRPG

Todas as funções estão contidas na unidade "scene.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "scene.lua"* require("scene.lua");    *-- Agora é possível acessar as funções da biblioteca* SceneLib.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca SceneLib

&nbsp;

| **function** SceneLib.getLoadedScenes() |
| --- |


&nbsp;

Retorna um array de Scenes que estão rodando no RRPG no momento.

&nbsp;

Retorno:

* &nbsp;
  * Array (tabela lua indexada de 1 a #tabela) de [objeto Scene](<ObjetoScene.md>)

&nbsp;

&nbsp;

| **function** SceneLib.registerPlugin(attachCallback) |
| --- |


&nbsp;

Registra um plug-in de scene no RRPG.

&nbsp;

Parâmetros:

* &nbsp;
  * attachCallback - Uma função que será invocada para cada Scene rodando ou que vier a ser carregado. Esta função recebe dois parâmetros na seguinte ordem: scene ([um objeto Scene](<ObjetoScene.md>)) e attachment (um [objeto ScenePluginAttachment](<ObjetoScenePluginAttachment.md>)) representando, respectivamente, o scene o qual o plug-in deve instalar e um objeto que identifica esta ligação entre o plug-in e o scene.

&nbsp;

Retorno:

* &nbsp;
  * Um identificador do plug-in registrado que poderá ser utilizado posteriormente como parâmetro para a função [SceneLib.unregisterPlugin](<BibliotecaSceneLib.md#unregisterPlugin()>) para desregistrá-lo.

&nbsp;

Observações:

* &nbsp;
  * Um pacote .rpk (plugin SDK 3) pode instalar mais de um Plug-in de Scene.
  * Um plug-in de scene pode existir mesmo quando não há nenhum Scene rodando no RRPG, não tem problema.
  * Um plug-in de scene pode se anexar a mais de 1 scene ao mesmo tempo\! A função "attachCallback" será chamada uma vez para cada Scene existente e uma instância do [objeto ScenePluginAttachment](<ObjetoScenePluginAttachment.md>) será criada para representar cada uma desta ligação "plugin x scene".
  * Assim como um plug-in pode se anexar a vários scenes, um scene pode estar anexado a vários plug-ins. É uma relação N:N (leia-se: N para N).

&nbsp;

&nbsp;

Exemplo de um plug-in simples que apenas exibe uma mensagem quando se anexa a um Scene:

| require("scene.lua"); require("dialogs.lua");   SceneLib.registerPlugin(     **function** (scene, attachment)                    showMessage("Plugin anexado a um tabuleiro de tamanho " ..                     scene.worldWidth .. scene.worldMetricName .. " x " ..                     scene.worldHeight .. scene.worldMetricName ..                     " de cor de fundo ".. scene.bkgColor);     **end**);&nbsp; |
| --- |


&nbsp;

&nbsp;

| **function** SceneLib.unregisterPlugin(pluginID) |
| --- |


&nbsp;

Desregistra um plug-in de scene do RRPG que fora previamente instalado pela função [SceneLib.registerPlugin ](<BibliotecaSceneLib.md#registerPlugin()>)

&nbsp;

Parâmetros:

* &nbsp;
  * pluginID - O identificador do plugin que deseja desinstalar. Este valor é retornado pela função [SceneLib.registerPlugin](<BibliotecaSceneLib.md#registerPlugin()>) .

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Normalmente não é preciso se preocupar em desregistrar plug-ins de scene pois o RRPG já faz este trabalho automaticamente quando o .rpk é descarregado da memória.

&nbsp;

&nbsp;

| **function** SceneLib.Math.newRotationMatrix(angle, pivoX, pivoY) |
| --- |


&nbsp;

Cria e retorna uma Matriz de rotação 2D

&nbsp;

Parâmetros:

* &nbsp;
  * angle - O ângulo da rotação em graus
  * pivoX - A posição X do pivô da rotação
  * pivoY - A posição Y do pivô da rotação

&nbsp;

Retorno:

* &nbsp;
  * A Matriz de rotação. (Um tipo de dados interno)

&nbsp;

&nbsp;

| **function** SceneLib.Math.transformPoint(x, y, matrix) |
| --- |


&nbsp;

Transforma a posição de um ponto ao multiplicá-lo por uma matriz.

&nbsp;

Parâmetros:

* &nbsp;
  * x - A posição X do ponto
  * y - A posição Y do ponto
  * matrix - Uma matriz de transformação.

&nbsp;

Retorno:

* &nbsp;
  * x - A nova posição X
  * y - A nova posição Y

&nbsp;

&nbsp;

| **function** SceneLib.Math.rotatePoint(x, y, angle, pivoX, pivoY) |
| --- |


&nbsp;

Rotaciona um ponto.

&nbsp;

Parâmetros:

* &nbsp;
  * x - A posição X do ponto
  * y - A posição Y do ponto
  * angle - O ângulo da rotação em graus
  * pivoX - A posição X do pivô da rotação
  * pivoY - A posição Y do pivô da rotação

&nbsp;

Retorno:

* &nbsp;
  * x - A nova posição X
  * y - A nova posição Y

***
_Created with the Personal Edition of HelpNDoc: [Modernize your help files with HelpNDoc's WinHelp HLP to CHM conversion tool](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
