# Objeto SceneUserDrawing

# Objeto SceneUserDrawing

O Objeto SceneUserDrawing representa um único item gráfico no Scene do tipo "desenho do usuário".

## Herança

O o**bjeto SceneUserDrawing** herda de [SceneGraphicItem](<ObjetoSceneGraphicItem.md>) e possui também **TODAS** todas as suas características.

&nbsp;

Veja também:

* &nbsp;
  * [Objeto SceneGraphicItem](<ObjetoSceneGraphicItem.md>)
  * [Objecto SceneBaseObject](<ObjetoSceneBaseObject.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneUserDrawing também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String "userDrawing" | (Somente Leitura) Contém um texto que identifica o tipo do objeto gráfico - "userDrawing".&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **userDrawing:markAsMyDrawing();** | Marca o UserDrawing como pertencente ao usuário atual.&nbsp; A marca de dono do userDrawing permite usuários com +jogadores desenhar e controlar seus desenhos no scene. &nbsp; Se o usuário atual for MESTRE, esta função transforma o desenho em um desenho que faz parte do scene e não pertence a ninguém.&nbsp; Se o usuário atual for +JOGADOR e se o item tiver acabado de ser criado, esta função marca o desenho como "desenho de jogador".&nbsp; Se o usuário atual for +JOGADOR mas o item já existir, a função não faz nada. |


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
_Created with the Personal Edition of HelpNDoc: [What is a Help Authoring tool?](<https://www.helpauthoringsoftware.com>)_
