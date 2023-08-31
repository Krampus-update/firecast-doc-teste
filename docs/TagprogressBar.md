# Tag progressBar

# Tag progressBar

&nbsp;

A tag/componente **progressBar** representa uma barra de progresso/estado, ótimo para dar noção ao usuário do progresso de algo em um formato visual.

&nbsp;

## Herança

O **progressBar** possui **todas** as características das tags visuais.&nbsp;

Veja:

* &nbsp;
  * [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

&nbsp;

## Características

Além das características herdadas, o **progressBar** possui também as seguintes características:

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **color** | Cor | "green" | Define a cor da barra de progresso.&nbsp; Veja [String de cores no Lua Form](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso.&nbsp; |
| **position ** **ou ** **value**&nbsp; | Float | &#48;.0 | Define a posição atual da barra de progresso.&nbsp; |
| **min** | Float | &#48;.0 | Define o valor mínimo da posição da barra de progresso.&nbsp; |
| **max** | Float | &#49;00.0 | Define o valor máximo da posição da barra de progresso.&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o progressBar passa a ler seu "position/value" a partir deste campo.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **fieldMin** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o progressBar passa a ler seu "min" a partir deste campo.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **fieldMax** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o progressBar passa a ler seu "max" a partir deste campo.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **mouseGlow** | Boolean | true | Define se a barra deve brilhar quando o usuário passar o mouse em cima.&nbsp; OBS: Este atributo só tem efeito se o valor do atributo hitTest for "true"&nbsp; |
| **colorMode** | Enumerado: "default" "hl" | "default" | Define como o progressBar desenhará sua cor na interface.&nbsp; "default" - Modo padrão, efeito degradê sobre a cor escolhida.&nbsp; "hl" - Half Lightness/meia iluminosidade. Aplica efeito degradê em cima do tom da cor escolhida com ilumonisade em 50%. As barrinhas de HP/MP/ETC do RRPG utilizam este modo de coloração. Por fixar a iluminosidade em 50%, cores com diferentes brilhos serão apresentadas da mesma forma (Exemplo: azul claro e azul escuro)&nbsp; |


&nbsp;

## Exemplos

### Exemplo 1 - Exemplos de ProgressBars de várias cores

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFTeste"**\>**          **\<progressBar** width="150" color="green" top="25" left="20" value="50" max="100"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

| color="green" | ![Image](<lib/NewItem204.png>) |
| --- | --- |
| color="red" | ![Image](<lib/NewItem205.png>) |
| color="black" | ![Image](<lib/NewItem206.png>) |
| color="darkorchid" | ![Image](<lib/NewItem207.png>) |


&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Converting Word Documents to eBooks: A Step-by-Step Guide with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
