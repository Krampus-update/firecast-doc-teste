# Objeto SceneCanvas

# Objeto SceneCanvas

O Objeto SceneCanvas representa como um item do Scene deve ser desenhado na tela do usuário e, no fundo, é uma lista de operações gráficas que devem ser executadas para compor a aparência de um item no tabuleiro.

O SceneCanvas de um item gráfico pode ser obtido através da propriedade "[canvas](<ObjetoSceneGraphicItem.md#prop%20canvas>)" de um que herde de [objeto SceneGraphicItem](<ObjetoSceneGraphicItem.md>)

&nbsp;

A grande vantagem em utilizar o SceneCanvas é que as operações gráficas são persistidas no scene e serão executadas no tabuleiro de cada usuário, mesmo que algum não tenha instalado algum determinado plug-in.

&nbsp;

## Herança

O o**bjeto SceneCanvas** herda de [SceneBaseObject](<ObjetoSceneBaseObject.md>) e possui também todas as suas características.

&nbsp;

## Características

Além das características herdadas, o objeto SceneCanvas também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **opCount** | Integer | (Somente Leitura) Contém a quantidade de operações gráficas que este Canvas possui.&nbsp; |


&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **canvas:getOp(index)** | Retorna a operação gráfica de índice passado por parâmetro.&nbsp; Parâmetros: index - Um número inteiro informando qual operação gráfica do canvas você deseja obter. Este valor deve estar entre 0 e&nbsp; "opCount" - 1&nbsp; Retorno: Um [objeto SceneDrawingOp](<ObjetoSceneDrawingOp.md>) representando a operação gráfica do índice informado.&nbsp; Observação:&nbsp; O item retornado pode ser uma operação gráfica de bitmap/imagem ([objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>)) ou uma operação gráfica de caminho/formas/polígonos ([objeto SceneDrawingOpPath](<ObjetoSceneDawingOpPath.md>)). Para saber qual é o tipo da operação gráfica, verifique a propriedade objectType do objeto retornado.&nbsp; |
| **canvas:addBitmap()** | Adiciona uma operação gráfica de desenho de bitmap/imagem ao canvas.&nbsp; Parâmetros: Nenhum&nbsp; Retorno: Um [objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>) representando a operação gráfica criada.&nbsp; |
| **canvas:addPath()** | Adiciona uma operação gráfica de desenho de caminho/formas/polígonos ao canvas.&nbsp; Parâmetros: Nenhum&nbsp; Retorno: Um [objeto SceneDrawingOpPath](<ObjetoSceneDawingOpPath.md>) representando a operação gráfica criada.&nbsp; |
| **canvas:addText()** | Adiciona uma operação gráfica de desenho de texto ao canvas.&nbsp; Parâmetros: Nenhum&nbsp; Retorno: Um [objeto SceneDrawingOpText](<ObjetoSceneDrawingOpText.md>) representando a operação gráfica criada.&nbsp; |
| **canvas:findByName(name)** | Localiza uma operação gráfica pelo seu nome.&nbsp; Parâmetros: name - Um texto, o nome da operação gráfica que está procurando neste Canvas/Item do Scene.&nbsp; Retorno: Se o Scene encontrar uma operação gráfica cuja propriedade name for igual ao texto informado, retorna um [objeto SceneDrawingOp](<ObjetoSceneDrawingOp.md>) representando a operação gráfica localizada. Se o Scene não encontrar, retorna **nil**. &nbsp; Observação:&nbsp; O item retornado pode ser uma operação gráfica de bitmap/imagem ([objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>)) ou uma operação gráfica de caminho/formas/polígonos ([objeto SceneDrawingOpPath](<ObjetoSceneDawingOpPath.md>)). Para saber qual é o tipo da operação gráfica, verifique a propriedade objectType do objeto retornado.&nbsp; |
| **canvas:clear()** | Limpa o canvas excluindo todas as operações gráficas contida nele.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Um plug-in que adiciona/remove uma marca personalizada quando o usuário clica nos itens do scene.

&nbsp;

| require("scene.lua");   SceneLib.registerPlugin(     **function** (scene, attachment)                                    *-- Manipular o evento OnMouseDown do Viewport*                 scene.viewport.onMouseDown = **function**(event)             *-- Usuário clicou no Scene*             *-- Transformar as coordenadas de tela em métrica de mundo*             **local** worldX, worldY = scene.viewport:screenToWorld(event.x, event.y);                         *-- Localizar o item que o usuário clicou*             **local** item = scene.items:itemAtPoint(worldX, worldY);                         **if** item ~= nil **then**                 *-- Encontrou um item na posição clicada.             *                 **local** NOME\_MINHA\_MARCA = "MarcaExemplo";                                 *-- Localizar uma operação gráfica neste item com o nosso nome*                 **local** opGrafica = item.canvas:findByName(NOME\_MINHA\_MARCA);                                 **if** opGrafica == nil **then**                     *--\[\[ A operação gráfica da minha marca ainda não*                         *existe neste token/item. Vamos criar \]\]*                                             opGrafica = item.canvas:addBitmap();                     opGrafica.name = NOME\_MINHA\_MARCA; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; *-- Abaixo, URL da imagem da nossa marca.*                     opGrafica.url = "https://wiki.teamfortress.com/w/images/d/dd/Bleed\_drop.png?t=20110425044341";                     opGrafica.x = 0.25;                     opGrafica.width = 0.3;                     opGrafica.y = -0.1;                     opGrafica.height = 0.3;                     opGrafica.z = 10;                                       **else**                     *-- Vamos apagar nossa operação gráfica previamente criada*                     opGrafica:delete();                 **end**;             **end**;                    **end**;                     **end**);&nbsp; |
| --- |


&nbsp;

| ![Image](<lib/NewItem222.png>) Item sem a marca | ![Image](<lib/NewItem223.png>) Item com a marca |
| :---: | :---: |


&nbsp;

### Exemplo 2 -

&nbsp;

| &nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [From Word to ePub or Kindle eBook: A Comprehensive Guide](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
