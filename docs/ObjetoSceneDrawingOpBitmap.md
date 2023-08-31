# Objeto SceneDrawingOpBitmap

# Objeto SceneDrawingOpBitmap

O Objeto SceneDrawingOpBitmap representa uma operação gráfica de um Bitmap/Imagem em um [SceneCanvas](<ObjetoSceneCanvas.md>) .

## Herança

O o**bjeto SceneDrawingOpBitmap** herda de [SceneDrawingOp](<ObjetoSceneDrawingOp.md>) e possui também **TODAS** todas as suas características.

&nbsp;

Veja também:

* &nbsp;
  * [Objeto SceneDrawingOp](<ObjetoSceneDrawingOp.md>)
  * [Objecto SceneBaseObject](<ObjetoSceneBaseObject.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneDrawingOpBitmap também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String "opBitmap" | (Somente Leitura) Contém um texto que identifica o tipo da operação gráfica - "opBitmap".&nbsp; |
| **url** | String | Contém a URL da imagem/bitmap que será renderizada.&nbsp; Este valor: Pode ser um endereço de internet (exemplo: “[http://xxxx.com.br/a.png](<http://xxxx.com.br/a.png>)”)&nbsp; Pode ser o caminho de um arquivo contido no pacote do plugin. Pode ser um arquivo que se encontra no [HD Virtual](<HDVirtual.md>) do plugin instalado.&nbsp; |
| **flipHorz** | Boolean | Determina se a imagem deve ser desenhada de forma espelhada horizontalmente.&nbsp; |
| **flipVert** | Boolean | Determina se a imagem deve ser desenhada de forma espelhada verticalmente.&nbsp; |
| **grayscale** | Boolean | Determina se imagem deve ser desenhada usando um filtro de cores que transforma a imagem em uma imagem de escala cinzenta.&nbsp; |
| **colorBlend** | [String de Cor](<StringdecoresnoLuaForm.md>)&nbsp; | Determina se a imagem deve ser desenhada utilizando um filtro que misturando as cores originais com uma cor definida pela propriedade "colorBlend".&nbsp; O valor padrão é "#00000000" e significa não realizar misturar de cores.&nbsp; Exemplo: "Blue" fará com que a imagem seja desenhada misturada com a cor azul.&nbsp; |
| **colorMask** | [String de Cor](<StringdecoresnoLuaForm.md>)&nbsp; | Determina se a imagem deve ser desenhada utilizando um filtro que seleciona as cores da imagem realizando uma multiplicação das cores da imagem pela cor definida em "colorMask".&nbsp; O valor padrão é "#FFFFFFFF" e significa que todas as coras originais da imagem deve ser desenhadas sem alteração.&nbsp; Exemplo: "Blue" fará com que a imagem seja desenhada selecionando apenas os tons azuis pois os componentes da cor azul são R = 0, G = 0 e B = 255, o que transformando em notação de ponto flutuante fica R = 0.0, G = 0.0, B = 1.0... Para cada pixel da imagem, o Red será multiplicado por 0, o Green será multiplicado por 0 e o Blue será multiplicado por 1.0.&nbsp; |
| **filterEx** | Enumerado: "none" (Padrão) "glow" "innerGlow" "blur" "sepia"&nbsp; | Determina se a imagem deve ser desenhada com mais algum filtro de imagem especial.&nbsp; "none" - Nenhum filtro especial.&nbsp; "glow" - Um filtro que adiciona uma incandescência à imagem. Não esqueça de preencher a propriedade "filterExColor" ao utilizar este filtro.&nbsp; "innerGlow" - Um filtro que adiciona um brilho interno à imagem. Não esqueça de preencher a propriedade "filterExColor" ao utilizar este filtro.&nbsp; "blur" - Um filtro que aplica um "borrão" na imagem.&nbsp; "sepia" - Um filtro que aplica um tom marrom na imagem.&nbsp; |
| **filterExColor** | [String de Cor](<StringdecoresnoLuaForm.md>)&nbsp; | Alguns filtros permitem escolher uma cor como parâmetro.&nbsp; Se a propriedade filterEx for:&nbsp; "glow" - Esta propriedade contém a cor da incandescência que será criada na imagem.&nbsp; "innerGlow" - Esta propriedade contém a cor do brilho interno que será criado na imagem.&nbsp; A cor padrão é "Red"&nbsp; |
| **frame** | Enumerado: "none" (Padrão) "boton" | Determina se a imagem deve ser desenhada com alguma borda.&nbsp; "none" - A imagem será desenhada sem bordas.&nbsp; "boton" - A imagem será desenhada com borda de um bóton arredondado.&nbsp; |
| **sourceRect** | [Estrutura SceneRect](<EstruturaSceneRect.md>) | Determina, utilizando uma [Estrutura SceneRect](<EstruturaSceneRect.md>), qual porção da imagem original deve ser desenhada.&nbsp; Os valores de left, top, right e bottom vão de 0.0 a 1.0, onde 0.0 = representa o inicio e 1.0 o final do eixo.&nbsp; O valor padrão é: {left=0.0, top=0.0, right=1.0, bottom=1.0} ... isto é, desenhar todo contéudo da imagem original.&nbsp; Exemplo:&nbsp; {left=0.5, top=0, right=1.0, bottom=0.5} - Desenhar apenas o quadrante superior-direita da imagem.&nbsp; |


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

### Exemplo 1 - Um plug-in que adiciona/remove uma marca personalizada quando o usuário clica nos itens do scene.

&nbsp;

| require("scene.lua");   SceneLib.registerPlugin(     **function** (scene, attachment)                                    *-- Manipular o evento OnMouseDown do Viewport*                 scene.viewport.onMouseDown = **function**(event)             *-- Usuário clicou no Scene*             *-- Transformar as coordenadas de tela em métrica de mundo*             **local** worldX, worldY = scene.viewport:screenToWorld(event.x, event.y);                         *-- Localizar o item que o usuário clicou*             **local** item = scene.items:itemAtPoint(worldX, worldY);                         **if** item ~= nil **then**                 *-- Encontrou um item na posição clicada.             *                 **local** NOME\_MINHA\_MARCA = "MarcaExemplo";                                 *-- Localizar uma operação gráfica neste item com o nosso nome*                 **local** opGrafica = item.canvas:findByName(NOME\_MINHA\_MARCA);                                 **if** opGrafica == nil **then**                     *--\[\[ A operação gráfica da minha marca ainda não*                         *existe neste token/item. Vamos criar \]\]*                                             opGrafica = item.canvas:addBitmap();                     opGrafica.name = NOME\_MINHA\_MARCA; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; *-- Abaixo, URL da imagem da nossa marca.*                     opGrafica.url = "https://wiki.teamfortress.com/w/images/d/dd/Bleed\_drop.png?t=20110425044341";                     opGrafica.x = 0.25;                     opGrafica.width = 0.3;                     opGrafica.y = -0.1;                     opGrafica.height = 0.3;                     opGrafica.z = 10;                                       **else**                     *-- Vamos apagar nossa operação gráfica previamente criada*                     opGrafica:delete();                 **end**;             **end**;                    **end**;                     **end**);&nbsp; |
| --- |


&nbsp;

| ![Image](<lib/NewItem222.png>) Item sem a marca | ![Image](<lib/NewItem223.png>) Item com a marca |
| :---: | :---: |


&nbsp;

### Exemplo 2 -&nbsp;

&nbsp;

| &nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Transform Your Word Document into a Professional eBook with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
