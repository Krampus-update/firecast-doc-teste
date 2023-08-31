# Tag event

# Tag event

Esta tag especial serve para tratar um evento de uma tag/controle usando a linguagem de programação LUA (veja [A linguagem de programação LUA](<AlinguagemdeprogramacaoLUA.md>)).

&nbsp;

&nbsp;

Observações:&nbsp;

* &nbsp;
  * O corpo da tag contém código de programação LUA
  * Esta tag não cria nenhum controle.
  * Você deve colocar a tag **event** dentro da tag que deseja tratar o evento.

&nbsp;

**Importante**: Não deixe de ler as [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

## Características

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **name** | String | \<Não há valor padrão\> | Identifica o nome do evento que deseja manipular.&nbsp; Cada tag/controle possui seu próprio conjunto de eventos que podem ser tratados. Consulte a documentação\!&nbsp; O preenchimento desta propriedade é obrigatório. |


&nbsp;

## Exemplos

### Exemplo 1 - Olá mundo com um botão.

&nbsp;

A tag **event** está dentro da tag **button**, portanto, a tag está manipulando o evento "onClick" do **button**

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<button** left="20" top="20" text="clique"**\>**                 **\<event** name="onClick"**\>**                         showMessage("Olá mundo\!");                 **\</event\>**         **\</button\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem102.png>)

\
**Importante**: Não deixe de ler as [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

&nbsp;

### Exemplo 2 - Centralizando um controle na interface visual

&nbsp;

A tag **event** está dentro da tag **form**, portanto ela está manipulando o evento "onResize" do **form**.

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<event** name="onResize"**\>**                 self.btnMeuBotao.left = self.width / 2 - self.btnMeuBotao.width / 2;                 self.btnMeuBotao.top = self.height / 2 - self.btnMeuBotao.height / 2;         **\</event\>**                **\<button** name="btnMeuBotao" text="Meu botão\!"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem103.png>)![Image](<lib/NewItem104.png>)![Image](<lib/NewItem105.png>)

&nbsp;

**Importante**: Não deixe de ler as [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

&nbsp;

### Exemplo 3&nbsp; - Definindo funções e as chamando em eventos

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<script\>**\<\!\[CDATA\[                 local function rotacionarUmPouco(controle)                         local angulo = controle.rotationAngle;                         angulo = angulo + 30;                                                while angulo \>= 360 do                                 angulo = angulo - 360;                         end;                                                controle.rotationAngle = angulo;                 end;            \]\]\>         **\</script\>**          **\<button** name="btnMeuBotao" left="20" top="30" text="Botão 1"**\>**                 **\<event** name="onClick"**\>**                         rotacionarUmPouco(self.btnMeuBotao);                 **\</event\>**                        **\</button\>**                **\<button** name="btnMeuBotao2" left="20" top="100" text="Botão 2"**\>**                 **\<event** name="onClick"**\>**                         rotacionarUmPouco(self.btnMeuBotao2);                 **\</event\>**                        **\</button\>**       **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem108.png>) ---\> ![Image](<lib/NewItem107.png>)

&nbsp;

&nbsp;

Neste exemplo foi usada a [Tag script](<Tagscript.md>) para definir uma função e foi usado um bloco [CDATA](<DocumentosXML.md#Lidando%20com%20caracteres%20reservados%20no%20XML>) para lidar com caracteres reservados do XML.

&nbsp;

**Importante**: Não deixe de ler as [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Experience the Power and Ease of Use of a Help Authoring Tool](<https://www.helpndoc.com>)_
