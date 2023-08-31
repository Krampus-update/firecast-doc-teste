# Tag colorComboBox

# Tag colorComboBox

A tag/componente **colorCmboBox** representa uma caixa de seleção que permite o usuário selecionar uma cor qualquer.

&nbsp;

## Herança

O **colorComboBox** possui todas as características de uma tag visual. Veja:

* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

&nbsp;

## Características

Além das características herdadas, a tag **colorComboBox** também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **color** | [String de Cor](<StringdecoresnoLuaForm.md>) | "Null" | A cor escolhida pelo usuário.&nbsp; Exemplos: "Red", "White", "#005623"&nbsp; |
| **useAlpha** | Boolean | True | Se true, permite o usuário escolher uma cor com transparência.&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o colorComboBox passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **frameRegion** | String | \<string vazio\> | Considerando que o componente/tag pai possui um frame (ver [Frames](<Frames.md>)), ao definir o valor desta propriedade, a posição e tamanho deste controle é automaticamente calculada para se encaixar na Região do Frame de mesmo nome.&nbsp; Veja [Frames e Regiões](<FrameseRegioes.md>)&nbsp; |
| &nbsp; | &nbsp; | &nbsp; | &nbsp; |


### Métodos

| **Método** | Descrição |
| --- | --- |
| **colorComboBox:dropDown()** | "Abre" o colorComboBox. Exibe a caixa de seleção de cores na interface.&nbsp; |


### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando a seleção do colorComboBox é alterada.&nbsp; |
| **onUserChange** | Este evento é disparado quando o valor do campo do objeto Nodo associado (ver atributo "field") for alterado porque o usuário alterou o conteúdo do colorComboBox.&nbsp; Importante: Este evento é disparado APENAS se o atributo "field" estiver preenchido corretamente e se a alteração de valor ocorrer neste colorComboBox mediante ação do usuário.&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

## Exemplos

### Exemplo 1 - colorComboBox simples

&nbsp;

| &nbsp; |
| --- |


&nbsp;

&nbsp;

&nbsp;

&nbsp; &nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Easy Qt Help documentation editor](<https://www.helpndoc.com>)_
