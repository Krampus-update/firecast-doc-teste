# Objeto Scene

# Objeto Scene

O Objeto Scene representa um "tabuleiro de combate" aberto pelo usuário e é a instância principal de um Scene e, através deste objeto, o programador consegue acessar todas as propriedades do mesmo.

&nbsp;

O programador **não** consegue instanciar um "Objeto Scene" através do SDK 3, mas:&nbsp;

* &nbsp;
  * Consegue descobrir todos os Scenes abertos pelo usuário utilizando a função [SceneLib.getScenes](<BibliotecaSceneLib.md#getScenes()>)
  * Consegue instalar um plug-in de Scene para todos os plug-ins abertos (e que vierem a ser abertos depois) utilizando a função [SceneLib.registerPlugin](<BibliotecaSceneLib.md#registerPlugin()>).

&nbsp;

## Herança

O o**bjeto Scene** herda de [SceneBaseObject](<ObjetoSceneBaseObject.md>) e possui também todas as suas características.

## Características

Além das características herdadas, o objeto Scene também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **worldWidth** | Double | Define a LARGURA do tabuleiro de combate. O valor desta propriedade contem o valor em [Métrica do Mundo Scene](<MetricadoMundovsMetricadaTela.md>).&nbsp; |
| **worldHeight** | Double | Define a ALTURA do tabuleiro de combate. O valor desta propriedade contem o valor em [Métrica do Mundo Scene](<MetricadoMundovsMetricadaTela.md>).&nbsp; |
| **worldMetricName** | String | Define o nome da [métrica do mundo](<MetricadoMundovsMetricadaTela.md>) que é usada por este scene.&nbsp; Exemplo: "m", "km", "cm", etc..&nbsp; Exemplo2: supondo que a propriedade worldWidth = 60 e worldMetricName = "km", intepreta-se que tabuleiro possui uma largura de 60 quilômetros.&nbsp; |
| **bkgColor** | [String de Color](<StringdecoresnoLuaForm.md>) | Define a cor de fundo do tabuleiro.&nbsp; Exemplo: "white", "black", "#FFDE05"&nbsp; |
| **bkgImageURL** | String | Contém a URL da imagem/bitmap que será renderizada como fundo do tabuleiro.&nbsp; Este valor: Pode ser um endereço de internet (exemplo: “[http://xxxx.com.br/a.png](<http://xxxx.com.br/a.png>)”)&nbsp; Pode ser o caminho de um arquivo contido no pacote do plugin. Pode ser um arquivo que se encontra no [HD Virtual](<HDVirtual.md>) do plugin instalado.&nbsp; |
| **workingLayer** | Enumerado: "background" "objects" "tokens"&nbsp; | Define qual em que camada do scene o usuário está trabalhando.&nbsp; "map" - O usuário está trabalhando na camada Background&nbsp; "objects" - O usuário está trabalhando na camada Objetos&nbsp; "tokens" - O usuário está trabalhando na camada Tokens.&nbsp; Este é um valor local e não é compartilhado com os outros usuários que estão visualizando o mesmo scene.&nbsp; Saiba mais sobre as camadas em: [As camadas do tabuleiro](<Ascamadasdotabuleiro.md>)&nbsp; |
| **viewport** | [Objeto SceneViewport](<ObjetoSceneViewport.md>) | (Somente Leitura) Objeto viewport do Scene. Objeto que contém propriedades sobre a "tela" do Scene, como "Qual região do scene o usuário está vendo", "Qual o zoom que o usuário aplicou no tabuleiro?", etc..&nbsp; |
| **grid** | [Objeto SceneGridLayer](<ObjetoSceneGridLayer.md>) | (Somente Leitura) Objeto que contém características, informações e utilitários a respeito da GRID do scene.&nbsp; |
| **items** | [Objeto SceneGraphicItemList](<ObjetoSceneGraphicItemList.md>) | (Somente Leitura) Objeto que reúne os itens visuais do tabuleiro como tokens.&nbsp; |
| **fogOfWar** | [Objeto SceneFogOfWar](<ObjetoSceneFogOfWar.md>) | (Somente Leitura) Objeto que reúne informações e operações com o FogOfWar/Névoa de Guerra do Tabuleiro de combate.&nbsp; |
| **isGM** | Boolean | (Somente Leitura) True se o usuário atual é mestre deste scene ou false.&nbsp; |
| **isViewingAsGM** | Boolean | True se o usuário atual for mestre e estiver visualizado como mestre do scene.&nbsp; O usuário atual pode ser mestre mas desejar ver como os jogadores estão enxergando o scene, então isGM = true e isViewingAsGM = false.&nbsp; |
| **isViewingWalls** | Boolean | True se o usuário atual for mestre e estiver visualizado as paredes/áreas opacas do tabuleiro.&nbsp; |
| **currentUserID** | String | (Somente Leitura) Contém o login do usuário atual que está utilizando o Scene.&nbsp; |
| **renderAsPlayer** | Boolean | (Somente Leitura) Uma propriedade bem peculiar e mais difícil de explicar. Algumas vezes, mesmo quando "isGM" é true e "isViewingAsGM" é true, o tabuleiro deve ser renderizado como "visualizando como jogador".&nbsp; Esta propriedade foi feita inicialmente pensando na integração do Firecast com o programa "OBS Studio" para streaming. Enquanto o mestre está visualizando o tabuleiro como GM, o tabuleiro deve ser renderizado como jogador para o "OBS Studio".&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **scene:newTransaction()** | Cria um NodeTransaction que poderá ser utilizado para gerenciar as mudanças feitas localmente no Scene.&nbsp; Retorna: Um objeto [NodeTransaction](<ObjetoNodeTransaction.md>) que poderá ser utilizado em scene:pushTransaction()&nbsp; |
| **scene:pushTransaction(transaction)** | Ativa uma transação para controlar mudanças no Scene.&nbsp; Parâmetros: transaction - um [objeto NodeTransaction](<ObjetoNodeTransaction.md>) previamente criado pela função [scene:newTransaction](<ObjetoScene.md#scene:newTransaction()>) que controlará as próximas mudanças no Scene.&nbsp; Observações: Após ativar uma transação, todas as alterações que ocorrerem no Scene serão mantidas localmente e não serão compartilhadas automaticamente com os outros usuários. Você deverá controlar o que acontecerá com estas mudanças ao invocar "[transaction:rollback()](<ObjetoNodeTransaction.md#transaction:rollback()>)" se quiser desfazê-las ou "[transaction:commit()](<ObjetoNodeTransaction.md#transaction:commit()>)" para confirmá-las e compartilhar-lhas com os outros usuários. Para cada chamada de [scene:pushTransaction()](<ObjetoScene.md#scene:pushTransaction()>), deve haver uma chamada de [scene:popTransaction()](<ObjetoScene.md#scene:popTransaction()>).&nbsp; |
| **scene:popTransaction()** | Desativa a última transação ativada no Scene pela função [scene:pushTransaction()](<ObjetoScene.md#scene:pushTransaction()>)&nbsp; Observações: Para cada chamada de [scene:pushTransaction()](<ObjetoScene.md#scene:pushTransaction()>), deve haver uma chamada de [scene:popTransaction()](<ObjetoScene.md#scene:popTransaction()>). Se antes de chamar pushTransaction o Scene já estava sendo controlado por alguma transação, esta transação é restaurada. Apenas invocar este método não é o suficiente para realizar o controle das mudanças. Você o invocar o método "[rollback()](<ObjetoNodeTransaction.md#transaction:rollback()>)" da transaction se quiser desfazer as mudanças capturadas ou invocar o método "[commit()](<ObjetoNodeTransaction.md#transaction:commit()>)" da transaction para confirmar e compartilhar as mudanças capturadas. &nbsp; |
| **scene:broadcastMessage(messageId, message \[, loopBack\])** | Envia uma mensagem a todos os outros usuários que estão com o scene aberto.&nbsp; Parâmetros: messageId - Uma cadeia de caracteres contendo a identificação da mensagem. message - A mensagem a ser transmitida. Aqui são aceitos textos, tabelas lua, números e booleanos. (OPICIONAL) loopBack - Informa se quer que esta mensagem seja retransmitida para você mesmo. Valor padrão: false &nbsp; Observações: A mensagem enviada é entregue a todos os outros usuários conectados no scene. Para receber as mensagens recebidas, o usuário destinatário deve ter previamente invocado a função [scene:newBroadcastListener](<ObjetoScene.md#scene:newBroadcastListener>)&nbsp; |
| **scene:newBroadcastListener(messageId, callback)** |  Cria uma escuta de mensagens para receber mensagens postadas pela função [scene:broadcastMessage ](<ObjetoScene.md#scene:broadcastMessage>)&nbsp; Parâmetros: messageId - Uma cadeia de caracteres contendo a identificação das mensagens que deseja receber. Deve ser igual ao messageId usado na função [scene:broadcastMessage](<ObjetoScene.md#scene:broadcastMessage>). callback - Uma função que será invocada ao receber mensagens. Esta função recebe três parâmetros na seguinte ordem: sender - Cadeia de caracteres contendo o **login** do usuário que enviou a mensagem messageId - Cadeia de caracteres contendo a identificação da mensagem recebida message - A mensagem que foi postada.&nbsp; Retorno: Retorna um objeto representando o Listener.&nbsp; Observações: Importante: Mantenha referência ao objeto retornado por esta função enquanto quiser que a escuta esteja ativa. Se o coletor de lixo LUA coletar este objeto, a escuta é destruída e a função callback não será mais invocada. Se quiser destruir a escuta imediatamente, invoque a função destroy do objeto retornado.... obj:destroy();&nbsp; |
| **scene:sendDelayedUpdates()** |  Force the scene to transmit all the pending delayed updates caused by the network transfer optimization |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onWorkingLayerChange** | Evento que é chamado quando a propriedade [workingLayer](<ObjetoScene.md#workingLayer>) for alterada.&nbsp; |
| **onGMStateChange** | Evento que é chamado quando as propriedades isGM, isViewingAsGM ou isViewingWalls mudarem.&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Um Plugin de Scene que, ao se anexar a um tabuleiro, exibe uma mensagem com algumas características do Scene.

&nbsp;

| require("scene.lua"); require("dialogs.lua");   SceneLib.registerPlugin(     **function** (scene, attachment)                    showMessage("Plugin anexado a um tabuleiro de tamanho " ..                     scene.worldWidth .. scene.worldMetricName .. " x " ..                     scene.worldHeight .. scene.worldMetricName ..                     " de cor de fundo ".. scene.bkgColor);     **end**);&nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Add an Extra Layer of Security to Your PDFs with Encryption](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
