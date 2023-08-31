# Tag richEdit

# Tag richEdit

A tag/componente **richEdit** representa uma caixa de texto de múltiplas linhas com possibilidade de adicionar formatação, cores, alinhamentos, imagens, etc... Um ótimo controle para permitir a entrada de dados "texto ricos".

&nbsp;

## Herança

O **richEdit** possui todas as características de uma tag visual. Veja:

* [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, a tag **richEdit** também possui as seguintes características:

&nbsp;

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **animateImages** | Boolean | false | Define se o RichEdit deve executar a animação de imagens que são animadas (exemplo: GIF, GIFV) quando suportadas.&nbsp; |
| **readOnly ** | Boolean | false | Quando true, o richEdit não permite o usuário alterar seu conteúdo&nbsp; |
| **field** | String | \<string vazio\> | Caminho de um campo no NodeDatabase.&nbsp; Quando associado, o richEdit passa a apresentar e salvar o conteúdo no campo informado.&nbsp; Veja também: [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>) [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **backgroundColor** | String de Cor | "White" | Define a cor de fundo do RichEdit.&nbsp; Exemplos: Black White #FDFDFD&nbsp; Veja [String de cores no Lua Form](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso.&nbsp; |
| **defaultFontColor** | String de Cor | "Black" | Define a cor padrão para os textos do richEdit&nbsp; Exemplos: Black White #FDFDFD&nbsp; Veja [String de cores no Lua Form](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso&nbsp; |
| **defaultFontSize** | Float | &#49;5&nbsp; | Define o tamanho de fonte padrão para os textos do richEdit&nbsp; |
| **showToolbar** | Boolean | true | Define se o richEdit deve apresentar uma baixa de ferramentas para auxiliar o usuário a formatar seu texto.&nbsp; |
| **hideSelection** | Boolean | true | Define se a seleção que o usuário fizer (com o mouse ou teclado) será apresentada quando ele estiver focado em outro controle.&nbsp; True - A seleção continuará existindo, porém não será exibida visualmente se o usuário estiver focado em outro controle&nbsp; False - A seleção continuará existindo e será exibida visualmente mesmo se o usuário estiver focado em outro controle.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos:

### Exemplo 1 - Um richEdit simples

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form ......\>**     **\<richEdit** align="client" backgroundColor="black" defaultFontColor="white" field="txt"**/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

&nbsp;

![Image](<lib/NewItem227.png>)

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [From Word to ePub or Kindle eBook: A Comprehensive Guide](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
