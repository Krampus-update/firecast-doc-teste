# Objeto SceneDrawingOp

# Objeto SceneDrawingOp

O Objeto SceneDrawingOp representa uma operação gráfica de um [SceneCanvas](<ObjetoSceneCanvas.md>) .

&nbsp;

## Herança

O o**bjeto SceneDrawingOp** herda de [SceneBaseObject](<ObjetoSceneBaseObject.md>) e possui também todas as suas características.

&nbsp;

## Abstração

Esta é uma **classe abstrata** e você nunca encontrará um objeto SceneDrawingOp vivo sem ser uma das seguintes classes:

* [Objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>)
* [Objeto SceneDrawingOpPath](<ObjetoSceneDawingOpPath.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneDrawingOp também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String: "opBitmap" "opPath" "opText" | (Somente Leitura) Contém um texto que identifica o tipo da operação gráfica e pode conter um dos seguintes valores:&nbsp; "opBitmap" -&nbsp; este operação gráfica é um [Objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>), uma imagem/bitmap.&nbsp; "opPath" - esta operação gráfica é um [Objeto SceneDrawingOpPath](<ObjetoSceneDawingOpPath.md>), um caminho/forma/polígono.&nbsp; "opText" - Esta operação gráfica é um [Objeto SceneDrawingOpText](<ObjetoSceneDrawingOpText.md>), um texto.&nbsp; |
| **x** | Double | Contém a posição X de onde esta operação gráfica deve ser renderizada.&nbsp; Por padrão, este valor está em uma métrica relativa ao SceneCanvas de um item no scene e é normalizado entre 0.0 e 1.0, onde 0.0 = canto esquerdo do item, 0.5 = centro do item e 1.0 = canto direito do item. (Item, neste caso, é o Token/UserDrawing/EffectArea desta operação gráfica)&nbsp; |
| **y** | Double | Contém a posição Y de onde esta operação gráfica deve ser renderizada.&nbsp; Por padrão, este valor está em uma métrica relativa ao SceneCanvas de um item no scene e é normalizado entre 0.0 e 1.0, onde 0.0 = canto superior do item, 0.5 = centro do item e 1.0 = canto inferior do item (Item, neste caso, é o Token/UserDrawing/EffectArea desta operação gráfica)&nbsp; |
| **width** | Double | Contém a largura que a operação gráfica deve ser renderizada.&nbsp; Por padrão, este valor está em uma métrica relativa ao SceneCanvas de um item no scene e é normalizado entre 0.0 e 1.0, onde 0.5 = metade da largura do item, 1.0 = largura do item e 2.0 = duas vezes a largura do item. (Item, neste caso, é o Token/UserDrawing/EffectArea desta operação gráfica)&nbsp; |
| **height** | Double | Contém a altura que a operação gráfica deve ser renderizada.&nbsp; Por padrão, este valor está em uma métrica relativa ao SceneCanvas de um item no scene e é normalizado entre 0.0 e 1.0, onde 0.5 = metade da altura do item, 1.0 = altura do item e 2.0 = duas vezes a altura do item. (Item, neste caso, é o Token/UserDrawing/EffectArea desta operação gráfica)&nbsp; |
| **z** | Double | Contém um número para definir a ordem Z da operação gráfica, isto é, a ordem em que deve ser renderizada.&nbsp; Exemplo: Se A e B forem duas operações gráficas de um mesmo Item de Scene e se A possuir ordem Z equivalente a 5 e B possuir ordem Z equivalente a 10, a operação gráfica A aparecerá abaixo da operação gráfica B na tela.&nbsp; |
| **name** | String | Um texto auxiliar qualquer para ajudar a identificar qual é esta operação gráfica.&nbsp; Pode ser utilizado pela função "canvas:findByName()" do [objeto SceneCanvas](<ObjetoSceneCanvas.md>) para fácil localização.&nbsp; |
| **opacity** | Double | Define a opacidade da operação gráfica.&nbsp; Este valor varia de 0.0 a 1.0, onde 0.0 = totalmente transparente e 1.0 = totalmente opaco.&nbsp; |
| **rotMode** | Enumerado: "default" "ignoreCanvasRot" | Define como a operação gráfica deve se comportar em relação à rotação do item/canvas dono da operação gráfica.&nbsp; "default": Padrão, a operação gráfica deve ser rotacionada conforme a rotação de seu canvas/item do scene.&nbsp; "ignoreCanvasRot": A renderização desta operação gráfica deve ignorar a rotação de seu canvas/item do scene.&nbsp; |
| **visibility** | Enumerado: "everyone" "gmOnly"&nbsp; | Define quem pode visualizar esta operação gráfica:&nbsp; "everyone": Padrão, todos podem visualizar esta operação gráfica.&nbsp; "gmOnly": Apenas o mestre da mesa pode ver esta operação gráfica.&nbsp; |
| **rotation** | Double | Define a rotação da operação gráfica em graus.&nbsp; |
| **rotCenterX** | Double | Define onde, no eixo X da operação gráfica, está o pivô de rotação.&nbsp; O valor varia entre 0.0 a 1.0: 0.0 = lado esquerdo do desenho. 0.5 = centro do desenho (Padrão) 1.0 = lado direito do desenho.&nbsp; |
| **rotCenterY** | Double | Define onde, no eixo Y da operação gráfica, está o pivô de rotação.&nbsp; O valor varia entre 0.0 a 1.0: 0.0 = parte superior do desenho. 0.5 = centro do desenho (Padrão). 1.0 = parte inferior do desenho.&nbsp; |
| **drawingTrigger** | Conjunto: "hover" "selected"&nbsp; | Define gatilhos para esta operação ser desenhada.&nbsp; É um conjunto, uma tabela contendo um ou mais dos seguintes itens:&nbsp; "hover" - Quando o mouse estiver por cima do objeto/token.&nbsp; "selected" - Quando o objeto/token estiver selecionado.&nbsp; Exemplos: {} - Não há gatilhos, sempre é desenhada {"hover"} - Quando o mouse estiver por cima do item. {"hover", "selected"} - Quando o mouse estiver por cima do item ou quando o item estiver selecionado.&nbsp; |
| **outOfOrderMode** | Enumerado: "noOutOfOrder" "afterFogOfWarLayer" "beforeOwnerLayer" "afterOwnerLayer" | Define se a operação gráfica possui um comportamento fora da ordem padrão.&nbsp; "noOutOfOrder" - (Padrão) A operação não possui comportamento de desenho fora da ordem e é desenhado na ordem normal.&nbsp; "afterFogOfWarLayer" - A operação possui comportamento de desenho fora de ordem. É desenhada após a camada de Fog Of War ser desenhada no tabuleiro.&nbsp; "beforeOwnerLayer" - A operação possui comportamento de desenho fora de ordem. Ela é desenhada abaixo da camada do item que a possui.&nbsp; "afterOwnerLayer" - "beforeOwnerLayer" - A operação possui comportamento de desenho fora de ordem. Ela é desenhada acima da camada do item que a possui.&nbsp; |
| **xMetric** **yMetric** **widthMetric** **heightMetric** | Enumerado: "screenMetric" "worldMetric" "canvasMetric" "cellMetric"&nbsp; | Altera a medida em que as propriedades "x", "y", "width" e "height" foram informadas:&nbsp; "canvasMetric" - (Padrão) A propriedade está representado em métricas de canvas, onde, por exemplo, 0.5 = metade da largura/altura do token/desenho e 1.0 = largura/altura do token/desenho.&nbsp; "screenMetric" - A propriedade está representado em [métricas de tela](<MetricadoMundovsMetricadaTela.md>).&nbsp; "worldMetric" - A propriedade está representado em [métricas de mundo](<MetricadoMundovsMetricadaTela.md>).&nbsp; "cellMetric" - A propriedade está representado em métricas de células. (Exemplo, 0.5 = meia célula do grid, 2 = duas células do grid)&nbsp; |
| **xOrigin** **yOrigin** | Double | Contém a posição de origem no eixo X e no eixo Y de onde as propriedades "x" e "y" são relativas.&nbsp; Este valor está em uma métrica relativa ao SceneCanvas de um item no scene e é normalizado entre 0.0 e 1.0, onde 0.0 = canto esquerdo do item, 0.5 = centro do item e 1.0 = canto direito do item. (Item, neste caso, é o Token/UserDrawing/EffectArea desta operação gráfica)&nbsp; Observação: Estes valores são úteis apenas quando é usado xMetric/yMetric diferente de "canvasMetric".&nbsp; Exemplo: x = -1; xMetric = "cellMetric"; xOrigin = 0.5; width=2 widthMetric="cellMetric"&nbsp; Faz com que a operação gráfica tenha largura equivalente a 2 células do grid e sua posição X seja equivalente ao "centro X do token menos 1 célula do grid" (Horizontalmente alinhado)&nbsp; |


&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **drawingOp:delete()** | Remove/Apaga a operação gráfica do Canvas do Item no Scene.&nbsp; |


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

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;

&nbsp;

&nbsp;

### Exemplo 2 -

&nbsp;

| &nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Convert Your Word Doc to an eBook: A Step-by-Step Guide](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
