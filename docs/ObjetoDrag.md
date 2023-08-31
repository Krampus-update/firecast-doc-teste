# Objeto Drag

# Objeto Drag

Este objeto é responsável por conter informações da operação arrastar-e-soltar em operação.

&nbsp;

Leia mais sobre a operação [Arraste e Solte / Drag And Drop.](<ArrastandoeSoltandoInformacoesDr.md>)

&nbsp;

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **dataCount** | Inteiro | (Somente Leitura) Contém a quantidade de dados associados neste Drag/Arraste.&nbsp; |
| **actionCount** | Inteiro | (Somente Leitura) Contém a quantidade de ações associadas neste Drag/Arraste.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **drag:addData(dataType, dataValue)** | Adiciona um dado a este Drag/Arraste.&nbsp; Parâmetros: dataType - Uma cadeia de caracteres que define o tipo de dados. Existem alguns dataType que são padrões do RRPG mas você pode inventar um dataType novo, se for o caso. Não deixe de ler "[Arrastando e Soltando Informações / Drag And Drop](<ArrastandoeSoltandoInformacoesDr.md>)" para mais informações sobre o DataType dataValue - O valor associado ao dataType&nbsp; |
| **drag:getData(dataType)** | Retorna um dado deste Drag/Arraste.&nbsp; Parâmetros: dataType - Uma cadeia de caracteres que define o tipo de dados. Existem alguns dataType que são padrões do RRPG mas você pode inventar um dataType novo, se for o caso. Não deixe de ler "[Arrastando e Soltando Informações / Drag And Drop](<ArrastandoeSoltandoInformacoesDr.md>)" para mais informações sobre o DataType&nbsp; Retorno: O valor associado ao dataType ou **nil** se não possuir associação.&nbsp; |
| **drag:addAction(dataType, callback)** | Adiciona uma ação a este Drag/Arraste.&nbsp; Parâmetros: dataType - Uma cadeia de caracteres que define o tipo de dados associado a esta ação. Existem alguns dataType que são padrões do RRPG mas você pode inventar um dataType novo, se for o caso. Não deixe de ler "[Arrastando e Soltando Informações / Drag And Drop](<ArrastandoeSoltandoInformacoesDr.md>)" para mais informações sobre o DataType callback - Uma função que será invocada caso o usuário arraste este drag a uma área de drop que contenha informação do tipo "dataType" nela. A função recebe os seguintes 2 parâmetros na ordem: value - O valor da informação provida pela área de drop. drop - [Objeto Drop](<ObjetoDrop.md>) que contém as informações da área de drop combinada.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |


&nbsp;

## Exemplos

***
_Created with the Personal Edition of HelpNDoc: [Leave the tedious WinHelp HLP to CHM conversion process behind with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
