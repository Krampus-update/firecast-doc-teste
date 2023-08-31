# Biblioteca NDB

# Biblioteca NDB

A biblioteca ndb provê funções para manipular NodeDatabases, como abrir um NodeDatabase, retornar o nó pai de um nó, etc..

Todas as funções estão contidas na table/variável "NDB" da unidade "ndb.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "ndb.lua"* require("ndb.lua");    *-- Agora é possível acessar as funções da biblioteca* NDB.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca NDB

&nbsp;

| **function** NDB.load(fileName \[, userName\]) |
| --- |


&nbsp;

Carrega um NodeDatabase que está localizado no [HD Virtual](<HDVirtual.md>) do plug-in e retorna o nodo raiz.

&nbsp;

Parâmetros:

* &nbsp;
  * fileName – cadeia de caracteres identificando o nome do arquivo
  * \[Opcional\] userName – Se você desejar fazer controle de permissões em um NodeDatabase local, passe neste parâmetro uma cadeia de caracteres identificando o usuário que está abrindo o database. Normalmente **não** é preciso se preocupar com este parâmetro, e basta omitir seu valor na chamada da função.

&nbsp;

Retorno:

* &nbsp;
  * Retorna um [Objeto Nodo](<ObjetoNodo.md>), representado a raiz do NodeDatabase.
    * Todas as alterações feitas neste nodo (e em seus nodos filhos) serão salvas automaticamente no arquivo passado no parâmetro “fileName”.

&nbsp;

Observações:

* &nbsp;
  * O parâmetro “fileName” é expandido (através da função “[VHD.expandFileName](<BibliotecaVHD.md#expandFileName>)”) antes de procurar o arquivo.
  * Caso o arquivo não exista, um novo é criado automaticamente.
    * Se foi fornecido um caminho curto no parâmetro “fileName” (não relativo à raiz do HD Virtual), então o nome do arquivo é expandido em relação ao diretório “/” (raiz do HD Virtual) antes da criação do arquivo.
  * O formato do arquivo é XML.
  * Se o arquivo especificado fizer parte da pasta [projeto do plug-in,](<ProjetosdePlugin.md>) o NodeDatabase será aberto em modo somente leitura.

&nbsp;

| **function** NDB.newMemNodeDatabase() |
| --- |


&nbsp;

Cria um novo NodeDatabase temporário que reside apenas na memória. Quando o RRPG fecha, os dados salvos neste NodeDatabase são perdidos.

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há.

&nbsp;

Retorno:

* &nbsp;
  * Retorna um [Objeto Nodo](<ObjetoNodo.md>), representado a raiz do NodeDatabase temporário.

&nbsp;

&nbsp;

| **function** NDB.newObserver(node) |
| --- |


&nbsp;

Cria um novo [objeto NodeObserver](<ObjetoNodeObserver.md>) para o nodo passado como parâmetro. Um NodeObserver é capaz de monitorar e notificar as mudanças ocorridas em um determinado Nodo de NodeDatabase.

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) que deseja monitorar mudanças.

&nbsp;

Retorno:

* &nbsp;
  * Um novo [objeto NodeObserver](<ObjetoNodeObserver.md>)

&nbsp;

&nbsp;

| **function** NDB.newTransaction(node) |
| --- |


Cria uma nova transação para controlar como as mudanças são salvas/compartilhadas em um NodeDatabase

&nbsp;

Parâmetros:

* &nbsp;
  * node - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que deseja controlar as mudanças.

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto NodeTransaction](<ObjetoNodeTransaction.md>)

&nbsp;

Observações:

* &nbsp;
  * Apenas criar um NodeTransaction não faz com que as mudanças sejam controladas. É preciso chamar o método [NDB.pushTransaction](<BibliotecaNDB.md#ndb.pushTransaction()>) para ativar a captura de mudanças para o controle.

&nbsp;

&nbsp;

| **function** NDB.isNodeObject(value) |
| --- |


&nbsp;

Verifica se determinado valor é um [objeto nodo](<ObjetoNodo.md>).

&nbsp;

Parâmetros:

* &nbsp;
  * value - O valor que deseja verificar se é um objeto nodo.&nbsp;

&nbsp;

Retorno:

* &nbsp;
  * **true** se o valor passado é um [objeto nodo](<ObjetoNodo.md>) válido
  * **false** se o valor passado não for um [objeto nodo](<ObjetoNodo.md>) válido.

&nbsp;

| **function** NDB.getRoot(node) |
| --- |


&nbsp;

Retorna o nodo raiz de um nodo, isto é, o nodo mais externo do NodeDatabase.

&nbsp;

Parâmetros:

* &nbsp;
  * node - Um [objeto nodo](<ObjetoNodo.md>) do qual se deseja obter a raiz.

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto nodo](<ObjetoNodo.md>) representando o nodo raiz do NodeDatabase.

