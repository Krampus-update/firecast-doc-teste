# Objeto SceneFogOfWar

# Objeto SceneFogOfWar

O Objeto SceneFogOfWar é responsável por lidar a névoa de guerra do scene.

## Herança

O o**bjeto SceneFogOfWar** herda de [SceneBaseObject](<ObjetoSceneBaseObject.md>) e possui também **TODAS** todas as suas características.

&nbsp;

Veja também:

* &nbsp;
  * [Objecto SceneBaseObject](<ObjetoSceneBaseObject.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneDrawingOpText também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String "fogOfWar" | (Somente Leitura) Contém um texto que identifica o tipo do objeto - "fogOfWar"&nbsp; |
| **enabled** | Boolean | Define se o Fog of War está ativo no tabuleiro.&nbsp; Apenas o mestre pode alterar esta propriedade.&nbsp; |
| **ambientLight** | Enumerado: "intense" "weak" "none" | Define qual é a iluminação ambiente do scene e pode ser:&nbsp; "intense" (Padrão) - Todo o tabuleiro recebe uma iluminação de ambiente Intensa. Exemplo: Ambiente à luz do sol.&nbsp; "weak" - Todo o tabuleiro recebe uma iluminação de ambiente fraca. Exemplo: Luz do luar.&nbsp; "none" - O tabuleiro não recebe nenhum tipo de iluminação do ambiente.&nbsp; |
| **sharingMode** | Enumerado: "individual" "group" | Define como ocorre o compartilhamento de visão entre os membros do grupo.&nbsp; "individual" (Padrão) - Cada membro do grupo enxerga apenas o que seus personagens enxergam.&nbsp; "group" - Cada membro do grupo enxerga o que todo o grupo enxerga.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **fogOfWar:setArea(polygon, areaType)** | Configura uma área do tabuleiro para se comportar como um determinado tipo de área de Fog of War.&nbsp; Parâmetros: polygon - Um array de tabelas que contém propriedades x e y ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)), e cada cada item do array representando um vértice do polígono. Este é o polígono que será configurado. areaType - O tipo que esta área se comportará como. Pode ser um dos seguintes valores: "explorable" - Uma área à explorar "alwaysVisible" - Uma área sempre visível aos jogadores "alwaysHidden" - Uma área sempre escondida dos jogadores "semiVisible" - Uma área parcialmente visível aos jogadores&nbsp; Observações: Apenas o mestre pode configurar áreas do tabuleiro&nbsp; |
| **fogOfWar:resetAreas();** | Reseta todas as áreas definidas no tabuleiro. Isto é, todo o tabuleiro passará a ser uma área do tipo "explorable".&nbsp; Observações: Apenas o mestre pode configurar áreas do tabuleiro&nbsp; |
| **fogOfWar:addOpaqueArea(polygon)** | Adiciona uma área opaca/parede ao tabuleiro.&nbsp; Parâmetros: polygon - Um array de tabelas que contém propriedades x e y ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)), e cada cada item do array representando um vértice do polígono. Este é o polígono que será configurado.&nbsp; Observações: Apenas o mestre pode configurar áreas opacas do tabuleiro.&nbsp; |
| **fogOfWar:removeOpaqueArea(polygon)** | Remove uma área opaca/parede ao tabuleiro.&nbsp; Parâmetros: polygon - Um array de tabelas que contém propriedades x e y ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)), e cada cada item do array representando um vértice do polígono. Este é o polígono que será removido das áreas opacas.&nbsp; Observações: Apenas o mestre pode configurar áreas opacas do tabuleiro.&nbsp; |
| **fogOfWar:resetOpaqueAreas();** | Remove todas as áreas opacas do tabuleiro.&nbsp; Observações: Apenas o mestre pode configurar áreas opacas do tabuleiro.&nbsp; |
| **fogOfWar:testCircleMovementCollisionVsOpaqueAreas(centerX, centerY, r, offsetX, offsetY)** | Verifica se um determinado círculo movendo colide com alguma área opaca/parede do tabuleiro.&nbsp; Parâmetros: centerX - Centro do círculo no eixo X ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) antes de realizar o movimento centerX - Centro do círculo no eixo Y ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) antes de realizar o movimento. r - Raio do círculo ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) offsetX - Define o sentido e comprimento do movimento do círculo no eixo X ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) ... Exemplo: 1.0 significa que o círculo andou 1.0 métrica mundo para a direita. offsetX - dirX - Define o sentido e comprimento do movimento do círculo no eixo Y ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) ... Exemplo: 1.0 significa que o círculo andou 1.0 métrica mundo para baixo.&nbsp; Retorno: Esta função retorna 3 valores na seguinte ordem: true se o ocorre uma colisão durante o movimento ou false Centro do círculo no eixo X ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) onde ocorreu a colisão. Centro do círculo no eixo Y ([em métrica de mundo](<MetricadoMundovsMetricadaTela.md>)) onde ocorreu a colisão.&nbsp; |


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

***
_Created with the Personal Edition of HelpNDoc: [Keep Your PDFs Safe from Unauthorized Access with These Security Measures](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
