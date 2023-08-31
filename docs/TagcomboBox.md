# Tag comboBox

# Tag comboBox

A tag/componente **comboBox** representa uma caixa de seleção que permite o usuário selecionar um item entre vários..

&nbsp;

## Herança

O **comboBox** possui todas as características de uma tag de texto. Veja:

* [Características de todas as tags de textos](<Caracteristicasdetodasastagsdete.md>)
* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

&nbsp;

## Características

Além das características herdadas, a tag **comboBox** também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **text** | String | \<string vazio\> | O texto escolhido pelo usuário e apresentado na interface pelo comboBox.&nbsp; Observação: Este campo retorna e aceita somente valores que estão na propriedade "items"&nbsp; |
| **value** | String | \<string vazio\>\> | O valor associado ao item escolhido e apresentado na interface.&nbsp; Observação: Este campo retorna e aceita somente valores que estão na propriedade "values".&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o comboBox passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **frameRegion** | String | \<string vazio\> | Considerando que o componente/tag pai possui um frame (ver [Frames](<Frames.md>)), ao definir o valor desta propriedade, a posição e tamanho deste controle é automaticamente calculada para se encaixar na Região do Frame de mesmo nome.&nbsp; Veja [Frames e Regiões](<FrameseRegioes.md>)&nbsp; |
| **transparent** | Boolean | false | Quando True, as bordas e o fundo do comboBox não serão exibidas, mostrando apenas o texto conteúdo.&nbsp; |
| **items** | Arranjo de String | {} | Lista de itens do qual o usuário poderá escolher um.&nbsp; Exemplo: {'Lança', 'Espada', 'Adaga'}&nbsp; |
| **values** | Arranjo de String | {} | Lista de valores associados aos itens da propriedade "items".&nbsp; Cada posição deste arranjo é "casado" com a mesma posição do arranjo "items".&nbsp; Observação 1: Não é obrigatório o uso desta propriedade;&nbsp; Observação 2: Quando esta propriedade e o atributo "field" estiverem definidos, este são os valores que serão salvos no NodeDatabase.&nbsp; Exemplo: {'L', 'E', 'A'}&nbsp; |


### Métodos

| **Método** | Descrição |
| --- | --- |
| **comboBox:dropDown()** | "Abre" o comboBox. Exibe a lista de seleção na interface.&nbsp; |


### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando a seleção do comboBox é alterada.&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

## Exemplos

### Exemplo 1 - comboBox simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<comboBox** left="20" top="20" items="{'Lança', 'Espada', 'Adaga'}"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

&nbsp;

![Image](<lib/NewItem78.png>) &nbsp; ![Image](<lib/NewItem79.png>)

&nbsp;

&nbsp;

### Exemplo 2 - comboBox usando a propriedade "values" para escolha do item padrão.

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<comboBox** left="20" top="20" items="{'Lança', 'Espada', 'Adaga'}"                   values="{'L', 'E', 'A'}" value="E"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem80.png>)

&nbsp;

Neste exemplo, devido as propriedades "items" e "values", houve a associação dos seguintes valores e itens:

* L = Lança
* E = Espada
* A = Adaga

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Elevate your documentation to new heights with HelpNDoc's built-in SEO](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
