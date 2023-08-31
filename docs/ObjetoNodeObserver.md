# Objeto NodeObserver

# Objeto NodeObserver

Este objeto representa um NodeObserver, um mecanismo capaz de monitorar e notificar mudanças que ocorrerem em um determinado [Nodo](<ObjetoNodo.md>) do [NodeDatabase](<NodeDatabase.md>).

&nbsp;

## Como instanciar um NodeObserver

É possível instanciar um NodeObserver através do método [NDB.newObserver](<BibliotecaNDB.md#ndb.newObserver>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

O objeto NodeObserver possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **enabled** | Boolean | Determina se o NodeObserve está ativo e se pode disparar eventos notificando mudanças. Valor padrão: true&nbsp; |
| **node** | [objeto Nodo](<ObjetoNodo.md>) | Somente leitura, contém o [objeto Nodo](<ObjetoNodo.md>) que está sendo monitorado pelo NodeObserver&nbsp; |


&nbsp;

### Eventos

&nbsp;

| **Nome do evento** | Descrição |
| --- | --- |
| **onChildAdded**&nbsp; | Este evento é invocado quando um [objeto nodo](<ObjetoNodo.md>) filho é criado no nodo que está sendo monitorado.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) filho que foi criado.&nbsp; |
| **onChildRemoved** | Este evento é invocado quando um [objeto nodo](<ObjetoNodo.md>) filho é deletado do nodo que está sendo monitorado.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) filho que foi removido.&nbsp; |
| **onDeepChildAdded** | Este evento é invocado quando um [objeto nodo](<ObjetoNodo.md>) filho é criado no nodo que está sendo monitorado ou em algum de seus filhos (monitoramento recursivo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) filho que foi criado.&nbsp; |
| **onDeepChildRemoved** | Este evento é invocado quando um [objeto nodo](<ObjetoNodo.md>) filho é deletado do nodo que está sendo monitorado ou de algum de seus filhos (monitoramento recursivo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) filho que foi removido.&nbsp; |
| **onChanged** | Este evento é invocado quando o valor de algum atributo do nodo que está sendo monitorado é alterado.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) onde ocorreu a mudança do do valor. attribute - Cadeia de caracteres contendo o nome do atributo que mudou. oldValue - Antigo valor do atributo.&nbsp; |
| **onDeepChanged** | Este evento é invocado quando o valor de algum atributo do nodo ou nodo filho do nodo que está sendo monitorado é alterado (monitoramento recursivo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) onde ocorreu a mudança do do valor. attribute - Cadeia de caracteres contendo o nome do atributo que mudou. oldValue - Antigo valor do atributo.&nbsp; |
| **onPersistedChanged** | Este evento é invocado quando ocorre uma mudança de valor no **servidor** de algum atributo do nodo que está sendo monitrado.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) onde ocorreu a mudança do do valor no servidor. attribute - Cadeia de caracteres contendo o nome do atributo que mudou. oldValue - Antigo valor de servidor do atributo.&nbsp; Observações: Devido a existência de transações no NodeDatabase e também devido à característica assíncrona do NodeDatabase, o valor dos atributos do NodeDatabases podem, temporariamente, não refletir ao valor salvo no servidor e nem ao valor que os outros usuários remotos tem acesso. Este evento é chamado quando alguma alteração é confirmada no lado do Servidor, persistida e disponibilizada para todos os outros usuários remotos. O valor persistido pode ser obtido através da função [NDB.getPersistedAttributeValue()](<BibliotecaNDB.md#ndb.getPersistedAttributeValue>)&nbsp; |
| **onDeepPersistedChanged** | Este evento é invocado quando ocorre uma mudança de valor no **servidor** de algum atributo do nodoou nodo filho que está sendo monitrado (monitoramento recursivo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) onde ocorreu a mudança do do valor no servidor. attribute - Cadeia de caracteres contendo o nome do atributo que mudou. oldValue - Antigo valor de servidor do atributo.&nbsp; Observações: Devido a existência de transações no NodeDatabase e também devido à característica assíncrona do NodeDatabase, o valor dos atributos do NodeDatabases podem, temporariamente, não refletir ao valor salvo no servidor e nem ao valor que os outros usuários remotos tem acesso. Este evento é chamado quando alguma alteração é confirmada no lado do Servidor, persistida e disponibilizada para todos os outros usuários remotos. O valor persistido pode ser obtido através da função [NDB.getPersistedAttributeValue()](<BibliotecaNDB.md#ndb.getPersistedAttributeValue>)&nbsp; |
| **onUserChanged** | Este evento é invocado quando o valor de algum atributo do nodo que está sendo monitorado é alterado **porque** o **usuário local** alterou o conteúdo do do campo, seja editando ele visualmente ou através de código Lua.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) onde ocorreu a mudança do do valor. attribute - Cadeia de caracteres contendo o nome do atributo que mudou. oldValue - Antigo valor do atributo.&nbsp; Observações: Lembre-se, este evento será disparado apenas quando o usuário local alterar o valor de algum dos campos do nodo monitorado.&nbsp; |
| **onDeepUserChanged** | Este evento é invocado quando o valor de algum atributo do nodo ou nodo filho que está sendo monitorado é alterado **porque** o **usuário local** alterou o conteúdo do do campo, seja editando ele visualmente ou através de código Lua (monitoramento recursivo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) onde ocorreu a mudança do do valor. attribute - Cadeia de caracteres contendo o nome do atributo que mudou. oldValue - Antigo valor do atributo.&nbsp; Observações: Lembre-se, este evento será disparado apenas quando o usuário local alterar o valor de algum dos campos do nodo ou nodo filho monitorado.&nbsp; |
| **onDeleted** | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) que está sendo monitorado é apagado.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) que foi removido.&nbsp; |
| **onPermissionListChanged** | Este evento é invocado quando definições de permissões de acesso são inseridas ou removidas do [objeto nodo ](<ObjetoNodo.md>)que está sendo monitorado.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) que sofreu alteração na lista de definições de permissões.&nbsp; |
| **onDeepPermissionListChanged** | Este evento é invocado quando definições de permissões de acesso são inseridas ou removidas do [objeto nodo ](<ObjetoNodo.md>)que está sendo monitorado ou em algum de seus nodos filhos (monitoramento recursivo).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) que sofreu alteração na lista de definições de permissões.&nbsp; |
| **onFinalPermissionsCouldBeChanged** | Este evento é invocado quando as permissões finais de acesso a este nodo podem ter sofrido alterações porque uma permissão em um nodo pai foi removida/inserida e, por consequência, pode ter sido herdada pelo nodo que está sendo monitorado, ou as permissões finais podem ter sofrido alterações porque o usuário mudou de grupo de permissões (Exemplo: O usuário atual virou +mestre).&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) que pode ter sofrido alteração nas permissões finais.&nbsp; |
| **onStateChanged** | Este evento é invocado quando o estado de carregamento do node (ver [ndb.getState](<BibliotecaNDB.md#ndb.getState>)) muda.&nbsp; Parâmetros: node - O [objeto nodo](<ObjetoNodo.md>) que sofreu mudança no estado de carregamento.&nbsp; |


### Observações:

* &nbsp;
  * Se um NodeObserver não for mais acessível pelo código e for destruído pela coleta de lixos do Lua, os eventos não serão mais disparados.

&nbsp;

## Exemplos

### Exemplo 1 - Monitorando um Node "sheet"

&nbsp;

| self.observer = ndb.newObserver(sheet);        self.observer.onChildAdded =         **function**(node)                 *--  Esta função será chamada quando um novo Nodo Filho for criado em sheet*         **end**;           self.observer.onChildRemoved =         **function**(node)                 *--  Esta função será chamada quando um nodo Filho for removido de sheet*         **end**;                   self.observer.onChanged =         **function**(node, attribute, oldValue)                 *-- Esta função será chamada quando algum atributo de sheet mudar de valor*                 *-- attribute possui o nome do atributo que sofreu alteração*         **end**; |
| --- |


&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Create Encrypted, Password-Protected PDFs](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
