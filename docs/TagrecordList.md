# Tag recordList

# Tag recordList

&nbsp;

A tag/componente **recordList** é uma lista de registros na interface. Usada em conjunto com um [NodeDatabase](<NodeDatabase.md>), o controle apresenta um painel na interface para cada item/nodo filho de um campo.

&nbsp;

Observações:

* &nbsp;
  * O painel dos itens é customizado pelo programador.
  * O painel dos itens deve ser um form (ver [Tag form](<Tagform.md>)) e é chamado de Template Form.
  * Você vai precisar de ao menos dois arquivos de extensão ".lfm": Um onde se encontra o recordList, e outro representando o painel item.
  * Cada item possui seu próprio [objeto nodo](<ObjetoNodo.md>), e cada painel de item é automaticamente ligado a seu [escopo de dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>).

## Herança

O **recordList** possui **todas** as características da tag layout.&nbsp;

Veja:

* &nbsp;
  * [Tag layout](<Taglayout.md>)
  * [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

&nbsp;

## Características

Além das características herdadas, o **recordList** possui também as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o recordList passa a usar este campo para salvar e apresentar os itens desta lista.&nbsp; Observações: Deve ser preenchido para o recordList funcionar. O campo informado se tornará um nodo no NodeDatabase&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **templateForm** | String | \<string vazio\> | Identifica qual é o template form do record list, isto é, o painel que será exibido para cada item.&nbsp; Deve ser igual ao atributo "name" de um form contido em algum arquivo ".lfm" do projeto do plugin.&nbsp; Sim, você precisará de outro arquivo ".lfm" para definir fazer esta tag funcionar.&nbsp; |
| **itemHeight** | Float | &#54;4.0 | Altura padrão de cada item do recordList.&nbsp; Este valor é usado quando a propriedade "height" do Template Form não for definida.&nbsp; |
| **minQt** | Integer | &#48; | Define qual é a quantidade mínima de itens que este recordList deve apresentar na interface.&nbsp; Experimente colocar o valor 1 nesta propriedade. As vezes isto ajuda o usuário =)&nbsp; |
| **autoHeight** | Boolean | False | Quando true, o recordList automaticamente se expande/contrai na vertical para melhor visualização de seus itens.&nbsp; Quando false, o recordList apresenta barras de rolagens quando o conteúdo for maior que sua altura.&nbsp; |
| **layout** | Enumerado: "vertical" "horizontal" "horizontalTiles" "verticalTiles" | "vertical" | Define como são organizados visualmente os itens do recordList.&nbsp; "vertical' - Os itens são empilhados de forma vertical, 1 item por linha. A altura de cada painel é definido pela propriedade "height" do templateForm e a largura é ajustada para equivaler à largura do recordList.&nbsp; "horizontal" - Os Itens são empilhados lado a lado, de forma horizontal em apenas 1 linha. A largura de cada painel é definido pelo atributo "width" do templateForm e a altura é ajustada para equivaler à altura do recordList. A propriedade autoHeight é desativada ao usar este layout.&nbsp; "horizontalTiles" - Os itens são dispostos na horizontal (lado a lado), podendo quebrar de linha quando for preciso mais espaço. Tanto a altura quanto a largura de cada painel são definidos pelas propriedades "width" e "height" do templateForm.&nbsp; "verticalTiles" - Os itens são dispostos na vertical, podendo ocupar mais de 1 coluna quando houver espaço para isso. Tanto a altura quanto a largura de cada painel são definidos pelas propriedades "width" e "height" do templateForm.&nbsp; |
| **selectable** | Boolean | False | Indica se o recordList deve funcionar visualmente como uma lista de itens selecionáveis.&nbsp; |
| **selectedNode** | [Objeto Nodo](<ObjetoNodo.md>) | \<\< Não há \>\> | Contém o [Objeto Nodo](<ObjetoNodo.md>) do item atualmente focado/selecionado no recordList.&nbsp; Caso não haja seleção, contém **nil**.&nbsp; Ao atribuir um valor, o recordList procura qual de seus itens está associado ao nodo e o seleciona. Caso não encontre, a seleção será desfeita e selectedNode passará a ser **nil**.&nbsp; |
| **selectedForm** | [Objeto Form](<Tagform.md>) | \<\< Não há \>\> | (Somente Leitura) Contém o [Objeto Form](<Tagform.md>) do item atualmente focado/selecionado no recordList.&nbsp; Caso não haja seleção, contém **nil**.&nbsp; |


&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **recordList:append();** | Insere um novo item ao recordList.&nbsp; Retorno: Caso consiga inserir um novo item, retorna o novo [objeto Nodo ](<ObjetoNodo.md>)do item inserido, senão retorna **nil**.&nbsp; |
| **recordList:sort();** | Força o recordList a executar uma reordenação de seus itens.&nbsp; Observação: Você deve manipular o evento [onCompare](<TagrecordList.md#Evento%20onEndEnumeration>) para definir como os itens serão ordenados. |
| **recordList:scrollToNode(node)** | Se a propriedade "autoHeight" for false, este método movimenta as barras de rolagem do recordList para que o painel do nodo fique visível na tela do usuário.&nbsp; Parâmetros: node - um [objeto Nodo](<ObjetoNodo.md>) identificando o nodo do item que deseja tornar visível na tela do usuário. &nbsp; |


&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onSelect** | Este evento é invocado quando a seleção do recordList muda, isto é, quando um item for selecionado ou quando nenhum item estiver selecionado.&nbsp; Observações:&nbsp; Para descobrir qual item foi selecionado, utilize as propriedades [selectedNode](<TagrecordList.md#propriedade%20selectedNode>) e [selectedForm](<TagrecordList.md#propriedade%20selectedForm>) Este evento é disparado mesmo quando a propriedade "selectable" for false.&nbsp; |
| **onBeginEnumeration** | Este evento é invocado quando o recordList começar a enumerar as mudanças de itens, disparando, logo a seguir, 0 ou mais eventos onItemAdded e/ou onItemRemoved.&nbsp; |
| **onItemAdded** | Evento disparado quando um item for carregado/adicionado visualmente no recordList&nbsp; Parâmetros: node - [Objeto Nodo](<ObjetoNodo.md>) do item adicionado. form - [Objeto Form](<Tagform.md>) do item adicionado.&nbsp; Observações: Este evento representa um item que foi enumerado visualmente na lista e não necessariamente que um novo item foi inserido nos dados salvos. Durante o carregamento dos dados, este evento é disparado para cada item carregado.&nbsp; |
| **onItemRemoved** | Evento disparado quando um item for descarregado/removido visualmente do recordList&nbsp; Parâmetros: node - [Objeto Nodo](<ObjetoNodo.md>) do item removido. form - [Objeto Form](<Tagform.md>) do item removido.&nbsp; Observações: Este evento representa um item que deixou de ser enumerado visualmente da lista e não necessariamente que um item foi deletado dos dados salvos.&nbsp; |
| **onEndEnumeration** | Este evento é invocado quando o recordList terminar de enumerar as mudanças de itens e não houver outro evento onItemAdded e/ou oItemRemoved para disparar a seguir.&nbsp; |
| **onCompare** | Este evento é invocado em momentos chaves para garantir a ordenação dos itens que são mostrados na interface. Quando invocado, o evento traz 2 nodos para que o programador retorne, entre os dois, qual deve aparecer antes.&nbsp; Parâmetros: nodeA - [Objeto Nodo](<ObjetoNodo.md>) contendo um nodo que deve ser comparado. nodeB - [Objeto Nodo](<ObjetoNodo.md>) contendo o outro nodo que deve ser comparado.&nbsp; Retorno: Retorne um número **menor** que 0 se "nodeA" deve ser exibido **antes** de "nodeB" Retorne um número **maior** que 0 se "nodeA" deve ser exibido **depois** de "nodeB" Retorne 0 se os dois são equivalentes na questão da ordem.&nbsp; Observação: Veja o [exemplo 2](<TagrecordList.md#Exemplo%202%20-%20ordenação>) para entender melhor como este evento funciona.&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos

### Exemplo 1 - Lista simples de edits

&nbsp;

| **Arquivo “ficha.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                 **\<button** left="20" top="20" height="25" text="Nova Magia" width="80"                 onClick="self.rclMagias:append();"**/\>** &nbsp; &nbsp; &nbsp; &nbsp;  **\<recordList** name="rclMagias" field="magias" templateForm="frmItemDeMagia"                     left="20" top="60" width="300" autoHeight="true"**/\>** **\</form\>** |


&nbsp;

&nbsp;

&nbsp;

| **Arquivo “itemDeMagia.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmItemDeMagia" height="30" margins="{top=2,bottom=2}"**\>**                **\<edit** align="client" field="nome" margins="{right=2}"**/\>**                 **\<button** align="right" text="Apagar" width="80"                 onClick="ndb.deleteNode(sheet);"**/\>** **\</form\>** |


&nbsp;

A tag recordList do arquivo "ficha.lfm" utiliza o form do arquivo"itemDeMagia.lfm" quando é definido sua propriedade "templateForm".

&nbsp;

![Image](<lib/NewItem100.png>) &nbsp; ![Image](<lib/NewItem101.png>)

&nbsp;

Note que existe uma instância de "frmItemDeMagia" para cada item existente.

&nbsp;

Observação: No botão apagar foi utilizada a [biblioteca "ndb](<BibliotecaNDB.md>)" para apagar um item. Leia mais sobre em:

* [NodeDatabase](<NodeDatabase.md>)
* [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)

&nbsp;

Detalhes que valem prestar a atenção:

* Na tag **form** do arquivo "itemDeMagia.lfm", a propriedade "height" foi definida. Esta é a altura do painel que se repete para cada item. Provavelmente você precisará definir um valor "height" apropriado para seu caso =).
* A variável "sheet" que foi referenciada no arquivo "itemDeMagia.lfm" representa [o objeto nodo](<ObjetoNodo.md>) do item ligado ao painel e não da ficha.

&nbsp;

&nbsp;

### Exemplo 2 - Adicionando uma ordenação ao Exemplo 1

&nbsp;

Manipulando o evento OnCompare parar ordenar de forma crescente pelo atributo "nome" dos itens.

&nbsp;

| **.....** **.....** **\<recordList** name="rclMagias" field="magias" templateForm="frmItemDeMagia"                         left="20" top="60" width="300" autoHeight="true"**\>**         **\<event** name="onCompare"**\>**                 return utils.compareStringPtBr(nodeA.nome, nodeB.nome);         **\</event\>** **\</recordList\>** **...** **...** |
| --- |


&nbsp;

&nbsp;

&nbsp;

Ordenando pelo \<custo, nome\>. Isto é, ordenar pelo custo e considerar o nome em caso de empate.

&nbsp;

| **\<recordList** name="rclMagias" field="magias" templateForm="frmItemDeMagia"                         left="20" top="60" width="300" autoHeight="true"**\>**         **\<event** name="onCompare"**\>**\<\!\[CDATA\[                                if (nodeA.custo or 0) \< (nodeB.custo or 0) then                         return -1;                 elseif (nodeA.custo or 0) \> (nodeB.custo or 0) then                         return 1;                 else                            return utils.compareStringPtBr(nodeA.nome, nodeB.nome);                 end;                                \]\]\>         **\</event\>** **\</recordList\>** |
| --- |


&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Maximize Your PDF Protection with These Simple Steps](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
