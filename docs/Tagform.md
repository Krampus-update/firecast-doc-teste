# Tag form

# Tag form

A tag/componente **form** representa uma ficha, um formulário ou uma janela do plug-in.&nbsp;

As principais características do **form** são:

* Para que alguma interface visual seja apresentada na tela do usuário, é necessário existir ao menos 1 **form**. Sem **form**, não há apresentação da interface.&nbsp;
* Apenas os componentes que estão dentro de um **form** são apresentados na tela.
* É possível existir um **form** dentro de outro **form.**
* É possível definir um tema para um **form** e todos os componentes que estão dentro dele. Exemplo: Você quer que o form (e demais componentes) tenha aparência escura ou clara?
* É possível associar um Nodo de um NodeDatabase (Ver [NodeDatabase](<NodeDatabase.md>)) a um **form.** Quando você faz isso, todos os componentes de edição (que estão dentro do form) passam a salvar os dados neste nodo.
  * Os modelos de ficha fazem isso\! Mas você não precisa se preocupar com isso, pois o SDK 3 faz isso automaticamente para você ;) .

## Herança

O **form** possui **todas** as características de um controle qualquer. Veja [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

## Características

Além das características herdadas, o **form** possui também as seguintes características:

### Propriedades e atributos da tag FORM

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **title** | String | \<string vazio\> | Define o título do formulário.&nbsp; Este título pode ser apresentado em vários lugares, como identificação da ficha (se for um modelo de ficha) ou como título de janela.&nbsp; |
| **description** | String | \<string vazio\> | Define um texto descritivo do formulário.&nbsp; Se for um modelo de ficha, este valor pode ser apresentado ao usuário durante a criação do personagem.&nbsp; |
| **dataType** | String | \<string vazio\> | Define um tipo de dados que este formulário é capaz de editar.&nbsp; Se você está criando uma ficha nova, você deve inventar este texto. A partir de então, este será o identificador da sua ficha\!&nbsp; Este campo deve ser preenchido se você estiver criando uma janela acoplável de mesa que salve dados em um [NodeDatabase](<NodeDatabase.md>) armazenado no servidor RRPG. Neste caso, o dataType serve para identificar qual NodeDatabase da mesa deverá ser aberto para salvamento de dados.&nbsp; O valor deve possuir ao menos 5 caracteres alfanuméricos, "\_" ou "." e não deve começar com um dígito.&nbsp; Exemplos: “RRPG.MeuNome.DnD5” “br.com.Meusite.VampiroAMascara” "br.com.MeuSite.MeuTablesDock"&nbsp; |
| **formType** | Enumerado: “undefined” “sheetTemplate” "tablesDock" | “undefined” | Define a finalidade deste formulário.&nbsp; “sheetTemplate” – Este formulário é um modelo de ficha.&nbsp; "tablesDock" - Este formulário é uma janela acoplável de mesa. **Importante**: Se você quiser que sua janela acoplável de mesa salve dados em um [NodeDatabase](<NodeDatabase.md>) armazenado no servidor RRPG, preencha também a propriedade "dataType". Janelas acopláveis são visíveis apenas para assinantes Gold e/ou em mesas onde seu criador for Gold Plus.&nbsp; “undefined” – Este formulário não tem uma finalidade bem definida e pode ser usado para várias finalidades diferentes. O RRPG não fará nenhum tratamento especial.&nbsp; |
| **theme** | Enumerado: “default” “light” “dark” | “default” | Define o tema de cores que os componentes visuais terão neste formulário.&nbsp; “default”: Tema padrão (cores escuras). “light”: Tema de cores claras. “dark”: Tema de cores escuras.&nbsp; Observação: Mesmo que outros temas sejam adicionados futuramente, "default" sempre usará cores escuras.&nbsp; |
| **lockWhileNodeIsLoading** | Boolean | true | Quando true, o form apresenta o texto “carregando” e trava a interface enquanto o [NodeDatabase](<NodeDatabase.md>) associado estiver baixando dados.&nbsp; |
| **minWidth** | Float | \<o mesmo que width\>&nbsp; | Quando dentro de uma [tag flowLayout](<TagflowLayout.md>) ou quando for um item de uma [tag recordList](<TagrecordList.md>) layout "horizontalTiles" ou "verticalTiles", define a largura mínima que este form pode assumir, o tornando adaptável ao "tamanho da tela".&nbsp; Quando não definido, o valor "width" será usado e, portanto, o form não mudará sua largura de forma dinâmica.&nbsp; |
| **maxWidth** | Float | \<o mesmo que width\>&nbsp; | Quando dentro de uma [tag flowLayout](<TagflowLayout.md>) ou quando for um item de uma [tag recordList](<TagrecordList.md>) layout "horizontalTiles" ou "verticalTiles", define a largura máxima que este form pode assumir, o tornando adaptável ao "tamanho da tela".&nbsp; Quando não definido, o valor "width" será usado e, portanto, o form não mudará sua largura de forma dinâmica.&nbsp; |
| **isShowing** | Boolean | False | (Somente Leitura) Esta propriedade contém True se o form está sendo exibido na interface do usuário ou false se o form não está visível.&nbsp; |


&nbsp;

### Métodos da tag FORM

| **Método** | Descrição |
| --- | --- |
| **form:setNodeObject(nodeObject)** | Define em qual [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase os controles de edição deste formulário devem salvar os dados.&nbsp; Parâmetros: nodeObject – Um objeto Nodo (de um NodeDatabase) ou **nil**.&nbsp; Ver:&nbsp; [NodeDatabase](<NodeDatabase.md>) [Escopo de Dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>)&nbsp; |
| **form:getNodeObject();** | Retorna o [objeto nodo](<ObjetoNodo.md>) (de um NodeDatabase) no qual os controles de edição deste formulário devem salvar os dados.&nbsp; **nil** é retornado quando não há nodo associado.&nbsp; Ver:&nbsp; [NodeDatabase](<NodeDatabase.md>) [Escopo de Dados](<LuaFormeNodeDatabase.md#Escopo%20de%20dados>)&nbsp; |
| **form:lockWithActivity(\[msg\])** | Desabilita a interação do usuário com o formulário exibindo um indicador de atividade e, opcionalmente, uma mensagem.&nbsp; Ideal quando você quer fazer o usuário aguardar a conclusão de algum processo qualquer antes de voltar a interagir com a interface.&nbsp; Parâmetros: (OPCIONAL) msg - uma cadeia de caracteres contendo a mensagem que será exibida na interface.&nbsp; Observações: Este método segue uma ideia de pilha: Você pode invocar este método mais de uma vez. Para cada chamada a este método, deve haver uma chamada do método [unlockWithActivity](<Tagform.md#método%20unlockWithActivity>) para destravar a interface. A mensagem exibida será sempre a da última chamada ao método.&nbsp; |
| **form:unlockWithActivity()** | Volta a habilitar a interação entre o usuário e a interface que foi previamente travada pelo método form:lockWithActivity&nbsp; Retorna true se o form foi realmente liberado, ou false se precisar de mais chamadas de unlockWithActivity para isso.&nbsp; |


### Eventos da tag Form

| **Nome do evento** | Descrição |
| --- | --- |
| **onNodeReady**&nbsp; | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase associado a este formulário está pronto para ser usado.&nbsp; Quando este evento é chamado, você pode assumir: a variável "sheet" do LuaForm está diferente de nil e possui uma referência válida para um [objeto nodo](<ObjetoNodo.md>). O processo de carregamento do nodeDatabase associado já chegou ao fim. Você já consegue acessar os dados armazenados nele normalmente.&nbsp; |
| **onNodeUnready**&nbsp; | Este evento é invocado quando o [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase associado a este formulário **deixa de estar** pronto para ser usado.&nbsp; Quando este evento é chamado, você pode assumir: a variável "sheet" do LuaForm não contém mais uma referência válida para um objeto nodo.&nbsp; |
| **onNodeChanged** **ou** **onScopeNodeChanged**&nbsp; | Este evento é invocado um [objeto nodo](<ObjetoNodo.md>) de um NodeDatabase é associado ou desassociado a este formulário.&nbsp; Ver [NodeDatabase](<NodeDatabase.md>)&nbsp; |
| **onShow** | Este evento é invocado quando o formulário for ficar visível na interface.&nbsp; |
| **onHide** | Este evento é invocado quando o formulário for ser escondido/fechado.&nbsp; |


&nbsp;

Veja também [Tratando eventos do Lua Form.](<TratandoeventosdoLuaForm.md>)

***
_Created with the Personal Edition of HelpNDoc: [Make your documentation accessible on any device with HelpNDoc](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