&nbsp;

&nbsp;

| **function** NDB.getParent(node) |
| --- |


&nbsp;

Retorna o nodo pai de um nodo, isto é, o nodo que contém o nodo passado como parâmetro.

&nbsp;

Parâmetros:

* &nbsp;
  * node - Um [objeto nodo](<ObjetoNodo.md>) do qual se deseja obter o nodo pai.

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto nodo](<ObjetoNodo.md>) representando o nodo pai ou **nil** se o parâmetro node for um nodo raiz.

&nbsp;

&nbsp;

| **function** NDB.getChildNodes(node) |
| --- |


&nbsp;

Retorna todos os nodos filhos de um determinado nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) do qual se deseja obter os nodos filhos.

&nbsp;

Retorno:

* &nbsp;
  * Um arranjo (tabela/objeto LUA) onde cada índice, começando do 1, contém um [objeto nodo](<ObjetoNodo.md>) filho do nodo passado como parâmetro.

&nbsp;

&nbsp;

| **function** NDB.getAttributes(node) |
| --- |


&nbsp;

Retorna uma tabela contendo todos os atributos e&nbsp; valores de um determinado objeto nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) do qual se deseja obter todos os atributos.

&nbsp;

Retorno:

* &nbsp;
  * Uma tabela/objeto LUA contendo pares de nomeAtributo=valorAtributo.

&nbsp;

Observação:

* &nbsp;
  * Esta função não retorna os nodos filhos do objeto nodo. Retorna apenas os atributos.

&nbsp;

&nbsp;

| **function** NDB.getNodeName(node) |
| --- |


&nbsp;

Retorna o nome de um objeto nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) de qual deseja obter o nome.

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres (string) contendo o nome do nodo ou **nil** se o parâmetro node não for um objeto nodo válido.

&nbsp;

| **function** NDB.getPersistedAttributeValue(node, attributeName) |
| --- |


&nbsp;

Retorna o valor que está persistido/salvo no servidor de um atributo de um objeto nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) de qual deseja obter o valor persistido.
  * attributeName - Cadeia de caracteres contendo o nome do atributo/campo que se deseja obter o valor persistido.

&nbsp;

Retorno:

* &nbsp;
  * O valor persistido ou **nil** caso não seja encontrado.

&nbsp;

Observações:

* &nbsp;
  * Devido a existência de transações no NodeDatabase e também devido à caracteristica assíncrona do NodeDatabase, o valor dos atributos do NodeDatabases podem, temporariamente, não refletir ao valor salvo no servidor e nem ao valor que os outros usuários remotos tem acesso.&nbsp;
  * Esta função retorna o valor que foi aprovado pelo servidor e que é conhecido pelos outros usuários remotos.

&nbsp;

&nbsp;

| **function** NDB.createChildNode(node, childName) |
| --- |


&nbsp;

Cria um nodo filho dentro de um nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) que receberá o novo nodo filho.
  * childName - uma cadeia de caracteres (string) contendo o nome do novo nodo.

&nbsp;

Retorno:

* &nbsp;
  * Um [objeto nodo](<ObjetoNodo.md>) representando o nodo filho recém criado ou **nil** caso a operação falhe.

&nbsp;

&nbsp;

| **function** NDB.deleteNode(node) |
| --- |


&nbsp;

Remove um nodo do Node Database.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) que deseja remover.

&nbsp;

Observações:

* &nbsp;
  * Não é possível remover um nodo raiz do NodeDatabase.

&nbsp;

&nbsp;

| **function** NDB.clearNode(node) |
| --- |


&nbsp;

Limpa um objeto nodo, isto é, remove todos os atributos e todos os nodos filhos de um determinado nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - O [objeto nodo](<ObjetoNodo.md>) o qual deseja limpar.

&nbsp;

Observações:

* &nbsp;
  * Diferente da função "ndb.deleteNode", esta função não remove o nodo passado como parâmetro do NodeDatabase.

&nbsp;

&nbsp;

| **function** NDB.copy(destinationNode, sourceNode) |
| --- |


Copia os dados de um node de NodeDatabase para outro node de NodeDatabase.

&nbsp;

Parâmetros:

* &nbsp;
  * destinationNode - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que será o destino da operação de cópia.
  * sourceNode - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que será a fonte da operação de cópia.

&nbsp;

Observações:

* &nbsp;
  * Os dados de destinationNode serão apagados antes da cópia começar.

&nbsp;

&nbsp;

| **function** NDB.beginUpdate(node) |
| --- |


Coloca o Node Database em estado de "em alterações". Enquanto estiver neste estado, as sincronizações de dados e notificações/eventos referentes a alterações no NodeDatabase serão adiadas até que este saia do modo "em alterações".

