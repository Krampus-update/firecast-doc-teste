# Objeto Drop

# Objeto Drop

Este objeto é responsável por conter informações da área de drop em uma operação arraste e solte / drag and drop.

&nbsp;

Leia mais sobre a operação [Arraste e Solte / Drag And Drop.](<ArrastandoeSoltandoInformacoesDr.md>)

&nbsp;

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **dataCount** | Inteiro | (Somente Leitura) Contém a quantidade de dados associados nesta área de Drop.&nbsp; |
| **actionCount** | Inteiro | (Somente Leitura) Contém a quantidade de ações associadas nesta área de Drop.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **drop:addData(dataType, dataValue)** | Adiciona um dado a esta área de drop.&nbsp; Parâmetros: dataType - Uma cadeia de caracteres que define o tipo de dados. Existem alguns dataType que são padrões do RRPG mas você pode inventar um dataType novo, se for o caso. Não deixe de ler "[Arrastando e Soltando Informações / Drag And Drop](<ArrastandoeSoltandoInformacoesDr.md>)" para mais informações sobre o DataType dataValue - O valor associado ao dataType&nbsp; |
| **drop:getData(dataType)** | Retorna um dado desta área de drop.&nbsp; Parâmetros: dataType - Uma cadeia de caracteres que define o tipo de dados. Existem alguns dataType que são padrões do RRPG mas você pode inventar um dataType novo, se for o caso. Não deixe de ler "[Arrastando e Soltando Informações / Drag And Drop](<ArrastandoeSoltandoInformacoesDr.md>)" para mais informações sobre o DataType&nbsp; Retorno: O valor associado ao dataType ou **nil** se não possuir associação.&nbsp; |
| **drop:addAction(dataType, callback)** | Adiciona uma ação a esta área de drop.&nbsp; Parâmetros: dataType - Uma cadeia de caracteres que define o tipo de dados associado a esta ação. Existem alguns dataType que são padrões do RRPG mas você pode inventar um dataType novo, se for o caso. Não deixe de ler "[Arrastando e Soltando Informações / Drag And Drop](<ArrastandoeSoltandoInformacoesDr.md>)" para mais informações sobre o DataType callback - Uma função que será invocada caso o usuário arraste uma informação que contenha "dataType" nela. A função recebe os seguintes 4 parâmetros na ordem: value - O valor da informação que está sendo arrastada x - A posição na coordenada x de onde a informação está sendo arrastada y -&nbsp; A posição na coordenada y de onde a informação está sendo arrastada drag - [Objeto Drag](<ObjetoDrag.md>) que contém a informação arrastada&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |


&nbsp;

## Exemplos

***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Documentation Capabilities with a Help Authoring Tool](<https://www.helpauthoringsoftware.com>)_
