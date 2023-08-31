# Objeto SceneBaseObject

# Objeto SceneBaseObject

A classe SceneBaseObject é uma abstração e todos os outros objetos do SceneLib herdam desta classe. Isto significa que não é possível existir um objeto SceneBaseObject diretamente e que sua existência está condicionada à existência dos objetos que herdam dele.

&nbsp;

## Características

Todos os objetos que herdam de SceneBaseObject possuem as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String | (Somente Leitura) Cadeia de caracteres que informam o tipo do objeto. Exemplos de valores: "scene", "viewport", "token", etc..&nbsp; |
| **isObjectAlive** | Boolean | (Somente Leitura) Contém **true** se o objeto ainda estiver vivo no código fonte do RRPG ou **false** se ele já foi destruído&nbsp; |
| **objectID** | Integer | (Somente Leitura) Contém um número único que identifica o objeto no RRPG local. &nbsp; |
| **userData** | [Objeto Nodo](<ObjetoNodo.md>) | (Somente Leitura) Contém um objeto nodo de um NodeDatabase que armazena dados extras que o programador possa querer armazenar.&nbsp; Cada Objeto do Scene 3 possui seu próprio userData.&nbsp; Saiba mais lendo sobre [NodeDatabase](<NodeDatabase.md>) e sobre [Objeto Nodo.](<ObjetoNodo.md>)&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **obj:isType(typeName)** | Retorna true se o objeto é do tipo "typeName", senão retorna false.&nbsp; |
| **obj:beginUpdate()** | Coloca o objeto em estado de alteração. Se você for fazer várias mudanças em um objeto de uma única vez, talvez seja possível obter uma melhoria de performance usando beginUpdate.&nbsp; para cada chamada de beginUpdate, deve haver 1 chamada de endUpdate&nbsp; |
| **obj:endUpdate()** | Retira o objeto do estado de alteração que foi previamente configurado pela função beginUpdate.&nbsp; para cada chamada de beginUpdate, deve haver 1 chamada de endUpdate&nbsp; |
| **obj:newUserDataLink(\[field\])** | Cria e retorna um novo objeto DataLink que monitora um determinado field do&nbsp; objeto nodo "userData".&nbsp; Parâmetros: (OPCIONAL) field - Uma cadeia de string contendo o nome/caminho do campo que será monitorado.&nbsp; Retorna: Um [objeto dataLink](<TagdataLink.md>) que monitora o field solicitado do "userData" deste objeto.&nbsp; Observações: Esta é a melhor maneira de capturar mudança de valores nos valores de userData.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |



***
_Created with the Personal Edition of HelpNDoc: [Transform Your Help Documentation Process with a Help Authoring Tool](<https://www.helpndoc.com>)_
