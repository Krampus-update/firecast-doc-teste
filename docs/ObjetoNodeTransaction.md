# Objeto NodeTransaction

# Objeto NodeTransaction

Este objeto representa uma transação em um [NodeDatabase](<NodeDatabase.md>), um mecanismo que dá maior controle ao programador sobre as mudanças locais.

Uma Transação é um objeto que armazena localmente todas as mudança realizadas em um NodeDatabase para que você possa decidir, mais tarde, se quer descartá-las ou confirmá-las.

&nbsp;

## Como instanciar um NodeTransaction

É possível instanciar um NodeTransaction através do método [ndb.newTransaction](<BibliotecaNDB.md#ndb.newTransaction()>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Observação importante:

Apenas criar um NodeTransaction não faz com que os dados sejam controlados. É preciso também utilizar os métodos [ndb.pushTransaction](<BibliotecaNDB.md#ndb.pushTransaction()>) e [ndb.popTransaction](<BibliotecaNDB.md#ndb.popTransaction>) para isso.

## Características

O objeto NodeTransaction possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| &nbsp; | &nbsp; | &nbsp; |
| &nbsp; | &nbsp; | &nbsp; |


&nbsp;

### Métodos

&nbsp;

| **Nome do método** | Descrição |
| --- | --- |
| **transaction:commit()** | Confirma as mudanças que estavam armazenadas localmente.&nbsp; Ao realizar Commit, os dados serão salvos em arquivo/Servidor RRPG e compartilhados com os demais usuários.&nbsp; |
| **transaction:rollback()** | Desfaz as mudanças que estavam armazenadas localmente.&nbsp; |
| **transaction:createUndoData()** | Cria um [objeto NodeUndoData](<ObjetoNodeUndoData.md>) que contem as instruções necessário para desfazer todas as mudanças que estão armazenadas localmente.&nbsp; Você pode, então, depois, decidir se deseja desfazer as mudanças guardadas utilizando o método [transaction:applyUndoData](<ObjetoNodeTransaction.md#applyUndoData()>)&nbsp; Observações: Armazenar o NodeUndoData é uma ótima forma de criar recursos parecidos com o famoso "ctrl+z" Esta função deve ser chamada antes de invocar "commit" para ter o efeito esperado.&nbsp; |
| **transaction:applyUndoData(undoData)** | Aplica as instruções de um [objeto NodeUndoData](<ObjetoNodeUndoData.md>) para desfazer mudanças previamente feitas.&nbsp; Parâmetros: undoData - O [objeto NodeUndoData](<ObjetoNodeUndoData.md>) que contém o material/instruções para desfazer mudanças, criado previamente pela função [transaction:createUndoData()](<ObjetoNodeTransaction.md#createUndoData()>)&nbsp; Observações: Após invocar este método, ainda é necessário invocar "commit" para que os dados sejam de fato desfeitos Materiais de undo devem ser aplicados na ordem reversa que ocorreram e apenas uma vez. Desfazer mudanças fora de ordem ou mais de uma vez leva a um comportamento indefinido&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Exemplo de uso do Transaction

&nbsp;

| **local** tr1 = ndb.newTransaction(sheet); **local** tr2 = ndb.newTransaction(sheet);   sheet.nome = "Maria"; *-- Mudança 1*   ndb.pushTransaction(sheet, tr1);        sheet.idade = 20; *-- Mudança 2*   ndb.pushTransaction(sheet, tr2); sheet.nome = "Ana";  *-- Mudança 3* ndb.popTransaction(sheet);   sheet.altura = "1.60m";  *-- Mudança 4* ndb.popTransaction(sheet);   tr2:rollback();   *--\[\[*     *Ao final da execução:*     *\* Mudança 1 -*         *Será salva e compartilhada com todos, pois foi realizada fora de qualquer transação.*             *\* Mudanças 2 e 4 -*         *Será mantida APENAS localmente e ninguém mais enxergará as mudanças, pois foram feitas na transação "tr1" e esta não recebeu nem commit e nem rollback.*         *Esta mudança local existirá enquanto o objeto "tr1" existir. Quando ele for destruído pelo coletor de lixo do Lua, as mudanças serão desfeitas.*             *\* Mudança 3 -*         *Será desfeita pois foi realizada na transação "tr2" e ela recebeu uma chamada de "rollback"* *\]\]--*&nbsp; |
| --- |


&nbsp;

&nbsp;

### Exemplo 2 - Perguntando ao usuário se ele deseja salvar mudanças feitas

&nbsp;

| **local** tr = ndb.newTransaction(sheet);  &nbsp; ndb.pushTransaction(sheet, tr); sheet.nome = "maria"; sheet.idade = 20; sheet.altura = "1.60m" ndb.popTransaction(sheet);  &nbsp; dialogs.confirmYesNo("Deseja salvar as alterações?",     **function**(resposta)         **if** resposta **then**             tr:commit();         **else**             tr:rollback();         **end**;     **end**);&nbsp; |
| --- |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Benefits of a Help Authoring Tool](<https://www.helpauthoringsoftware.com>)_
