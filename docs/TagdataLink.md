# Tag dataLink

# Tag dataLink

A tag **dataLink** representa um componente não visual (não é exibido na interface) que monitora mudanças em um NodeDatabase.

&nbsp;

Veja também:

* &nbsp;
  * [NodeDatabase](<NodeDatabase.md>)
  * [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)

&nbsp;

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **name** | String | \<string vazio\> | Define um nome para a componente.&nbsp; O nome deve ser único, isto é, dentro de um **form**, não é possível existir 2 controles com o mesmo nome. Se não for definido um nome para o controle no arquivo LFM, um nome único será gerado para ele em tempo de compilação. Nomear controles é especialmente útil quando se quer trabalhar com códigos LUA.&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o dataLink passa a monitorar mudanças no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **fields** | Arranjo de String | {} // \<arranjo vazio\> | Idem à propriedade "field", porém permite monitorar mudanças em mais de um campo com um único dataLink.&nbsp; Observação: Não é possível utilizar as propriedades "fields" e "field" ao mesmo tempo, elas são mutualmente exclusivas.&nbsp; |
| **defaultValue** | String | \<String Vazio\> | Quando definido, se o campo identificado pelo atributo "field" estiver vazio, ele será inicializado com este valor informado.&nbsp; |
| **defaultValues** | Arranjo de String | {} // \<arranjo vazio\> | Idem à propriedade "defaultValue", porém permite definir valores padrões para cada um dos campos informado na propriedade "fields"&nbsp; Observação: Não é possível utilizar as propriedades "defaultValue" e "defaultValues" ao mesmo tempo pois elas são mutualmente exclusivas.&nbsp; |


&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando ocorre uma mudança de valor no campo definido pela propriedade "field" ou quando ocorrer mudança de valor em algum dos campos definidos pela propriedade "fields"&nbsp; Parâmetros/Informações: field - string informando qual campo mudou oldValue - Antigo valor do campo newValue - Novo valor do campo&nbsp; Observações: Este evento pode ser invocado em qualquer uma destas ocasiões: Os dados do nodedatabase da ficha/form acabaram de ser carregados O usuário local alterou o valor de algum campo monitorado pelo dataLink Algum outro usuário remoto alterou algum dos campos monitrados pelo dataLink.&nbsp; |
| **onPersistedChange** | Este evento é invocado quando ocorre uma mudança de valor no campo definido pela propriedade "field" ou quando ocorrer mudança de valor em algum dos campos definidos pela propriedade "fields" no **servidor**.&nbsp; Parâmetros/Informações: field - string informando qual campo mudou oldValue - Antigo valor conhecido do campo no servidor. newValue - Novo valor do campo no servidor.&nbsp; Observações: Devido a existência de transações no NodeDatabase e também devido à característica assíncrona do NodeDatabase, o valor dos atributos do NodeDatabases podem, temporariamente, não refletir ao valor salvo no servidor e nem ao valor que os outros usuários remotos tem acesso. Este evento é chamado quando alguma alteração é confirmada no lado do Servidor, persistida e disponibilizada para todos os outros usuários remotos. O valor persistido pode ser obtido através da função [NDB.getPersistedAttributeValue()](<BibliotecaNDB.md#ndb.getPersistedAttributeValue>)&nbsp; |
| **onUserChange** | Este evento é invocado quando ocorre uma mudança de valor no campo definido pela propriedade "field" ou quando ocorrer mudança de valor em algum dos campos definidos pela propriedade "fields" **porque** o **usuário local** alterou o conteúdo do do campo, seja editando ele visualmente ou através de código Lua.&nbsp; Parâmetros/Informações: field - string informando qual campo mudou oldValue - Antigo valor do campo newValue - Novo valor do campo.&nbsp; Observações: Lembre-se, este evento será disparado apenas quando o usuário local alterar o valor de algum dos campos monitorados pelo dataLink.&nbsp; |
| **onChildAdded** | Este evento é invocado quando um [objeto nodo](<ObjetoNodo.md>) filho é criado dentro do field que está sendo monitorado (se o campo for um nodo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) filho que foi criado.&nbsp; |
| **onChildRemoved** | Este evento é invocado quando um [objeto nodo](<ObjetoNodo.md>) filho é removido de dentro do field que está sendo monitorado (se o campo for um nodo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) filho que foi removido.&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

&nbsp;

## Exemplos:

### Exemplo 1 - Calculando um modificador de atributo de D\&D

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>&nbsp; &nbsp; ** **\<form** name="frmFichaTeste"**\>**                 *\<\!-- Layout da interface --\>*              **\<layout** left="20" top="20" height="25" width="125"**\>**                     **\<label** align="left" text="Força: " autoSize="true"**/\>**                 **\<edit** align="client" horzTextAlign="center" field="atributoForca"**/\>**                               *\<\!-- Modificador --\>*                 **\<label** align="right" width="30" field="modificadorForca" horzTextAlign="center"**/\>**         **\</layout\>**               *\<\!-- Cálculo de campos / uso de dataLink --\>*&nbsp;             **\<dataLink** field="atributoForca"**\>**                 **\<event** name="onChange"**\>**                         **local** valorForca = tonumber(sheet.atributoForca);                                               **if** (valorForca ~= nil) **then**                                 sheet.modificadorForca = math.floor(valorForca / 2) - 5;                                  **if** sheet.modificadorForca \> 0 **then**                                         sheet.modificadorForca = "+" .. sheet.modificadorForca;                                 **end**;                         **else**                                 sheet.modificadorForca = nil;                         **end**                 **\</event\>**         **\</dataLink\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem85.png>)&nbsp; &nbsp; &nbsp; ![Image](<lib/NewItem86.png>)&nbsp; &nbsp; &nbsp; ![Image](<lib/NewItem88.png>)

&nbsp;

Neste exemplo, ligamos um edit ao campo "atributoForca" e um label ao campo "modificadorForca"... Usamos um dataLink para monitorar mudanças em "atributoForca" para calcularmos e salvamos o modificador no campo "modificadorForca" (para que o label possa exibir o valor).

&nbsp;

Veja também:

* &nbsp;
  * [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)
  * [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)

### Exemplo 2 - Somando dois campos na interface

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  *\<\!-- Layout da interface --\>*              **\<layout** left="20" top="20" height="25" width="200"**\>**                     **\<edit** field="parcela1" align="left" horzTextAlign="center" width="50"**/\>**                 **\<label** align="left" text="  +  " autoSize="true"**/\>**         &nbsp;                     **\<edit** field="parcela2" align="left" horzTextAlign="center" width="50"**/\>**                 **\<label** align="left" text="  =  " autoSize="true"**/\>**                                             *\<\!-- Resultado --\>*                 **\<label** align="client" field="resultadoSoma" horzTextAlign="center"**/\>**         **\</layout\>**               *\<\!-- Cálculo de campos / uso de dataLink --\>*                **\<dataLink** fields="{'parcela1', 'parcela2'}"**\>**                 **\<event** name="onChange"**\>**                                        sheet.resultadoSoma = (tonumber(sheet.parcela1) **or** 0) + &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (tonumber(sheet.parcela2) **or** 0);                 **\</event\>**         **\</dataLink\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem89.png>) &nbsp; ![Image](<lib/NewItem91.png>)

&nbsp;

Neste exemplo, usamos o dataLink para monitorar dois campos ao mesmo tempo: "parcela1" e "parcela2"

&nbsp;

Veja também:

* &nbsp;
  * [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)
  * [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)

***
_Created with the Personal Edition of HelpNDoc: [Revolutionize your documentation process with HelpNDoc's online capabilities](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
