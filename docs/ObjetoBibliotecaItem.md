# Objeto BibliotecaItem

# Objeto BibliotecaItem

Este objeto representa um item na biblioteca de uma mesa no RRPG Firecast.

&nbsp;

## Herança

O **Objeto BibliotecaItem** possui todas as características de um WrappedObject. Veja:

* [Objeto WrappedObject](<ObjetoWrappedObject.md>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, o Objeto BibliotecaItem também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **mesa** | [Objeto Mesa](<ObjetoMesa.md>) | Somente leitura, contém o [Objeto Mesa](<ObjetoMesa.md>) que representa em qual mesa este item está.&nbsp; |
| **pai** | [Objeto BibliotecaItem](<ObjetoBibliotecaItem.md>)&nbsp; | Somente leitura, contém o objeto BibliotecaItem que é pai deste item.&nbsp; Observação: Se o item for raiz da biblioteca, esta propriedade conterá **nil**.&nbsp; |
| **filhos** | Arranjo de [Objeto BibliotecaItem](<ObjetoBibliotecaItem.md>) | Contém um arranjo de Objetos BibliotecaItem representando os sub-itens deste item.&nbsp; Um arranjo é uma tabela lua indexada de 1 a N.&nbsp; |
| **tipo** | Enumerado: "biblioteca" "diretorio" "personagem" "imagem" "sceneUnitClass" "scene2" | Somente leitura, contém que tipo de item este é.&nbsp; "biblioteca" - diretório raiz da biblioteca.&nbsp; "diretorio" - uma pasta na biblioteca&nbsp; "personagem" - Um personagem&nbsp; "imagem" - Uma imagem (implementação futura)&nbsp; "sceneUnitClass" - Um item do Scene2&nbsp; "scene2" - Um tabuleiro de Scene 2&nbsp; |
| **codigoInterno** | Integer | Somente Leitura, contém o código interno que identifica este item de biblioteca unicamente no RRPG Firecast.&nbsp; |
| **nome** | String | Somente leitura, contém o nome do item da biblioteca.&nbsp; |
| **loginDono** | String | Somente leitura, contém o login RRPG do usuário que é dono deste item.&nbsp; |
| **dono** | [Objeto Jogador](<ObjetoJogador.md>) | Somente leitura, contém o o objeto Jogador do dono deste item.&nbsp; Observação: Se o dono não estiver na mesa no momento, esta propriedade conterá **nil.** Utilize a propriedade "loginDono" para descobrir o login do dono mesmo se ele não estiver na mesa.&nbsp; |
| **loginCriador** | String | Somente leitura, contém o login do usuário que criou este item.&nbsp; |
| **criador** | [Objeto Jogador](<ObjetoJogador.md>) | Somente leitura, contém o objeto Jogador do usuário que criou este item.&nbsp; Observação: Se o criador não estiver na mesa no momento, esta propriedade conterá **nil.** Utilize a propriedade "loginCriador" se você quiser descobrir quem criou o item mesmo se ele não estiver na mesa.&nbsp; |
| **visivel** | Boolean | Somente leitura, contém true se o item estiver marcado para ser visível a todos da mesa.&nbsp; Observação: Esta propriedade pode conter true mas o item não estar de fato visível a todos. Isto ocorre quando o item está dentro de um item pai que está escondido.&nbsp; Para descobrir se o item está realmente visível a todos, utilize a propriedade "visivelRecursivamente".&nbsp; |
| **visivelRecursivamente** | Boolean | Somente leitura, contém true se o item está realmente visível a todos da mesa.&nbsp; |


&nbsp;

&nbsp;

### Métodos

&nbsp;

| **Método** | Descrição |
| --- | --- |
| **bibliotecaItem:isType(typeName)**&nbsp; | Retorna true se passado "bibliotecaItem" como parâmetro. |


&nbsp;

&nbsp;

## Exemplos

### Exemplo 1 - Obter todos os nomes de todos os itens na biblioteca de uma mesa

&nbsp;

| **local** **function** obterNomesRecursivo(bibItem)         **local** itensFilhos = bibItem.filhos;         **local** nomes = bibItem.nome;                             **local** i;                **for** i = 1, #itensFilhos, 1 **do**                 **local** bibItemFilho = itensFilhos\[i\];                                                  **local** nomesDoFilho = obterNomesRecursivo(bibItemFilho) **or** "";       &nbsp;                 **if** nomesDoFilho ~= "" **then**                         nomes = nomes .. "**\\n**" .. nomesDoFilho;                 **end**;         **end**;                **return** nomes; **end**; &nbsp; **local** nomesDeTodosOsItens = obterNomesRecursivo(umObjetoMesa.biblioteca);    showMessage(nomesDeTodosOsItens); |
| --- |


&nbsp;

&nbsp; &nbsp; \
&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Elevate Your Help Documentation with a Help Authoring Tool](<https://www.helpauthoringsoftware.com/articles/what-is-a-help-authoring-tool/>)_