Alterar o NodeDatabase para o modo de alterações pode melhorar a performance de procedimentos que fazem várias alterações consecutivas no mesmo.&nbsp;

Para tirar o NodeDatabase do estado "em alterações", invoque a função [NDB.endUpdate](<BibliotecaNDB.md#ndb.endUpdate>).&nbsp;

&nbsp;

Parâmetros:

* &nbsp;
  * node - Um [objeto nodo](<ObjetoNodo.md>) cujo NodeDatabase deseja colocar no modo "em alterações".

&nbsp;

Observações:

* &nbsp;
  * Você pode invocar beginUpdate mais de uma vez no mesmo NodeDatabase. Para cada chamada de [NDB.beginUpdate](<BibliotecaNDB.md#ndb.beginUpdate>), deve haver uma chamada de [NDB.endUpdate](<BibliotecaNDB.md#ndb.endUpdate>) para fazer com que o NodeDatabase saia do estado "em alterações".
  * Apesar de ser passado um [objeto nodo](<ObjetoNodo.md>) no parâmetro, o NodeDatabase inteiro será colocado no estado em alterações.

&nbsp;

&nbsp;

| **function** NDB.endUpdate(node) |
| --- |


Faz com que o NodeDatabase saia do modo "em alterações" que havia sido previamente ativado pela função [NDB.beginUpdate.](<BibliotecaNDB.md#ndb.beginUpdate>)

Ao sair do modo "em alterações", as mudanças feitas serão sincronizadas e os devidos eventos/notificações serão invocadas\!

&nbsp;

Parâmetros:

* &nbsp;
  * node - Um [objeto nodo](<ObjetoNodo.md>) cujo NodeDatabase deseja retirado do modo "em alterações".

&nbsp;

Observações:

* &nbsp;
  * Para cada chamada de [NDB.beginUpdate](<BibliotecaNDB.md#ndb.beginUpdate>), deve haver uma chamada de [NDB.endUpdate](<BibliotecaNDB.md#ndb.endUpdate>) para fazer com que o NodeDatabase saia do estado "em alterações".
  * Apesar de ser passado um [objeto nodo](<ObjetoNodo.md>) no parâmetro, o NodeDatabase inteiro será retirado do modo "em alterações".

&nbsp;

&nbsp;

| **function** NDB.getState(node) |
| --- |


&nbsp;

Retorna o estado de um NodeDatabase

&nbsp;

Parâmetros:

* &nbsp;
  * node - Um [objeto nodo](<ObjetoNodo.md>) cujo NodeDatabase deseja verificar o estado.

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres, podendo ser:
    * "open" - O NodeDatabase está aberto e funcional
    * "opening" - O NodeDatabase está abrindo/carregando
    * "closed" - O NodeDatabase está fechado. Algum erro de carregamento pode ter ocorrido ou a conexão com o armazenamento foi perdida.

&nbsp;

| **function** NDB.onReady(node, callback\[, failCallback\]) |
| --- |


&nbsp;

Monitora um NodeDatabase e notifica o programador quando ele estiver pronto para ser usado

&nbsp;

Parâmetros:

* &nbsp;
  * node - Um [objeto nodo](<ObjetoNodo.md>) cujo NodeDatabase deseja monitorar o estado.
  * callback - Um método que será chamado quando o objeto nodo estiver pronto para ser usado, isto é, ele foi completamente carregado e está pronto para ter seus dados acessados.
  * (OPCIONAL) failCallback - Um método que será chamado se ocorrer algum erro durante o carregamento do NodeDatabase.

&nbsp;

Observações:

* &nbsp;
  * Às vezes, apenas ter a referência ao [objeto nodo](<ObjetoNodo.md>) não significa que ele já está pronto para ser usado. Algumas vezes ocorre um carregamento de dados em segundo plano pela internet e, enquanto ocorre este carregamento, o objeto nodo não aceita operações. Esta é uma boa maneira de saber quando o nodeDatabase está de fato pronto\!
  * Quando node já estiver carregado, callback será chamado imediatamente após um delay de 1 milisegundo.
  * Quando node estiver carregando, callback será chamado&nbsp; quando o processo de carregamento chegar ao fim.

&nbsp;

&nbsp;

&nbsp;

| **function** NDB.pushTransaction(node, transaction) |
| --- |


Ativa uma transação em um NodeDatabase.

&nbsp;

Parâmetros:

* &nbsp;
  * node - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que deseja controlar as mudanças.
  * transaction - um [objeto NodeTransaction](<ObjetoNodeTransaction.md>) previamente criado pela função [NDB.newTransaction](<BibliotecaNDB.md#ndb.newTransaction()>) que controlará as próximas mudanças no NodeDatabase.

&nbsp;

Observações:

* &nbsp;
  * Após ativar uma transação, todas as alterações que ocorrerem no NodeDatabase serão mantidas localmente e não serão compartilhadas automaticamente com os outros usuários. Você deverá controlar o que acontecerá com estas mudanças ao invocar "[transaction:rollback()](<ObjetoNodeTransaction.md#transaction:rollback()>)" se quiser desfazê-las ou "[transaction:commit()](<ObjetoNodeTransaction.md#transaction:commit()>)" para confirmá-las e compartilhar-lhas com os outros usuários.
  * Para cada chamada de [NDB.pushTransaction()](<BibliotecaNDB.md#ndb.pushTransaction()>), deve haver uma chamada de [NDB.popTransaction()](<BibliotecaNDB.md#ndb.popTransaction>).

&nbsp;

&nbsp;

| **function** NDB.popTransaction(node) |
| --- |


Desativa a última transação ativada em um NodeDatabase pela função [NDB.pushTransaction](<BibliotecaNDB.md#ndb.popTransaction>)

&nbsp;

Parâmetros:

* &nbsp;
  * node - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que deseja para de controlar as mudanças.

&nbsp;

Observações:

* &nbsp;
  * Para cada chamada de [NDB.pushTransaction()](<BibliotecaNDB.md#ndb.pushTransaction()>), deve haver uma chamada de [NDB.popTransaction()](<BibliotecaNDB.md#ndb.popTransaction>).
  * Se antes de chamar pushTransaction o NodeDatabase já estava sendo controlado por alguma transação, esta transação será restaurada.
  * Apenas invocar este método não é o suficiente para realizar o controle das mudanças. Você o invocar o método "[rollback()](<ObjetoNodeTransaction.md#transaction:rollback()>)" da transaction se quiser desfazer as mudanças capturadas ou invocar o método "[commit()](<ObjetoNodeTransaction.md#transaction:commit()>)" da transaction para confirmar e compartilhar as mudanças capturadas.

&nbsp;

&nbsp;

&nbsp;

| **function** NDB.getServerUTCTime(node) |
| --- |


Retorna a data e hora do servidor do NodeDatabase em UTC (Coordinated Universal Time)

&nbsp;

Parâmetros:

* &nbsp;
  * node - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que deseja consultar o servidor.

&nbsp;

Retorno:

* &nbsp;
  * Um número de ponto flutuante contendo quantos dias se passaram desde 30/12/1899 00:00. Exemplo: 2.75 representa a data 01/01/1900 18:00

&nbsp;

Observações:

* &nbsp;
  * A função retorna imediatamente, mas o valor retornado é um valor aproximado, podendo ser diferente do horário do servidor de fato em alguns segundos.

&nbsp;

# Funções de persistência de dados do NodeDatabase

&nbsp;

| **function** NDB.exportXML(node) |
| --- |


Salva o conteúdo de um node de NodeDatabase como XML

&nbsp;

Parâmetros:

* &nbsp;
  * node - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase que se deseja salvar os dados.

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres representando o conteúdo do Node e nodes filhos como um XML (codificado em UTF-8)

&nbsp;

| **function** NDB.importXML(destinationNode, xmlString) |
| --- |


Carrega os dados de um XML em um node de NodeDatabase.

&nbsp;

Parâmetros:

* &nbsp;
  * destinationNode - um [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase onde os dados serão carregados.
  * xmlString - Uma cadeia de caracteres cujo conteúdo é o XML contendo os dados a serem carregados.

&nbsp;

Observações:

* &nbsp;
  * Os dados de destinationNode serão apagados antes da importação.

&nbsp;

&nbsp;

# Funções de gerenciamento de permissões do NodeDatabase

NodeDatabases permitem definir permissões aos usuários, podendo, por exemplo, selecionar quais pessoas poderão alterar um Objeto Nodo e/ou quais pessoas não poderão saber da existência de algum Objeto Nodo.

&nbsp;

&nbsp;

&nbsp;

| **function** NDB.setPermission(node, selKind, selId, permission, allowance) |
| --- |


&nbsp;

Define uma permissão a alguém a um [Objeto nodo](<ObjetoNodo.md>).

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) o qual deseja definir a permissão.
  * selKind - Selector Kind, uma cadeia de caracteres podendo ser "group" ou "user". A combinação dos parâmetros selKind + selId define a quem esta permissão deve ser aplicada.
  * selId - Selector Id, uma cadeia de caracteres contendo a identificação do usuário ou grupo de usuários a quem esta permissão deve ser aplicada.&nbsp;
    * se selKind for "user", selId contém o login do usuário RRPG que deseja conceder/negar a permissão.
    * se selKind for "group", selId pode conter um dos seguintes valores:
      * "todos" - A permissão será aplicada a TODOS do RRPG
      * "mestresAux" - A permissão será a aplicada a todos os mestres auxiliares da mesa.
      * "mestres" - A permissão será aplicada a todos que possuírem o modo +mestre na mesa.
      * "jogadores" - A permissão será aplicada a todos que possuírem o modo +jogador na mesa.
      * "espectadores" - A permissão será aplicada a todos que forem espectadores na mesa.
      * "criadorDaMesa" - A permissão será aplicada em quem tiver criado a mesa.
      * "criador" - A permissão será aplicada em quem criou o NodeDatabase (Válido somente se for node for de um NodeDatabase de um personagem)
      * "dono" - A permissão será aplicada em quem for dono do NodeDatabase (Válido somente se for node for de um NodeDatabase de um personagem)
      * "cegos" - A permissão será aplicada em quem tiver o modo +cego na mesa.
      * "mudos" - A permissão será aplicada em quem tiver o modo +mudo na mesa.
      * "voices" - A permissão será aplicada em quem tiver o modo +voz na mesa.
  * permission - Uma cadeia de caracteres identificando qual permissão está sendo definida e pode conter um dos seguintes valores:
    * "read" - Permissão para ler valores de atributos do objeto nodo e permissão para saber que o objeto nodo existe.
    * "write" - Permissão para escrever valores de atributos no objeto nodo.
    * "createChild" - Permissão para criar Objetos Nodos filhos ao objeto nodo passado em parâmetro.
    * "delete" - Permissão para apagar Objetos Nodos.
    * "readPermissions" - Permissão para ler as permissões do objeto nodo (Uma meta-permissão).
    * "writePermissions" - Permissão para definir permissões no objeto nodo (Uma meta-permissão).
    * "writeMetaPermissions" - Permissão para definir meta-permissões no nodo. Quem possui esta permissão é capaz de escolher quem pode gerenciar permissões\! (Uma meta-permissão)
  * allowance - Define se a permissão é concedida ou negada. Pode ser um dos seguintes valores:
    * "allow" - Esta cadeia de caracteres define que a permissão é concedida.
    * "deny" - Esta cadeia de caracteres define que a permissão é negada.
    * "strongAllow" - Esta cadeia de caracteres define que a permissão é concedida. A diferença entre "allow" e "strongAllow" se dá quando um usuário for afetado por "deny" e "allow/strongAllow" ao mesmo tempo: Se o usuário for afetado por "deny" e "allow" ao mesmo tempo, "deny" prevalece. Se for afetado por "deny" e "strongAllow" ao mesmo tempo, "strongAllow" prevalece.
    * **nil** - Nil significa: Remover, não definir, não conceder e nem negar esta permissão: A permissão será herdada do objeto nodo Pai do objeto passado como parâmetro.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Se selKind for "user" e selId não identificar um usuário válido do RRPG, está função falhará.
  * As permissões funcionam de forma herdada: Isto é, todos os nodos filhos do "node" também respeitarão esta permissão se ela não for redefinida no filho.
  * Se em um mesmo nodo um usuário for afetado ao mesmo tempo por uma definição de permissão deny e por uma definição de permissão allow, "deny" prevalecerá por ser mais forte que "allow". Se em um mesmo nodo um usuário for afetado ao mesmo tempo por uma definição de permissão deny e por uma definição de permissão strongAllow, "strongAllow" prevalecerá por ser mais forte que "deny".
    * Exemplos de uso em que um usuário pode ser afetado por mais de uma definição de permissão:
      * Você quer que todos os jogadores consigam ver um nodo, exceto José: Adiciona-se uma permissão "group jogadores read allow" e uma permissão "user José read deny". Mesmo fazendo parte do grupo Jogadores, José não terá permissão de leitura por deny ser mais forte que allow.
      * Se você quer que NENHUM jogador consiga ver um nodo, exceto José: Adiciona-se uma permissão "group jogadores read deny" e uma permissão "user José read strongAllow". Mesmo fazendo parte do grupo Jogadores, José terá permissão de leitura por strongAllow ser mais forte que deny.
  * Mesmo que você não defina permissões, todo NodeDatabase possui um conjunto de permissões básicos que são herdados em todos os Nodos caso não sejam redefinidos.
  * Por segurança:
    * Esta função possui um gatilho que não permite o usuário remover sua própria permissão de "read", "readPermissions", "writePermissions" e "writeMetaPermissions" quando for possuidor de tais permissões.
    * Para conceder/negar permissões "read", "write", "createChild" e "delete", o usuário atual deve possuir a permissão "writePermissions". Para conceder/negar as meta-permissões "readPermissions", "writePermissions" e "writeMetaPermissions", o usuário deve possuir também a permissão "writeMetaPermissions". Por padrão, apenas o criador da sala possui "writeMetaPermissions" e todos os mestres possuem "writePermissions".
    * Um Super Usuário não é afetado por nenhuma definição de permissão de usuário e tem acesso total. Quando um usuário for o criador da mesa e estiver com o modo +mestre nesta mesma mesa, ele é considerado um Super Usuário.

&nbsp;

Exemplos:

&nbsp;

| *\-- Não permitir nem os jogadores e nem os espectadores verem os valores de Sheet* NDB.setPermission(sheet, "group", "jogadores", "read", "deny"); NDB.setPermission(sheet, "group", "espectadores", "read", "deny"); *-- Desfazer as permissões acima, voltando para valores padrões/herdados.* NDB.setPermission(sheet, "group", "jogadores", "read", nil); NDB.setPermission(sheet, "group", "espectadores", "read", nil);  *-- Permitir que +jogadores possam alterar valores de sheet* NDB.setPermission(sheet, "group", "jogadores", "write", "allow");  *-- Permitir que o usuário AlyssonRPG tenha permissões de mestre:* NDB.setPermission(sheet, "user", "AlyssonRPG", "read", "allow"); NDB.setPermission(sheet, "user", "AlyssonRPG", "write", "allow"); NDB.setPermission(sheet, "user", "AlyssonRPG", "createChild", "allow"); NDB.setPermission(sheet, "user", "AlyssonRPG", "delete", "allow"); NDB.setPermission(sheet, "user", "AlyssonRPG", "readPermissions", "allow"); NDB.setPermission(sheet, "user", "AlyssonRPG", "writePermissions", "allow"); |
| --- |


&nbsp;

&nbsp;

&nbsp;

| **function** NDB.getPermission(node, selKind, selId, permission) |
| --- |


&nbsp;

Retorna a definição de uma permissão de alguém de um [Objeto nodo](<ObjetoNodo.md>) que foi previamente definida pelo método [NDB.setPermission](<BibliotecaNDB.md#ndb.setPermission>)

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) o qual deseja consultar a permissão.
  * selKind - Selector Kind, uma cadeia de caracteres podendo ser "group" ou "user". A combinação dos parâmetros selKind + selId define de quem a permissão deve ser consultada.
  * selId - Selector Id, uma cadeia de caracteres contendo a identificação do usuário ou grupo de usuários de quem a permissão deve ser consultada.
    * se selKind for "user", selId contém o login do usuário RRPG que deseja consultar a permissão.
    * se selKind for "group", selId pode conter um dos seguintes valores:
      * "todos" - Permissão que foi aplicada a TODOS do RRPG
      * "mestresAux" - Permissão que foi aplicada a todos os mestres auxiliares da mesa.
      * "mestres" - Permissão que foi aplicada a todos que possuírem o modo +mestre na mesa.
      * "jogadores" - Permissão que foi aplicada a todos que possuírem o modo +jogador na mesa.
      * "espectadores" - Permissão que foi aplicada a todos que forem espectadores na mesa.
      * "criadorDaMesa" - Permissão que foi aplicada em quem tiver criado a mesa.
      * "criador" - Permissão que foi aplicada em quem criou o NodeDatabase (Válido somente se for node for de um NodeDatabase de um personagem)
      * "dono" - Permissão que foi aplicada em quem for dono do NodeDatabase (Válido somente se for node for de um NodeDatabase de um personagem)
      * "cegos" - Permissão que foi aplicada em quem tiver o modo +cego na mesa.
      * "mudos" - Permissão que foi aplicada em quem tiver o modo +mudo na mesa.
      * "voices" - Permissão que foi aplicada em quem tiver o modo +voz na mesa.
  * permission - Uma cadeia de caracteres identificando qual permissão está sendo consultada e pode conter um dos seguintes valores:
    * "read" - Permissão para ler valores de atributos do objeto nodo e permissão para saber que o objeto nodo existe.
    * "write" - Permissão para escrever valores de atributos no objeto nodo.
    * "createChild" - Permissão para criar Objetos Nodos filhos ao objeto nodo passado em parâmetro.
    * "delete" - Permissão para apagar Objetos Nodos.
    * "readPermissions" - Permissão para ler as permissões do objeto nodo (Uma meta-permissão).
    * "writePermissions" - Permissão para definir permissões no objeto nodo (Uma meta-permissão).
    * "writeMetaPermissions" - Permissão para definir meta-permissões no nodo. Quem possui esta permissão é capaz de escolher quem pode gerenciar permissões\! (Uma meta-permissão)

&nbsp;

Retorno:

&nbsp; &nbsp; A função pode retornar um dos 4 abaixo:

* &nbsp;
  * "allow"&nbsp; - Cadeia de caracteres que informa que a permissão foi concedida
  * "deny" - Cadeia de caracteres que informa que a permissão foi negada.
  * "strongAllow" - Cadeia de caracteres que informa que a permissão é concedida. A diferença entre "allow" e "strongAllow" se dá quando um usuário for afetado por "deny" e "allow/strongAllow" ao mesmo tempo: Se o usuário for afetado por "deny" e "allow" ao mesmo tempo, "deny" prevalece. Se for afetado por "deny" e "strongAllow" ao mesmo tempo, "strongAllow" prevalece.
  * **nil** - Nil significa que a permissão não foi definida, não foi concedida e nem negada: A permissão está sendo herdada do objeto nodo Pai do objeto passado como parâmetro

&nbsp;

Observações:

* &nbsp;
  * Esta função retorna se há uma definição de permissão em determinado nodo mas não analisa a herança de permissões. Caso queira testar se o usuário possui permissão, seja por uma definição local ou herdada, utilize o método [NDB.testPermission](<BibliotecaNDB.md#ndb.testPermission>)

&nbsp;

&nbsp;

| **function** NDB.testPermission(node, permission) |
| --- |


&nbsp;

Realiza um teste de permissão: Verifica se o usuário atual possui determinada permissão em um objeto nodo, seja permissão herdada ou permissão definida localmente.

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) o qual deseja testar a permissão.
  * permission - Uma cadeia de caracteres identificando qual permissão está sendo testada e pode conter um dos seguintes valores:
    * "read" - Permissão para ler valores de atributos do objeto nodo e permissão para saber que o objeto nodo existe.
    * "write" - Permissão para escrever valores de atributos no objeto nodo.
    * "createChild" - Permissão para criar Objetos Nodos filhos ao objeto nodo passado em parâmetro.
    * "delete" - Permissão para apagar Objetos Nodos.
    * "readPermissions" - Permissão para ler as permissões do objeto nodo (Uma meta-permissão).
    * "writePermissions" - Permissão para definir permissões no objeto nodo (Uma meta-permissão).
    * "writeMetaPermissions" - Permissão para definir meta-permissões no nodo. Quem possui esta permissão é capaz de escolher quem pode gerenciar permissões\! (Uma meta-permissão)

&nbsp;

Retorno:

* &nbsp;
  * Booleano **true** se o usuário possui permissão, senão **false**.

&nbsp;

&nbsp;

&nbsp;

| **function** NDB.enumPermissions(node) |
| --- |


&nbsp;

Retorna todas as permissões que foram definidas em um determinado objeto nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) o qual deseja enumerar as permissão.

&nbsp;

Retorno:

* &nbsp;
  * Um array (tabela Lua indexada de 1 a #retorno), onde cada item é uma tabela contendo as seguintes propriedades:
    * selKind - Selector Kind, uma cadeia de caracteres podendo ser "group" ou "user". A combinação dos parâmetros selKind + selId define a quem a permissão é aplicada.
    * selId - Selector ID, uma cadeia de caracteres contendo a identificação do usuário ou grupo de usuários a quem a permissão é aplicada.
      * se selKind for "user", selId contém o login do usuário RRPG a quem a permissão é aplicada.
      * se selKind for "group", selId pode conter um dos seguintes valores:
        * "todos" - Permissão que foi aplicada a TODOS do RRPG
        * "mestresAux" - Permissão que foi aplicada a todos os mestres auxiliares da mesa.
        * "mestres" - Permissão que foi aplicada a todos que possuírem o modo +mestre na mesa.
        * "jogadores" - Permissão que foi aplicada a todos que possuírem o modo +jogador na mesa.
        * "espectadores" - Permissão que foi aplicada a todos que forem espectadores na mesa.
        * "criadorDaMesa" - Permissão que foi aplicada em quem tiver criado a mesa.
        * "criador" - Permissão que foi aplicada em quem criou o NodeDatabase (Válido somente se for node for de um NodeDatabase de um personagem)
        * "dono" - Permissão que foi aplicada em quem for dono do NodeDatabase (Válido somente se for node for de um NodeDatabase de um personagem)
        * "cegos" - Permissão que foi aplicada em quem tiver o modo +cego na mesa.
        * "mudos" - Permissão que foi aplicada em quem tiver o modo +mudo na mesa.
        * "voices" - Permissão que foi aplicada em quem tiver o modo +voz na mesa.
    * permission - Uma cadeia de caracteres identificando qual permissão foi aplicada e pode conter um dos seguintes valores:
      * "read" - Permissão para ler valores de atributos do objeto nodo e permissão para saber que o objeto nodo existe.
      * "write" - Permissão para escrever valores de atributos no objeto nodo.
      * "createChild" - Permissão para criar Objetos Nodos filhos ao objeto nodo passado em parâmetro.
      * "delete" - Permissão para apagar Objetos Nodos.
      * "readPermissions" - Permissão para ler as permissões do objeto nodo (Uma meta-permissão).
      * "writePermissions" - Permissão para definir permissões no objeto nodo (Uma meta-permissão).
      * "writeMetaPermissions" - Permissão para definir meta-permissões no nodo. Quem possui esta permissão é capaz de escolher quem pode gerenciar permissões\! (Uma meta-permissão)
    * allowance - Define se a permissão foi concedida ou negada. Pode conter um dos seguintes valores:
      * "allow" - Esta cadeia de caracteres define que a permissão foi concedida.
      * "deny" - Esta cadeia de caracteres define que a permissão foi negada.
      * "strongAllow" - Esta cadeia de caracteres define que a permissão é concedida. A diferença entre "allow" e "strongAllow" se dá quando um usuário for afetado por "deny" e "allow/strongAllow" ao mesmo tempo: Se o usuário for afetado por "deny" e "allow" ao mesmo tempo, "deny" prevalece. Se for afetado por "deny" e "strongAllow" ao mesmo tempo, "strongAllow" prevalece.

&nbsp;

&nbsp;

| **function** NDB.resetPermissions(node) |
| --- |


Exclui todas as definições de permissões em um determinado objeto nodo.

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) que deseja limpar as definições de permissões.

&nbsp;

&nbsp;

&nbsp;

| **function** NDB.editPermissions(node) |
| --- |


Apresenta uma interface padrão para o usuário editar as permissões de um Node do NodeDatabase

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) que o usuário editará as permissões.

&nbsp;

&nbsp;

&nbsp;

# Funções de comunicação através do NodeDatabase

NodeDatabases permitem o envio e recebimento de mensagens aos usuários que estão acessando o mesmo NodeDatabase.

&nbsp;

&nbsp;

| **function** NDB.broadcastMessage(node, messageId, message\[, loopBack\]) |
| --- |


Envia uma mensagem a todos os outros usuários que estão com o nodeDatabase aberto.

&nbsp;

Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase a qual deseja enviar uma mensagem
  * messageId - Uma cadeia de caracteres contendo a identificação da mensagem.
  * message - A mensagem a ser transmitida. Aqui são aceitos textos, tabelas lua, números e booleanos.
  * (OPICIONAL) loopBack - Informa se quer que esta mensagem seja retransmitida para você mesmo. Valor padrão: false

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * A mensagem enviada é entregue a todos os outros usuários conectados no NodeDatabase.
  * Para receber as mensagens recebidas, o usuário destinatário deve ter previamente invocado a função [NDB.newBroadcastListener](<BibliotecaNDB.md#newBroadcastListener>)

&nbsp;

&nbsp;

| **function** NDB.newBroadcastListener(node, messageId, callback) |
| --- |


&nbsp;

\
Cria uma escuta de mensagens para receber mensagens postadas pela função [NDB.broadcastMessage](<BibliotecaNDB.md#broadcastMessage>).&nbsp;

\
Parâmetros:

* &nbsp;
  * node - [Objeto nodo](<ObjetoNodo.md>) do NodeDatabase do qual deseja receber mensagens.
  * messageId - Uma cadeia de caracteres contendo a identificação das mensagens que deseja receber. Deve ser igual ao messageId usado na função [NDB.broadcastMessage](<BibliotecaNDB.md#broadcastMessage>).
  * callback - Uma função que será invocada ao receber mensagens. Esta função recebe três parâmetros na seguinte ordem:
    * sender - Cadeia de caracteres contendo o **login** do usuário que enviou a mensagem
    * messageId - Cadeia de caracteres contendo a identificação da mensagem recebida
    * message - A mensagem que foi postada.

&nbsp;

Retorno:

* &nbsp;
  * Retorna um objeto representando o Listener.

&nbsp;

Observações:

* &nbsp;
  * Importante: Mantenha referência ao objeto retornado por esta função enquanto quiser que a escuta esteja ativa. Se o coletor de lixo LUA coletar este objeto, a escuta é destruída e a função callback não será mais invocada.
  * Se quiser destruir a escuta imediatamente, invoque a função destroy do objeto retornado.... obj:destroy();
  * Nos casos das fichas e janelas acopláveis, o RRPG mantém nodeDatabases carregados mesmo após o usuário fechar a janela da ficha. Por este motivo, a função callback pode ser invocada para uma ficha que não possui mais janela. Se fizer uso de mensagens, esteja preparado para este comportamento.

***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Create Encrypted, Password-Protected PDFs](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
