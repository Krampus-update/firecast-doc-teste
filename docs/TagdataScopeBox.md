# Tag dataScopeBox

# Tag dataScopeBox

&nbsp;

A tag/componente **dataScopeBox** funciona como a [tag layout](<Taglayout.md>), porém permite definir em qual [objeto Nodo](<ObjetoNodo.md>) seus controles salvarão/lerão os dados (NodeDatabase);

Após definir o nodo escopo, todos os componentes visuais que estão dentro desta tag passarão a ler e salvar os dados neste nodo.

&nbsp;

Saiba mais sobre escopo de dados do NodeDatabase em [Lua Form e NodeDatabase.](<LuaFormeNodeDatabase.md>)

&nbsp;

**Atenção**: A [tag popup](<Tagpopup.md>) não é capturada pelo escopo de dados definido pelo dataScopeBox.

## Herança

O **dataScopeBox** possui **todas** as características de uma [tag layout](<Taglayout.md>).&nbsp;

&nbsp;

Veja:

* &nbsp;
  * [Tag layout](<Taglayout.md>)
  * [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

&nbsp;

## Características

Além das características herdadas, o **dataScopeBox** possui também as seguintes características:

### Propriedades

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **scopeNode,** **nodeObject ou ** **node** | [Objeto Nodo](<ObjetoNodo.md>) | **nil** | Define em qual [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase os controles de edição deste dataScopeBox devem salvar os dados.&nbsp; Observações:&nbsp; Se for **nil**, os controles dentro desta tag que salvam/carregam dados no NodeDatabase ficam desabilitados. Só é possível alterar esta propriedade utilizando código Lua.&nbsp; Veja também:&nbsp; [NodeDatabase](<NodeDatabase.md>) [Escopo de Dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>)&nbsp; |


&nbsp;

### Métodos

É possível invocar métodos dos controles usando código LUA.

| **Método** | Descrição |
| --- | --- |
| **dataScopeBox:setNodeObject(nodeObject)** | Método alternativo para alterar a propriedade "[scopeNode](<TagdataScopeBox.md#propriedade%20scopeNode>)"&nbsp; |
| **dataScopeBox:getNodeObject();** | Método alternativo que retorna o valor da propriedade "[scopeNode](<TagdataScopeBox.md#propriedade%20scopeNode>)"&nbsp; |


&nbsp;

### Eventos da tag dataScopeBox

| **Nome do evento** | Descrição |
| --- | --- |
| **onNodeReady**&nbsp; | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase associado a este dataScopeBox está pronto para ser usado.&nbsp; Quando este evento é chamado, você pode assumir: a propriedade "node" do dataScopeBox está diferente de nil e possui uma referência válida para um [objeto nodo](<ObjetoNodo.md>). O processo de carregamento do nodeDatabase associado já chegou ao fim. Você já consegue acessar os dados armazenados nele normalmente.&nbsp; |
| **onNodeUnready**&nbsp; | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase associado a este dataScopeBox **deixa de estar** pronto para ser usado.&nbsp; Quando este evento é chamado, você pode assumir: a propriedade "node" do dataScopeBox não contém mais uma referência válida para um objeto nodo.&nbsp; |
| **onNodeChanged**&nbsp; | Este evento é invocado um [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase é associado ou desassociado a este dataScopeBox.&nbsp; Ver [NodeDatabase](<NodeDatabase.md>)&nbsp; |


&nbsp;

Veja também [Tratando eventos do Lua Form.](<TratandoeventosdoLuaForm.md>)

## &nbsp;

## Exemplos:

### Exemplo 1 - Lista com Painel de Detalhes

&nbsp;

Veja o tutorial [Criar uma lista dinâmica + painel de detalhes](<Criarumalistadinamicapaineldedet.md>) para ver o exemplo completo .

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Full-featured Kindle eBooks generator](<https://www.helpndoc.com/feature-tour/create-ebooks-for-amazon-kindle>)_
