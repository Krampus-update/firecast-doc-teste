# Lua Form e NodeDatabase

# Lua Form e NodeDatabase

O Lua Form foi desenvolvido de forma a se conectar facilmente ao [NodeDatabase](<NodeDatabase.md>) para criar interfaces que salvam dados.

&nbsp;

Para integrar um lua form ao Node Database é preciso duas coisas:

* &nbsp;
  * [Preencher o atributo "field"](<LuaFormeNodeDatabase.md#Preenchendo%20o%20atributo%20field>) das [tags que suportam NodeDatabase](<LuaFormeNodeDatabase.md#Tags%20que%20suportam%20NodeDatabase>)
  * Definir um [escopo de dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>) do Lua Form, isto é, informar em qual nodo de qual NodeDatabase o LuaForm salvará os dados.
    * Observação importante: O SDK3 faz isto automaticamente para você se for um [modelo de ficha,](<ModelosdeFichas.md>) se estiver usando a [tag recordList](<TagrecordList.md>) ou se for uma [janela acoplável](<Criarumajanelaacoplaveldemesa.md>).

&nbsp;

&nbsp;

## Tags que suportam NodeDatabase

&nbsp;

As tags/controles que se conectam ao NodeDatabase são:

* &nbsp;
  * [label](<Taglabel.md>)
  * [edit](<Tagedit.md>)
  * [checkBox](<TagcheckBox.md>)
  * [comboBox](<TagcomboBox.md>)
  * [colorComboBox](<TagcolorComboBox.md>)
  * [image](<Tagimage.md>)
  * [imageCheckBox](<TagimageCheckBox.md>)
  * [textEditor](<TagtextEditor.md>)
  * [recordList](<TagrecordList.md>)
  * [dataLink](<TagdataLink.md>)
  * [dataScopeBox](<TagdataScopeBox.md>)
  * [progressBar](<TagprogressBar.md>)

&nbsp;

## Escopo de dados

Toda tag/controle que suporta NodeDatabase precisa de um escopo de dados, isto é, um [objeto nodo](<ObjetoNodo.md>) de um nodedatabase onde os dados serão salvos.

As tags [form,](<Tagform.md>) [popup](<Tagpopup.md>) e [dataScopeBox](<TagdataScopeBox.md>) possuem o método "controle:setNodeObject" que permitem definir o escopo de dados e, após definido um [objeto nodo](<ObjetoNodo.md>) como escopo, todas as tags que estão dentro passarão a salvar/carregar dados neste obeto nodo.

&nbsp;

&nbsp;

Exemplo:

Suponha a seguinte interface:

| **\<form** name="minhaTagForm"**\>**         **\<edit** field="campoNome"**/\>** **\</form\>** |
| --- |


&nbsp;

Se o seguinte trecho de código Lua executar:

| minhaTagForm:setNodeObject(NODO\_A) |
| --- |


o edit passará a ler e salvar dados em NODO\_A.campoNome...\
&nbsp;

\
Agora, se o seguinte trecho de código Lua executar:

| minhaTagForm:setNodeObject(OUTRO\_NODO) |
| --- |


o edit agora passará a ler e salvar dados em OUTRO\_NODO.campoNome...\
\
\
E, por fim, se o seguinte trecho de código Lua executar:

| minhaTagForm:setNodeObject(**nil**) |
| --- |


o edit agora ficará desabilitado, pois utilizamos o atributo "field" mas não há nodo escopo de dados associado.

&nbsp;

&nbsp;

**Importante:** O SDK3 define o escopo de dados automaticamente para os [modelos de fichas](<ModelosdeFichas.md>), ao usar a [tag recordList](<TagrecordList.md>) e para as [janelas acopláveis](<Criarumajanelaacoplaveldemesa.md>):

* &nbsp;
  * Quando o usuário abre uma ficha no RRPG, o SDK3 carrega o NodeDatabase do personagem e define seu [objeto nodo](<ObjetoNodo.md>) raiz como escopo de dados do form.
  * No caso da tag recordList, o SDK3 automaticamente define o escopo de dados de cada painel de item.&nbsp;
  * Quando o usuário ativa um janela acoplável, o SDK 3 carrega o NodeDatabase do form (se ele tiver a propriedade dataType preenchida) e define o [objeto nodo](<ObjetoNodo.md>) raiz como escopo de dados do form.

&nbsp;

## Preenchendo o atributo "field"

&nbsp;

Nas tags que suportam NodeDatabase, o atributo "field" contém o nome do campo de um [objeto nodo](<ObjetoNodo.md>) a qual o controle deve se conectar.

&nbsp;

**Exemplo:**

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<edit** field="nomeESobrenome"**/\>**         **\<edit** field="caracteristicas"**/\>**                **\<label** field="forca"**/\>**         **\<label** field="destreza"**/\>** **\</form\>** |
| --- |


&nbsp;

No exemplo acima, quando a interface estiver rodando, o primeiro [edit](<Tagedit.md>) irá se ligará ao campo "nomeESobrenome" do objeto nodo, isto é:

* &nbsp;
  * Exibirá na interface o conteúdo do campo "nomeESobrenome" do [objeto nodo escopo](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>).
  * Quando alguém alterar o valor do campo "nomeESobrenome" do [objeto nodo escopo](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>), o edit captará a mudança e automaticamente mostrará o novo valor na interface.
    * Desde que estejam acessando o mesmo nodedatabase, este comportamento acontece mesmo se a pessoa que alterar o valor estiver em outro computador.
  * Se o usuário alterar o texto do edit, o novo valor será salvo no campo "nomeESobrenome" do [objeto nodo escopo](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>).

&nbsp;

Idem para as demais tags que tem o atributo "field" definido.

&nbsp;

**Acessando/salvando dados que estão em um nodo filho.**

É possível utilizar o caractere "." para informar que o campo na verdade está em um nodo filho do [nodo escopo](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>).

&nbsp;

Exemplo:

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<edit** field="atributos.modificadores.forca"**/\>**                **\<edit** field="nodoFilho.nodoNeto.campo1"**/\>**               &nbsp; &nbsp; &nbsp; &nbsp; **\<edit** field="nodoFilho.campo2"**/\>**     **\</form\>** |
| --- |


&nbsp;

No exemplo acima, o primeiro edit se ligará ao campo "forca" do nodo de nome "modificadores" que está dentro do nodo de nome "atributos" que, por sua vez, está dentro do [nodo escopo](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>).

Se o usuário alterar o conteúdo do edit e o não existir um nodo de nome "atributos" no nodo escopo, o SDK3 automaticamente criará este nodo antes de salvar os dados. Idem para o nodo "modificadores" dentro do nodo "atributos".

&nbsp;

## Variável sheet

Os códigos que estão dentro de um Lua Form tem acesso à uma variável chamada "sheet" que representa o [objeto nodo escopo](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>) do form.&nbsp;

&nbsp;

Exemplo:

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**              **\<edit** field="campoDeForca"**/\>**    &nbsp; &nbsp; &nbsp; **\<button** onClick="sheet.campoDeForca = 8;"**/\>** **\</form\>** |
| --- |


&nbsp;

No exemplo acima, ao clicar no botão, a propriedade "campoDeForca" será alterado para "8" e a mudança será refletida no edit já que está ligado ao mesmo campo que sofreu alteração.

&nbsp;

Veja também:

* &nbsp;
  * [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)
  * [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)

## Exemplos

### Exemplo 1 - Pequeno cadastro que informa se a pessoa é maior de idade

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<layout** left="20" top="20" height="500" width="250"**\>**                 **\<layout** align="top" height="32"**\>**                         **\<label** align="left" text="Nome: " width="50" horzTextAlign="trailing"**/\>**                         **\<edit** align="client" field="nome" margins="{left=5}"**/\>**                 **\</layout\>**                                **\<layout** align="top" height="32"**\>**                         **\<label** align="left" text="Idade: " width="50" horzTextAlign="trailing"**/\>**                         **\<edit** align="client" field="idade" margins="{left=5}"**/\>**                 **\</layout\>**                                             **\<label** name="labMaiorDeIdade" text="Preencha a idade" align="top" horzTextAlign="center"**/\>**         **\</layout\>**                **\<dataLink** field="idade"**\>**                 **\<event** name="onChange"**\>**                         local idade = tonumber(sheet.idade);                                                if idade ~= nil then                                 if idade \>= 18 then                                         self.labMaiorDeIdade.text = "Maior de idade";                                 else                                         self.labMaiorDeIdade.text = "Menor de idade";                                 end;                         else                                 self.labMaiorDeIdade.text = "Preencha a idade";                         end;                 **\</event\>**         **\</dataLink\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem125.png>)&nbsp; &nbsp; ![Image](<lib/NewItem127.png>)&nbsp; ![Image](<lib/NewItem128.png>)

&nbsp;

Neste exemplo foram usados:

* &nbsp;
  * [Tag layout](<Taglayout.md>)
  * [Tag edit](<Tagedit.md>)
  * [Tag label](<Taglabel.md>)
  * [Tag dataLink](<TagdataLink.md>)
  * [Tag event](<Tagevent.md>)

&nbsp;

Veja também:

* &nbsp;
  * [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)


***
_Created with the Personal Edition of HelpNDoc: [Don't Let Unauthorized Users View Your PDFs: Learn How to Set Passwords](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
