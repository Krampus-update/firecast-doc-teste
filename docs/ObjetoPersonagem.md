# Objeto Personagem

# Objeto Personagem

Este objeto representa um personagem na biblioteca de uma mesa no RRPG Firecast.

&nbsp;

## Herança

O **Objeto Personagem** possui todas as características de um Objeto BibliotecaItem. Veja:

* [Objeto BibliotecaItem](<ObjetoBibliotecaItem.md>)
* [Objeto WrappedObject](<ObjetoWrappedObject.md>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, o Objeto Personagem também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **dataType** | String | Somente leitura, contém o dataType da ficha do personagem, isto é, em qual formato de dados está a ficha do personagem.&nbsp; |
| **escritaBloqueada** | Boolean&nbsp; | Somente leitura, contém true se a ficha do personagem estiver com marcada como edição bloqueada.&nbsp; |
| **avatar** | String | Somente leitura, contém a URL da imagem do personagem.&nbsp; |


&nbsp;

&nbsp;

### Métodos

&nbsp;

| **Método** | Descrição |
| --- | --- |
| **personagem:isType(typeName)**&nbsp; | Retorna true se passado "personagem" como parâmetro.&nbsp; |
| **personagem:loadSheetNDB(callback)** | Abre um [NodeDatabase](<NodeDatabase.md>) do personagem que está fisicamente armazenado no servidor do RRPG.&nbsp; Parâmetros: callback - Uma função que será invocada quando o NodeDatabase for carregado ou quando ocorrer um erro no carregamento. Quando o carregamento for bem sucedido, a função callback será chamada contendo o [Objeto Nodo](<ObjetoNodo.md>) raiz do NodeDatabase no primeiro parâmetro. Este node é o mesmo equivalente ao "sheet" do lua form de fichas. Quando ocorrer algum erro no carregamento, a função callback será chamada contendo **nil** no primeiro parâmetro.&nbsp; Observações: Esta função é assíncrona, isto é, o código LUA continua sua execução normal enquanto o NDB é carregado em segundo plano. É preciso informar o parâmetro "callback" para obter o NodeDatabase carregado. Cada personagem possui apenas um NodeDatabase. Alterações feitas no NodeDatabase aberto por esta função são automaticamente sincronizadas com os outros usuários que também abriram o mesmo NodeDatabase, inclusives com a ficha aberta localmente (se tiver aberta). Se o usuário sair da mesa, o NodeDatabase terá sua conexão cortada e não mais sincronizará as alterações. Por padrão, os usuários com o modo +mestre e o dono do personagem podem ler e alterar o NodeDatabase enquanto os demais usuários podem apenas ler valores. A função "callback" pode demorar um pouco para ser chamada, pois um download precisará ser feito se o nodedatabase do personagem ainda não foi carregado localmente. O que acontece ao executar esta função em um personagem que utiliza SDK 2 ou SDK 1: Um nodedatabase é carregado mesmo assim, porém as alterações feitas aqui não são refletidas na ficha pois os dados reais dela estão salvos em outro formato e outro lugar.&nbsp; |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Free PDF documentation generator](<https://www.helpndoc.com>)_
