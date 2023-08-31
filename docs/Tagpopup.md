# Tag popup

# Tag popup

&nbsp;

A tag/componente **popup** representa um componente visual que fica escondido na interface e é posteriormente apresentado, tomando a atenção para si, na forma de um popup.

&nbsp;

## Herança

O **popup** possui **todas** as características da tag layout.&nbsp;

Veja:

* &nbsp;
  * [Tag layout](<Taglayout.md>)
  * [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

&nbsp;

## Características

Além das características herdadas, o **popup** possui também as seguintes características:

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **autoScopeNode** | Boolean | true | Define o comportamento dos campos de edição que estão dentro deste popup quando a propriedade "scopeNode" for **nil**.&nbsp; true - se scopeNode for nil, os componentes de edição usarão o scopeNode do formulário.&nbsp; false - se scopeNode for nil, os componentes de edição não funcionarão, pois não haverá um scopeNode.&nbsp; Observação: O valor padrão destee atributo para plugins que forem compilados com o SDK 3.4 ou inferior é false.&nbsp; |
| **cancelable** | Boolean | true | Indica se o popup pode ser cancelado pelo usuário.&nbsp; Quando false, a única maneira de fechar o popup é via programação ao invocar o método "close" com o parâmetro "forcar" igual a true.&nbsp; |
| **backOpacity** | Float &nbsp; | &#48;.85 | Indica a opacidade do fundo ao exibir este popup.&nbsp; Um valor entre 0.0 e 1.0, onde 0.0 = Fundo totalmente transparente e 1.0 = Fundo totalmente opaco.&nbsp; Esta opacidade se refere ao fundo que é aplicado a fim de tirar a atenção da interface e chamar a atenção para o popup.&nbsp; |
| **drawContainer** | Boolean | true | Define se o popup vai automaticamente desenhar uma borda que delimita o conteúdo do popup.&nbsp; |
| **scopeNode,** **nodeObject ou ** **node** | [Objeto Nodo](<ObjetoNodo.md>) | **nil** | Define em qual [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase os controles de edição deste popup devem salvar os dados.&nbsp; Observações:&nbsp; Só é possível alterar esta propriedade utilizando código Lua. Se **nil**, o nodeObject do form será utilizado para salvar dados se a propriedade autoScopeNode for true. Esta propriedade é um "atalho" para os métodos "setNodeObject" e "getNodeObject" desta tag.&nbsp; Veja também:&nbsp; [NodeDatabase](<NodeDatabase.md>) [Escopo de Dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>)&nbsp; |


### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onClose** | Este evento é invocado quando o popup for fechado.&nbsp; Parâmetros: canceled - Boolean indicando se o popup foi cancelado ou se foi fechado normalmente. |
| **onCanClose** | Este evento é invocado quando o popup estiver prestes a ser fechado. Retorne false para impedir o popup de ser fechado ou true para autorizar o fechamento do popup.&nbsp; Parâmetros: canceled - Boolean indicando se o popup será cancelado ou se será fechado normalmente.&nbsp; |
| **onCalculateSize** | Se você quiser definir a largura e altura do popup de forma dinâmica, trate este evento.&nbsp; Parâmetros: dueToResize - Booleano indicando se a interface mudou de tamanho e por isso é necessário recalcular o tamanho do popup. width - Largura padrão height - Altura padrão&nbsp; Retorne 2 números, o primeiro contendo a largura e o segundo contendo a altura (Exemplo: return 100, 200;)&nbsp; |
| **onNodeReady**&nbsp; | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase associado a este popup está pronto para ser usado.&nbsp; Quando este evento é chamado, você pode assumir: a propriedade "node" do poup está diferente de nil e possui uma referência válida para um [objeto nodo](<ObjetoNodo.md>). O processo de carregamento do nodeDatabase associado já chegou ao fim. Você já consegue acessar os dados armazenados nele normalmente.&nbsp; |
| **onNodeUnready** | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase associado a este popup **deixa de estar** pronto para ser usado.&nbsp; Quando este evento é chamado, você pode assumir: a propriedade "node" do popup não contém mais uma referência válida para um objeto nodo.&nbsp; |
| **onNodeChanged** | Este evento é invocado um [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase é associado ou desassociado a este popup.&nbsp; Ver [NodeDatabase](<NodeDatabase.md>)&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

### Métodos

É possível invocar métodos dos controles usando código LUA.

| **Método** | Descrição |
| --- | --- |
| **popup:show();**&nbsp; **ou**&nbsp; **popup:showPopup();**&nbsp; | Exibe o popup na interface.&nbsp; O popup será exibido no centro a interface. &nbsp; |
| **popup:close();**&nbsp; **ou **&nbsp; **popup:closePopup();**&nbsp; | Fecha o popup.&nbsp; |
| **popup:show(placement, control);**&nbsp; **ou**&nbsp; **popup:showPopup(placement, control);**&nbsp; **ou**&nbsp; **popup:showPopupEx(placement, control);**&nbsp; | Exibe o popup na interface permitindo o programador definir onde ela será exibida.&nbsp; Parâmetros: placement - String que define onde o popup será exibido em relação ao "control". Pode ser um destes valores: "bottom" - abaixo de control "top" - acima de control "left" - à esquerda de control "right" - à direita de control "center" - no centro de control "bottomCenter" - abaixo de control e centralizado horizontalmente "topCenter" - acima de control e centralizado horizontalmente "leftCenter" - à esquerda de control e centralizado verticalmente "rightCenter" - à direita de control e centralizado verticalmente "mouse" - onde o mouse está atualmente "mouseCenter" - centralizado onde o mouse está atualmente.&nbsp; control - Um controle/tag lua à qual o parâmetro "placement" se refere. Se nil, o form será utilizado. |
| **popup:close(cancelar, forcar);**&nbsp; **ou**&nbsp; **popup:closePopup(cancelar, forcar);** | Fecha o popup.&nbsp; Parâmetros: cancelar - Booleano indicando se o popup será cancelado ou se será fechado normalmente. Caso este parâmetro seja omitido, o valor padrão "false" será adotado.&nbsp; forcar - Booleano indicando se é para forçar o fechamento do popup mesmo se ele tiver atributo "cancelable" com true. Caso este parâmetro seja omitido, o valor padrão "false" será adotado.&nbsp; |
| **popup:setNodeObject(nodeObject)** | Define em qual [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase os controles de edição deste popup devem salvar os dados.&nbsp; Parâmetros: nodeObject – Um [objeto nodo](<ObjetoNodo.md>) (de um NodeDatabase) ou **nil**.&nbsp; Observação: Se **nil**, o nodeObject do form será utilizado para salvar dados.&nbsp; Veja também:&nbsp; [NodeDatabase](<NodeDatabase.md>) [Escopo de Dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>)&nbsp; |
| **popup:getNodeObject();** | Retorna o [objeto nodo](<ObjetoNodo.md>) (de um NodeDatabase) no qual os controles de edição deste popup devem salvar os dados.&nbsp; **nil** é retornado quando não há nodo associado.&nbsp; Observação: Se **nil**, o nodeObject do form será utilizado para salvar dados.&nbsp; Veja também:&nbsp; [NodeDatabase](<NodeDatabase.md>) [Escopo de Dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>)&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Uma imagem pequena que pode ser ampliada através do uso do popup

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                 *\<\!-- Popup --\>*         **\<popup** name="popMeuPopup" width="400" height="400" backOpacity="0.5"**\>**                 **\<label** align="top" text="Veja só a imagem maior\!" autoSize="true"**/\>**                 **\<image** align="client" src="/imagens/fenix.png"**/\>**                **\</popup\>**                *\<\!-- Invocador do Popup --\>*         **\<image** src="/imagens/fenix.png" left="20" top="20" width="80" height="80"**/\>**                            **\<button** text="Ampliar" width="70" left="25" top="102"                 onClick="self.popMeuPopup:show();"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem81.png>)

&nbsp;

&nbsp;

![Image](<lib/NewItem82.png>)

&nbsp;

Neste exemplo foram usadas também:

* [Tag image](<Tagimage.md>)
* [Tag label](<Taglabel.md>)
* [Tag button](<Tagbutton.md>)

### Exemplo 2 -&nbsp; Mostrando o popup abaixo de um componente na interface

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                 *\<\!-- Popup --\>*                   **\<popup** name="popMeuPopup" width="100" height="100" backOpacity="0.5"**\>**                 **\<label** align="client" horzTextAlign="center" text="Adaga + 1, de tal característica e outro atributo." **/\>**                      **\</popup\>**               *\<\!-- Invocador do Popup --\>*               **\<label** name="labNome" left="20" top="20" width="80" text="Adaga + 1"&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; horzTextAlign="trailing" height="20"**/\>**                             **\<button** text="i" width="20" left="105" top="20" height="20"                 onClick="self.popMeuPopup:show('bottom', self.labNome);"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem83.png>) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ![Image](<lib/NewItem84.png>)


***
_Created with the Personal Edition of HelpNDoc: [What is a Help Authoring tool?](<https://www.helpauthoringsoftware.com/articles/what-is-a-help-authoring-tool/>)_
