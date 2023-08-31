# Objeto Nodo

# Objeto Nodo de um NodeDatabase

Um Objeto Nodo é uma tabela LUA com um comportamento diferenciado que representa um nó/nodo de um NodeDatabase. Suas principais características são:

&nbsp;

&nbsp;

* Aparentam ser uma tabela/objeto LUA normal. Isto é, você pode ler e atribuir propriedades como faria com qualquer outra tabela/objeto LUA.
* Todas as alterações feitas no objeto nodo são salvas e sincronizadas automaticamente com as outras pessoas que estão acessando o mesmo NodeDatabase.
* Quando outras pessoas alteram atributos do nodo, o seu objeto nodo recebe e reflete tais alterações automaticamente.
* Não é possível atribuir uma “função” a uma propriedade do nodo.
* Quando se atribui uma tabela LUA a uma propriedade do nodo, uma cópia recursiva de todos os valores é realizada.&nbsp;
* O nome dos atributos são case-insensitive, isto é, não são diferenciadas letras minúsculas das maiúsculas (Ex: “nome” e “NoME” representam o mesmo atributo do nodo).

&nbsp;

## Alterando atributos de um Objeto Nodo

&nbsp;

Para alterar um atributo de um Objeto Nodo basta fazer uma atribuição como você faria em qualquer outra tabela/objeto Lua.

&nbsp;

Exemplo:

| require("ndb.lua"); **local** nodoRaiz = ndb.load("MeuNodeDatabase.xml");  *--\[\[ nodoRaiz é um Objeto Nodo --\]\]* nodoRaiz.atributo1 = "valor em string"; nodoRaiz.atributo2 = 2; nodoRaiz.atributo3 = true; nodoRaiz.atributoDeOutroNome = 6.7;  nodoRaiz\["atributo5"\] = "outro valor em string"; nodoRaiz\["atributo6"\] = 9999; nodoRaiz\["atributo7"\] = false; |
| --- |


&nbsp;

&nbsp;

Não tem mistério\! Você atribui normalmente.... Só não são aceitos **function** como valores.&nbsp;

As alterações são salvas automaticamente no documento.

&nbsp;

## Lendo atributos de um Objeto Nodo.

Mais uma vez, não há mistério: Basta acessar normalmente como uma tabela LUA qualquer.

&nbsp;

Exemplo:

| require("ndb.lua"); **local** nodoRaiz = ndb.load("MeuNodeDatabase.xml");  *--\[\[ nodoRaiz é um Objeto Nodo --\]\]*  showMessage(nodoRaiz.atributo1);  **if** nodoRaiz.atributo2 == 2 **then**         *-- faz alguma coisa....* **end**;  nodoRaiz.atributo200 = nodoRaiz.atributo3; nodoRaiz.atributo250 = nodoRaiz.atributo2 + 50; **local** valor = nodoRaiz\["atributoDeOutroNome"\]; valor = nodoRaiz\["atributo3"\]; |
| --- |


&nbsp;

## Removendo um atributo de um Objeto Nodo

&nbsp;

Basta atribuir **nil** ao atributo que deseja remover.

&nbsp;

Exemplo:

| require("ndb.lua"); **local** nodoRaiz = ndb.load("MeuNodeDatabase.xml");  *--\[\[ nodoRaiz é um Objeto Nodo --\]\]*  nodoRaiz.atributoQueDesejoRemover = nil; nodoRaiz.atributo1 = nil; nodoRaiz\["atributo2"\] = nil; |
| --- |


&nbsp;

As alterações são salvas automaticamente no documento.

&nbsp;

## Criando um Objeto Nodo filho

&nbsp;

Basta atribuir uma tabela a uma propriedade....

&nbsp;

Exemplo:

| require("ndb.lua"); **local** nodoRaiz = ndb.load("MeuNodeDatabase.xml");  *--\[\[ nodoRaiz é um Objeto Nodo --\]\]*  *-- Após a linha abaixo, nodoRaiz.nodoFilho será um Objeto Nodo filho de "nodoRaiz" de nome "nodoFilho"* nodoRaiz.nodoFilho = {};    *-- Na linha abaixo, nodoRaiz.nodoFilho2 será um Objeto Nodo filho de "nodoRaiz" de nome "nodoFilho2".* *-- Além disso, o novo Objeto Nodo já possuirá os valores nome="Meu Nome" e idade=7.* nodoRaiz.nodoFilho2 = {nome="Meu Nome", idade=7};  *-- Como nodoRaiz.nodoFilho é um Objeto Nodo, você pode criar um nodo filho "nodoNeto" dentro de *&nbsp; *--"nodoRaiz.nodoFilho" facilmente:* nodoRaiz.nodoFilho.nodoNeto = {};  *-- E pode atribuir propriedades a ele normalmente, pois "nodoNeto" também é um Objeto Nodo.* nodoRaiz.nodoFilho.nodoNeto.atributoDoNeto = "Valor"; |
| --- |


&nbsp;

As alterações são salvas automaticamente no documento.

&nbsp;

## Deletando um Objeto Nodo

basta atribuir **nil** ou usar a função "[ndb.deleteNode(nodo)](<BibliotecaNDB.md#ndb.deleteNode>)"

&nbsp;

Exemplo:

| require("ndb.lua"); **local** nodoRaiz = ndb.load("MeuNodeDatabase.xml");  *--\[\[ nodoRaiz é um Objeto Nodo --\]\]*  *-- apagando o nodo "nodoFilho" e todos seus filhos recursivamente do nodo raiz* nodoRaiz.nodoFilho = nil;  *-- apgando usando a função ndb.deleteNode(node)* ndb.deleteNode(nodoRaiz.nodoFilho2); |
| --- |


&nbsp;

As alterações são salvas automaticamente no documento.

&nbsp;

&nbsp;

## Duplicando um Objeto Nodo

Basta fazer uma atribuição simples...

&nbsp;

Exemplo:

| require("ndb.lua"); **local** nodoRaiz = ndb.load("MeuNodeDatabase.xml");  *--\[\[ nodoRaiz é um Objeto Nodo --\]\]*  *-- criando um nodo filho com valores padrões:* nodoRaiz.nodoFilho = {nome="José", idade=75, corFavorita="red", nodoNeto={}};  *-- duplicando o nodo filho.* nodoRaiz.nodoClone = nodoRaiz.nodoFilho; |
| --- |


&nbsp;

As alterações são salvas automaticamente no documento.

&nbsp;

&nbsp;

## Outras operações em um Objeto Nodo

&nbsp;

* &nbsp;
  * Obter o nome do objeto nodo: ndb.getNodeName(nodo);
  * Limpar o conteúdo do objeto nodo: [ndb.clearNode(nodo);](<BibliotecaNDB.md#ndb.clearNode>)
  * Obter o nodo pai: [ndb.getParent(nodo);](<BibliotecaNDB.md#ndb.getParent>)

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Easily create PDF Help documents](<https://www.helpndoc.com/feature-tour>)_
