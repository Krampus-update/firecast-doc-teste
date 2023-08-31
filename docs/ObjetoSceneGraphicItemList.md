# Objeto SceneGraphicItemList

# Objeto SceneGraphicItemList

O Objeto SceneGraphicItem é um objeto que contém a coleção de todos os itens gráficos/visuais do tabuleiro, como os tokens.

&nbsp;

O SceneGraphicItemList de um scene pode ser obtido através da propriedade "[items](<ObjetoScene.md#prop%20items>)" do [objeto Scene](<ObjetoScene.md>)

&nbsp;

&nbsp;

## Herança

O o**bjeto SceneGraphicItemList** herda de [SceneBaseObject](<ObjetoSceneBaseObject.md>) e possui também todas as suas características.

&nbsp;

## Características

Além das características herdadas, o objeto SceneGraphicItemList também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **operador #** | Integer | (Somente Leitura) Contem a quantidade de itens gráficos que existem no scene.&nbsp; Exemplo: local qtDeItens = #scene.items;&nbsp; |
| **operador \[\]** | [Objeto SceneGraphicItem](<ObjetoSceneGraphicItem.md>) | (Somente Leitura) Contem um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando um item gráfico do scene, como um token.&nbsp; O valor passado dentro do colchete deve ser um número entre 1 a "count".&nbsp; Exemplo de uso: local item1 = scene.items\[1\]; -- Primeiro item local item2 = scene.items\[2\];&nbsp; -- Percorrendo todos os itens gráficos do scene for i = 1, #scene.items, 1 do &nbsp; local umItem = scene.items\[i\]; end;&nbsp; |
| **count** | Integer | (Somente Leitura), equivale ao operador #. Contem a quantidade de itens gráficos que existem no scene.&nbsp; |
| **selection** | Array de [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) | (Somente Leitura) Retorna um array (uma tabela lua indexada de 1 a #array) contendo os itens do scene que estão selecionados no momento.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **list:get(index)** | Equivalente ao operador \[\], retorna um [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando um item gráfico do scene, como um token.&nbsp; Parâmetros: index - um número inteiro entre 1 e "count"&nbsp; Retorno: Um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>).&nbsp; |
| **list:enumAtPoint(worldX, worldY \[, layer\])** | Dada uma posição em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>), retorna todos os [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) do scene que podem ser encontrados neste ponto (isto é, se o ponto for uma posição dentro do item).&nbsp; Parâmetros: worldX - Número em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>) que contem a coordenada X da ponto. worldY - Número em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>) que contem a coordenada Y do ponto. (OPCIONAL) layer - String contendo uma [camada](<Ascamadasdotabuleiro.md>). Se este parâmetro for informado, apenas itens que estiverem na camada informada serão enumeradas por esta função. Se este parâmetro não informado, todos os itens no ponto serão retornados, independente de qual camada pertencer.&nbsp; Retorno: Um array (tabela lua com índices de 1 a #tabela) de objetos [SceneGraphicItem](<ObjetoSceneGraphicItem.md>). Caso nenhum item seja encontrado na posição informada, o array vem vazio.&nbsp; Observação:&nbsp; O array retornado pela função vem ordenado pela posição Z dos itens quando há sobreposição. Isto é, quando um item ocupa o mesmo espaço que outro item ocupa, a função garante que o item que é desenhado mais abaixo apareça antes no array retornado do que o item que é desenhado acima dele.Se um item achado não sobrepor nenhum outro item, sua ordem no array retornado é indefinida (Ordenação Z apenas dos itens em sobreposição).&nbsp; |
| **list:enumInRect(rect \[, layer\])** | Dado um retângulo em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>), retorna todos os [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) do scene que sobrepõe ao retângulo (que coincidem, justapõe, que intercedem, etc..)&nbsp; Parâmetros: rect - Um retângulo em [estrutura SceneRect](<EstruturaSceneRect.md>) com valores em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>). (OPCIONAL) layer - String contendo uma [camada](<Ascamadasdotabuleiro.md>). Se este parâmetro for informado, apenas itens que estiverem na camada informada serão enumeradas por esta função. Se este parâmetro não informado, todos os itens no ponto serão retornados, independente de qual camada pertencerem.&nbsp; Retorno: Um array (tabela lua com índices de 1 a #tabela) de objetos [SceneGraphicItem](<ObjetoSceneGraphicItem.md>). Caso nenhum item seja encontrado no retângulo informado, o array vem vazio.&nbsp; Observação:&nbsp; O array retornado pela função vem ordenado pela posição Z dos itens quando há sobreposição. Isto é, quando um item ocupa o mesmo espaço que outro item ocupa, a função garante que o item que é desenhado mais abaixo apareça antes no array retornado do que o item que é desenhado acima dele.Se um item achado não sobrepor nenhum outro item, sua ordem no array retornado é indefinida (Ordenação Z apenas dos itens em sobreposição).&nbsp; |
| **list:itemAtPoint(worldX, worldY \[, layer\])** | Dada uma posição em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>), retorna um [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) do scene que se encontra neste ponto.&nbsp; Parâmetros: worldX - Número em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>) que contem a coordenada X da ponto. worldY - Número em [métrica de mundo](<MetricadoMundovsMetricadaTela.md>) que contem a coordenada Y do ponto. (OPCIONAL) layer - String contendo uma [camada](<Ascamadasdotabuleiro.md>). Se este parâmetro for informado, apenas itens que estiverem na camada informada serão retornados por esta função. Se este parâmetro não informado, todos os itens no ponto poderão ser retornados, independente de qual camada pertencerem.&nbsp; Retorno: Se houver algum item na posição informada, retorna um [SceneGraphicItem,](<ObjetoSceneGraphicItem.md>) aquele mais acima na ordem Z, isto é, o que é desenhado acima dos outros. Se não houver item na posição informada, retorna **nil**.&nbsp; |
| **list:clearSelection()** | Deseleciona todos os itens que estavam na lista de seleção do usuário.&nbsp; |
| **list:addToken(\[layer\])** | Adiciona um novo Token ao tabuleiro.&nbsp; Parâmetros: (OPCIONAL) layer - Define em qual camada o novo token deve aparecer. Pode conter "background", "objects" ou "tokens".&nbsp; Retorno: [Objeto SceneToken](<ObjetoSceneToken.md>) representando o novo token.&nbsp; |
| **list:addUserDrawing(\[layer\])** | Adiciona um novo UserDrawing ao tabuleiro.&nbsp; Parâmetros: (OPCIONAL) layer - Define em qual camada o novo user drawing deve aparecer. Pode conter "background", "objects" ou "tokens".&nbsp; Retorno: [Objeto SceneUserDrawing](<ObjetoSceneUserDrawing.md>) representando o novo desenho de usuário.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onItemAdded** | Evento invocado quando um item for adicionado ao scene, seja porque acabou de ser criado ou porque estava invisível e se tornou visível agora.&nbsp; Parâmetros: Item - Um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando o item que foi adicionado. &nbsp; |
| **onItemRemoved** | Evento invocado quando um item for removido do scene, seja porque foi destruído ou porque se tornou invisível.&nbsp; Parâmetros: Item - Um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando o item que foi removido.&nbsp; |
| **onItemSelected** | Evento invocado quando um item for adicionado à seleção de itens do usuário.&nbsp; Parâmetros: Item - Um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando o item que foi selecionado.&nbsp; |
| **onItemDeselected** | Evento invocado quando um item for removido da seleção de itens do usuário.&nbsp; Parâmetros: Item - Um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando o item que foi removido da seleção.&nbsp; |
| **onItemLayerChange** | Evento invocado quando a camada de um item for alterada.&nbsp; Parâmetros: Item - Um objeto [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) representando o item que teve a propriedade "layer" alterada.&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Um plugin que descobre em qual item do scene o usuário clicou

&nbsp;

| require("scene.lua");   SceneLib.registerPlugin(     **function** (scene, attachment)                        *-- Manipular o evento onMouseUp do Viewport afim de detectar o click do mouse      *         scene.viewport.onMouseUp =             **function**(event)                 *-- Converter para métrica de mundo a posição do clique*                 **local** wx, wy = scene.viewport:screenToWorld(event.x, event.y);                                 *-- Localizar o objeto mais acima da posição clicada*                 **local** o = scene.items:itemAtPoint(wx, wy);                                 *-- Exibir uma mensagem*                 **if** o ~= nil **then**                     showMessage("Clique em um objeto");                 **else**                     showMessage("Clique em nada");                 **end**;             **end**;                     **end**); |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Create Professional CHM Help Files with HelpNDoc's Easy-to-Use Tool](<https://www.helpndoc.com/feature-tour/create-chm-help-files/>)_
