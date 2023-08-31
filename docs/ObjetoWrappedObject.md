# Objeto WrappedObject

# Objeto WrappedObject

Objeto que representa algo no RRPG Firecast, é como uma classe pai abstrata e não faz sentido sua existência por si só.&nbsp;

&nbsp;

Exemplo de objetos que são/herdam de WrappedObject:

* &nbsp;
  * O [objeto Mesa](<ObjetoMesa.md>) é um WrappedObject
  * O [objeto BibliotecaItem](<ObjetoBibliotecaItem.md>) é um WrappedObject
  * O [objeto Personagem](<ObjetoPersonagem.md>) é um WrappedObject
  * etc...

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

Todos objetos que são WrappedObject possuem as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectID** | Integer | Propriedade somente leitura, contém um número único à qual objeto do RRPG Firecast este WrappedObject representa.&nbsp; |
| **objectType** | String | Propriedade somente leitura, contém qual tipo de objeto este WrappedObject representa.&nbsp; Exemplo de valores: "mesa" "jogador" "bibliotecaItem" "personagem" "rolagem" "chatBase" "object"&nbsp; |
| **isObjectAlive** | Boolean | Propriedade somente leitura, contém "true" se o objeto ainda é válido no RRPG ou "false" se já não é mais válido.&nbsp; |


&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **objeto:isType(typeName)** | Retorna true se o objeto é do tipo "typeName", senão retorna false.&nbsp; |



***
_Created with the Personal Edition of HelpNDoc: [Free HTML Help documentation generator](<https://www.helpndoc.com>)_
