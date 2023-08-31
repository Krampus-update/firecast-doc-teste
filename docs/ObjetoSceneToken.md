# Objeto SceneToken

# Objeto SceneToken

O Objeto SceneToken representa um único item gráfico no Scene do tipo token, isto é, personagens, objetos e outros símbolos gráficos.

## Herança

O o**bjeto SceneToken** herda de [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) e possui também **TODAS** todas as suas características.

&nbsp;

Veja também:

* &nbsp;
  * [Objeto SceneGraphicItem](<ObjetoSceneGraphicItem.md>)
  * [Objecto SceneBaseObject](<ObjetoSceneBaseObject.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneToken também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String "token" | (Somente Leitura) Contém um texto que identifica o tipo do objeto gráfico - "token".&nbsp; |
| **image** | [Objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>) | (Somente Leitura) Contém um [Objeto SceneDrawingOpBitmap](<ObjetoSceneDrawingOpBitmap.md>) com os detalhes da imagem principal do token.&nbsp; |
| **name** | String | Define o nome do token. Este nome é exibido visualmente no Scene.&nbsp; |
| **facingMode** | Enumerado: "rotate" "drawArrow"&nbsp; | Define como o Scene deve indicar visualmente para que lado o token está virado.&nbsp; "rotate": Rotacionar a imagem para a direção.&nbsp; "drawArrow": Não rotacionar a imagem e desenhar uma seta para a direção.&nbsp; |
| **friendOrFoe** | Enumerado: "unknown" "friend" "neutral" "foe" | Define se este token é hostil ou amigável ao grupo do RRPG.&nbsp; "unknown" - Desconhecido, o mestre não definiu ou é um objeto.&nbsp; "friend" - Este token representa alguém/algo amigável aos personagens do grupo.&nbsp; "neutral" - Este token representa alguém/algo neutro ao grupo.&nbsp; "foe" - Este token representa alguém/algo hostil aos personagens do grupo.&nbsp; |
| **ownerUserID** | String&nbsp; | Contém o login do usuário do RRPG que é dono deste token e pode movimentá-lo.&nbsp; |
| **ownerCharacter** | Inteiro | Contém o ID interno do personagem deste token.&nbsp; Este valor é equivalente ao valor da propriedade "[codigoIntero](<ObjetoBibliotecaItem.md#prop%20codigoInterno>)" do objeto "[BibliotecaItem](<ObjetoBibliotecaItem.md#prop%20codigoInterno>)"&nbsp; 0 = Não foi definido o personagem.&nbsp; |
| **visionIntenseLightRange** | Double | Define, [em métrica de mundo](<MetricadoMundovsMetricadaTela.md>), o alcance da visão do token sob luz intensa.&nbsp; |
| **visionWeakLightRange** | Double | Define, [em métrica de mundo](<MetricadoMundovsMetricadaTela.md>), o alcance da visão do token sob luz fraca (exemplo: Luz do luar, uma vela fraca, etc..)&nbsp; |
| **visionDarknessRange** | Double | Define, [em métrica de mundo](<MetricadoMundovsMetricadaTela.md>), o alcance da visão do token na escuridão total.&nbsp; |
| **visionHaveVision** | Boolean | Define se o token possui visão/enxerga coisas no tabuleiro.&nbsp; Padrão: False&nbsp; |
| **visionAngle** | Double | Define, em graus, o ângulo de visão do token.&nbsp; Padrão: 360&nbsp; |
| **lightIntenseRange** | Double | Define, [em métrica de mundo](<MetricadoMundovsMetricadaTela.md>), o alcance da luz intensa emitida por este token. &nbsp; Se for igual a 0, este token não emite luz intensa.&nbsp; Padrão: 0&nbsp; |
| **lightWeakRange** | Double | Define, [em métrica de mundo](<MetricadoMundovsMetricadaTela.md>), o alcance da luz fraca emitida por este token. &nbsp; Se for igual a 0, este token não emite luz fraca.&nbsp; Padrão: 0&nbsp; |
| **lightAngle** | Double | Define, em graus, o ângulo da luz emitida por este token.&nbsp; Padrão: 360&nbsp; |
| **barValue1** **barValue2** **barValue3**&nbsp; | String | Define o valor atual de uma das barrinhas do token. |
| **barMax1** **barMax2** **barMax3**&nbsp; | String | Define o valor máximo de uma das barrinhas do token. |
| **barColor1** **barColor2** **barColor3**&nbsp; | [String de Cor](<StringdecoresnoLuaForm.md>) | Define a cor de uma das barrinhas do token. |
| **isMine** | Boolean | (Somente Leitura) Contém true se o token for controlado pelo usuário atual do RRPG.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **token:clearMemoryAreas();** | No FogOfWar, limpa a memória do Token das áreas que ele já viu em algum momento do passado.&nbsp; |


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

### Exemplo 1 -&nbsp;

&nbsp;

| &nbsp; |
| --- |


&nbsp;

### Exemplo 2 -&nbsp;

&nbsp;

| &nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Elevate your documentation to new heights with HelpNDoc's built-in SEO](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
