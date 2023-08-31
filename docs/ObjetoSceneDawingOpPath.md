# Objeto SceneDawingOpPath

# Objeto SceneDrawingOpPath

O Objeto SceneDrawingOpPath representa uma operação gráfica de um caminho/forma/polígono em um [SceneCanvas](<ObjetoSceneCanvas.md>) .

## Herança

O o**bjeto SceneDrawingOpPath** herda de [SceneDrawingOp](<ObjetoSceneDrawingOp.md>) e possui também **TODAS** todas as suas características.

&nbsp;

Veja também:

* &nbsp;
  * [Objeto SceneDrawingOp](<ObjetoSceneDrawingOp.md>)
  * [Objecto SceneBaseObject](<ObjetoSceneBaseObject.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneDrawingOpPath também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String "opPath" | (Somente Leitura) Contém um texto que identifica o tipo da operação gráfica - "opBitmap".&nbsp; |
| **data, pathData ou path** | String | Define a forma vetorial do path. Este texto deve estar no mesmo padrão do path do SVG e do XAML.&nbsp; Consulte a [documentação deles na internet](<https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths>)\!&nbsp; Outro link que pode ajudar:&nbsp; [http://www.w3schools.com/svg/svg\_path.asp](<http://www.w3schools.com/svg/svg\_path.asp>)&nbsp; Observação Importante: Path será automaticamente redimensionado para ficar com a mesma dimensão definida para esta operação gráfica.&nbsp; |
| **color** | [String de Cor](<StringdecoresnoLuaForm.md>) | Define a cor do conteúdo da forma.&nbsp; Veja [String de cores](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso. Define a cor do conteúdo da forma.&nbsp; Valor padrão: White&nbsp; |
| **strokeColor** | [String de Cor](<StringdecoresnoLuaForm.md>) | Define a cor do contorno da forma.&nbsp; Veja [String de cores](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso. Define a cor do conteúdo da forma.&nbsp; Valor padrão: Black&nbsp; |
| **strokeSize** | Double | Define a largura do contorno da forma. O significado deste número depende do valor da propriedade "strokeSizeMetric"&nbsp; Valor padrão: 0.0;&nbsp; |
| **strokeSizeMetric** | Enumerado: "screenMetric" "worldMetric" "canvasMetric" "cellMetric" | Define em que medida a propriedade "strokeSize" está medida.&nbsp; "screenMetric" - (Padrão) strokeSize está representado em [métricas de tela](<MetricadoMundovsMetricadaTela.md>).&nbsp; "worldMetric" - strokeSize está representado em [métricas de mundo](<MetricadoMundovsMetricadaTela.md>).&nbsp; "canvasMetric" - strokeSize está representado em métricas de canvas, onde, por exemplo, 0.5 = metade da largura/altura do token/desenho e 1.0 = largura/altura do token/desenho.&nbsp; "cellMetric" - strokeSize está representado em métricas de células. (Exemplo, 0.5 = meia célula do grid, 2 = duas células do grid)&nbsp; |
| **strokeCap** | Enumerado: "flat" "round" | Define o estilo gráfico usado ao desenhar o fim das linhas.&nbsp; "flat" - linhas com pontas retangulares "round" - linhas com pontas arredondadas.&nbsp; Valor padrão: "flat"&nbsp; |
| **strokeJoin** | Enumerado: "miter" "round" "bevel" | Define o estilo gráfico usado ao juntar segmentos de linha em uma forma.&nbsp; "miter" - As quinas/junções são "quadradas".&nbsp; "round" - As quinas/junções são arredondadas.&nbsp; "bevel" - As quintas/junções são ligadas de forma diagonal.&nbsp; Valor padrão: "miter"&nbsp; |
| **strokeDash** | Enumerado: "solid" "dash" "dot" "dashDot" "dashDotDot" | Define o estilo gráfico da linha.&nbsp; "solid" - A linha é sólida&nbsp; "dash" - A linha é tracejada&nbsp; "dot" - A linha é feita de pontos.&nbsp; "dashDot" - A linha é alternada entre traços e pontos.&nbsp; "dashDotDot" - A linha é alternada entre traço, ponto e ponto.&nbsp; Valor padrão: "solid"&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Um plug-in que adiciona/remove um triângulo amarelo quando o usuário clica nos itens do scene.

&nbsp;

| require("scene.lua");   SceneLib.registerPlugin(     **function** (scene, attachment)                                    *-- Manipular o evento OnMouseDown do Viewport*                 scene.viewport.onMouseDown = **function**(event)             *-- Usuário clicou no Scene*             *-- Transformar as coordenadas de tela em métrica de mundo*             **local** worldX, worldY = scene.viewport:screenToWorld(event.x, event.y);                         *-- Localizar o item que o usuário clicou*             **local** item = scene.items:itemAtPoint(worldX, worldY);                         **if** item ~= nil **then**                 *-- Encontrou um item na posição clicada.             *                 **local** NOME\_MINHA\_MARCA = "MarcaExemplo";                                 *-- Localizar uma operação gráfica neste item com o nosso nome*                 **local** opGrafica = item.canvas:findByName(NOME\_MINHA\_MARCA);                                 **if** opGrafica == nil **then**                     *--\[\[ A operação gráfica da minha marca ainda não*                         *existe neste token/item. Vamos criar \]\]*                                             opGrafica = item.canvas:addPath();                     opGrafica.name = NOME\_MINHA\_MARCA;                                                                             *-- Começar a desenhar no X equivalente a 80% da largura do item*                     *-- Começar a desenhar no Y equivalente a 25% da altura do item*                     opGrafica.x = 0.8;                     opGrafica.y = 0.25;                                                                 opGrafica.width = 0.5;  *-- Largura do Path: 50% da largura do item                 *                     opGrafica.height = 0.4;  *-- Altura do Path: 40% da altura do item*                                         opGrafica.z = 10;                                                                               *-- Cores e estilo do PATH*                     opGrafica.color = "yellow";                     opGrafica.strokeSize = 1;                                                                               *-- O path data (Um triângulo apontado para a direita)*                     opGrafica.data = "M 0 0 L 1 0.5 L 0 1 Z";                 **else**                     *-- Vamos apagar nossa operação gráfica previamente criada*                     opGrafica:delete();                 **end**;             **end**;                    **end**;                     **end**);&nbsp; &nbsp; |
| --- |


&nbsp;

| ![Image](<lib/NewItem224.png>) Item sem a marca |  ![Image](<lib/NewItem225.png>) Item com a marca |
| :---: | :---: |


&nbsp;

### Exemplo 2 -&nbsp;

&nbsp;

| &nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Easily create EBooks](<https://www.helpndoc.com/feature-tour>)_
