# Arrastando e Soltando Informações / Drag And Drop

# Arrastando e Soltando informações / Drag and Drop

&nbsp;

Arrastar e Soltar, do inglês "Drag and Drop", é a ação de clicar em um objeto virtual e "arrastá-lo" a uma posição diferente ou sobre um outro objeto virtual. De maneira geral, ele pode ser usado para invocar diversos tipos de ações, ou criar vários tipos de associações entre dois objetos abstratos.

&nbsp;

A sequência básica de ações relacionadas ao drag-and-drop é:

* Clicar, e manter o botão do mouse apertado para "agarrar" o objeto,
* "Arrastar" (drag) o objeto/cursor à posição ou localização desejada,
* "Soltar" (drop) o objeto, soltando o botão pressionado.

&nbsp;

# Fluxo de acontecimento

&nbsp;

No exemplo a seguir, o usuário iniciou o processo drag-and-drop agarrando o objeto preto (1 na figura), arrastando o mouse até o objeto vermelho (3 na figura) e soltando o botão.

![Image](<lib/NewItem226.png>)

&nbsp;

O fluxo segue na seguinte ordem:

* O Usuário clica e mantêm o botão do mouse pressionado sobre o objeto 1 para iniciar um processo de drag-and-drop.
* O Firecast, através do [evento onStartDrag](<Caracteristicasdetodasastagsvisu.md#onStartDrag>) do objeto 1, pede para que o objeto 1 informe as informações que o usuário pode arrastar dele.
* O Plugin SDK3, dentro da chamada do [evento onStartDrag](<Caracteristicasdetodasastagsvisu.md#onStartDrag>), informa ao Firecast o que o usuário pode arrastar do objeto 1. Os dados são adicionados a um [objeto Drag](<ObjetoDrag.md>) (2 na figura) que o Firecast cria automaticamente para esta operação de drag-and-drop específica.
* O Firecast interage com o usuário até que ele passe o mouse sobre uma área de Drop, isto é, de um objeto que aceite que operações drag-and-drop sejam "largadas" sobre ele. O objeto 3 possui uma área de drop.
* O Firecast, através do [evento onStartDrop](<ObjetoDrop.md>) do objeto 3, pede para que o objeto 3 informe o quais informações o usuário pode "largar" sobre ele.
* O Plugin SDK3, dentro da chamada do [evento onStartDrop](<ObjetoDrop.md>), informa ao Firecast o que o usuário pode largar sobre o objeto 3. Os dados são adicionados a um [objeto Drop](<ObjetoDrop.md>) que o Firecast cria automaticamente para receber estas informações.
* O Firecast, com base nas informações do [objeto Drag](<ObjetoDrag.md>) preenchidas pelo objeto 1 e nas informações do [objeto Drop](<ObjetoDrop.md>) preenchidas pelo objeto 3, decide se a operação drag-and-drop pode acontecer. Se um não conseguir lidar com as informações do outro, a operação drag-and-drop não poderá ser concluída.
* Caso a operação Drag-and-Drop puder ser finalizada, o Firecast chama a ação do objeto 3 ou objeto 1 que melhor puder lidar com esta operação.

&nbsp;

# Informações e Ações em uma operação drag-and-drop

&nbsp;

Para que uma operação Drag-And-Drop aconteça, é necessário haver ao menos uma informação e ao menos uma ação capaz de lidar com ela.&nbsp;

&nbsp;

Informações e ações podem existir tanto no [objeto Drag](<ObjetoDrag.md>) quanto no [objeto Drop:](<ObjetoDrop.md>)&nbsp;

* Informações existentes no [objeto Drag](<ObjetoDrag.md>) são combinadas com ações existentes no [objeto Drop](<ObjetoDrop.md>)
* Informações existentes no [objeto Drop](<ObjetoDrop.md>) são combinadas com ações existentes no [objeto Drag](<ObjetoDrag.md>)

&nbsp;

Informações e ações estão atreladas a um DataType, isto é, a uma cadeia de caracteres que define o tipo de dados que é arrastado.

&nbsp;

## DataTypes padrões do Firecast

O programador pode inventar qualquer DataType, porém existem os seguintes que são padrões do Firecast:

&nbsp;

| **DataType padrão** | **Valor transportado** |
| --- | --- |
| text | Uma cadeia de caracteres, um texto qualquer.&nbsp; |
| imageURL | Uma cadeia de caracteres que contém uma URL de uma imagem.&nbsp; |
| player | Um [objeto Jogador](<ObjetoJogador.md>)&nbsp; |
| players | Array de [objeto Jogador](<ObjetoJogador.md>)&nbsp; |
| character | Um [objeto Personagem](<ObjetoPersonagem.md>)&nbsp; |
| characters | Array de [objeto Personagem](<ObjetoPersonagem.md>)&nbsp; |
| libraryItem | Um [objeto BibliotecaItem](<ObjetoBibliotecaItem.md>)&nbsp; |
| libraryItens | Array de [objeto BibliotecaItem](<ObjetoBibliotecaItem.md>)&nbsp; |
| sceneUnitClass | Um [objeto SceneUnitClass](<ObjetoSceneUnitClass.md>)&nbsp; |
| sceneUnitClasses | Array de [objeto SceneUnitClass](<ObjetoSceneUnitClass.md>)&nbsp; |
| imageFile | A table containing the following attributes: name - String with the name of the file. mimeType - String with the MIME type of the image (examples: image/jpeg, image/png) stream - A read-only [Stream object](<ObjetoStream.md>) containing the image file bytes.&nbsp; |
| imageFiles | An array of tables with the same structure as the "imageFile". |


&nbsp;

Observação: Ao utilizar os dataTypes padrões, o RRPG valida e exige que sejam transportados valores adequados conforme a tabela acima.

&nbsp;

&nbsp;

# Exemplos

&nbsp;

## Exemplo 1 - Arrastando um texto de um Label

Experimente arrastar o label para a caixa de digitação de mensagens e comandos do RRPG.

&nbsp;

|  **\<label** text="Me arraste\!" top="150" hitTest="true"**\>**     **\<event** name="OnStartDrag"**\>**         drag:addData("text", "Texto que será arrastado deste label\!");     **\</event\>** **\</label\>**&nbsp; |
| --- |


&nbsp;

&nbsp;

## Exemplo 2 - Arrastando uma imagem e um texto de um Label

Experimente arrastar o label para o log do chat do RRPG\!

&nbsp;

|  **\<label** text="Me arraste\!" top="150" hitTest="true"**\>**     **\<event** name="OnStartDrag"**\>**         drag:addData("text", "Texto que será arrastado deste label\!");         drag:addData("imageURL", "http://www.rrpg.com.br/wp-content/uploads/2013/05/cropped-Untitled-2.png");     **\</event\>** **\</label\>**&nbsp; |
| --- |


&nbsp;

&nbsp;

&nbsp;

## Exemplo 3 - Um controle que captura arraste de imagens.

Arraste uma imagem do browser Chrome ou do jogador para este controle.

&nbsp;

| **\<rectangle** left="150" top="150"            width="150" height="150"            strokeColor="yellow" strokeSize="1"            color="none"**\>**                 **\<image** name="imgImagem" align="client" hitTest="true"**\>**         **\<event** name="OnStartDrop"**\>**             drop:addAction("imageURL",                 function(value)                     self.imgImagem.src = value;                 end);         **\</event\>**     **\</image\>**     **\</rectangle\>**&nbsp; |
| --- |


&nbsp;

&nbsp;

## Exemplo 4 - Um controle que captura arraste de Jogadores.

Arraste um jogador da mesa para este controle\!

&nbsp;

| **\<rectangle** left="150" top="150"            width="150" height="150"            strokeColor="yellow" strokeSize="1"            color="none"            hitTest="true"**\>**                 **\<event** name="OnStartDrop"**\>**         drop:addAction("player",             function(value)                 showMessage("O login deste jogador é: " .. value.login);                   end);     **\</event\>**            **\</rectangle\>**&nbsp; |
| --- |


&nbsp;

## Exemplo 5 - Arrastando uma ação à partir de um botão

Arraste este botão para um jogador da mesa\!

&nbsp;

| **\<button** left="150" top="150" text="meArraste"**\>**     **\<event** name="OnStartDrag"**\>**         drag:addAction("player",             function(destValue)                 showMessage("Você me arrastou para o jogador: " .. destValue.login);             end);     **\</event\>** **\</button\>**&nbsp; |
| --- |



***
_Created with the Personal Edition of HelpNDoc: [Generate EPub eBooks with ease](<https://www.helpndoc.com/create-epub-ebooks>)_
