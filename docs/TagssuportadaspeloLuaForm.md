# Tags suportadas pelo Lua Form

## Tags suportadas pelo Lua Form

### Tags de componentes

| **Tag** | Descrição |
| --- | --- |
| **form** | Representa um formulário/uma janela genérica.&nbsp; A **tag raiz** do arquivo LFM **deve ser** “form” ou "popupForm". Pode haver mais de um form no arquivo LFM.&nbsp; Leia mais em: [Tag form.](<Tagform.md>)&nbsp; |
| **popupForm** | Representa um formulário/uma janela cuja finalidade é ser exibida na interface como um popup.&nbsp; Leia mais em: [Tag popupForm](<TagpopupForm.md>).&nbsp; |
| **layout** | Componente visual **invisível**. Excelente para agrupar ou organizar um conjunto de outros componentes visuais.&nbsp; Leia mais em: [Tag layout](<Taglayout.md>)&nbsp; |
| **button** | Um botão. Excelente para executar uma tarefa quando o usuário optar por ela\!&nbsp; Leia mais em: [Tag button](<Tagbutton.md>)&nbsp; |
| **label** | Um componente texto não editável. Usado apenas para mostrar informações.&nbsp; Leia mais em [Tag label](<Taglabel.md>)&nbsp; |
| **image** | Uma imagem.&nbsp; Leia mais em [Tag image](<Tagimage.md>)&nbsp; |
| **edit** | Uma caixa de texto. Componente que permite a edição de texto ou números.&nbsp; Leia mais em [Tag edit](<Tagedit.md>)&nbsp; |
| **textEditor** | Uma caixa de texto que permite várias linhas.&nbsp; Leia mais em [Tag textEditor](<TagtextEditor.md>)&nbsp; |
| **tabControl** | Um componente que permite adicionar abas à interface. Deve ser usado em conjunto com “tab”&nbsp; Leia mais em [Tag tabControl](<TagtabControl.md>)&nbsp; |
| **tab** | Uma aba. Deve ser usado em conjunto com “tabControl”&nbsp; Leia mais em [Tag tab](<Tagtab.md>)&nbsp; |
| **scrollBox** | Controle que adiciona barras de rolagem, permitindo realizar “scroll” nos componentes que estão dentro da caixa. Em dispositivos que possuem touch screen, permite também o gesto de “pinça” para efetuar zoom do conteúdo.&nbsp; Leia mais em [Tag scrollBox](<TagscrollBox.md>)&nbsp; |
| **rectangle** | Controle para desenhar um retângulo de cor personalizada na interface.&nbsp; Leia mais em [tag rectangle.](<Tagrectangle.md>)&nbsp; |
| **richEdit** | Caixa de texto de múltiplas linhas com possibilidade de adicionar formatação, cores, alinhamentos, imagens, etc&nbsp; Leia mais em [tag richEdit](<TagrichEdit.md>)&nbsp; |
| **horzLine** | Uma linha horizontal.&nbsp; Leia mais em [Tag horzLine](<TaghorzLine.md>)&nbsp; |
| **path** | Uma forma geométrica/shape personalizada.&nbsp; Leia mais em&nbsp; [Tag path](<Tagpath.md>).&nbsp; |
| **checkBox** | Uma caixa de marcação.&nbsp; Leia mais em [Tag checkBox](<TagcheckBox.md>)&nbsp; |
| **imageCheckBox** | Uma caixa de marcação onde é possível personalizar a imagem apresentada quando está selecionada e quando não está selecionada.&nbsp; Leia mais em [Tag imageCheckBox](<TagimageCheckBox.md>)&nbsp; |
| **radioButton** | Uma caixa de marcação que, quando usada em grupo, permite apenas uma esteja marcada por vez.&nbsp; Leia mais em [Tag radioButton](<TagradioButton.md>)&nbsp; |
| **comboBox** | Uma caixa de seleção que permite o usuário selecionar um item entre vários.&nbsp; Leia mais em [Tag comboBox](<TagcomboBox.md>)&nbsp; |
| **colorComboBox** | Uma caixa de seleção que permite o usuário escolher uma cor qualquer.&nbsp; Leia mais em [Tag colorComboBox](<TagcolorComboBox.md>)&nbsp; |
| **popup** | Controle que permite exibir popups na interface.&nbsp; Leia mais em [Tag popup](<Tagpopup.md>)&nbsp; |
| **dataLink** | Controle invisível que monitora mudanças de valores nos campos do [NodeDatabase](<NodeDatabase.md>)&nbsp; Leia mais em [Tag dataLink](<TagdataLink.md>)&nbsp; |
| **flowLayout** | Controle que organiza controles na interface de forma dinâmica. Excelente para criar interfaces que se adaptam para diferentes tamanhos de tela.&nbsp; Leia mais em [Tag flowLayout](<TagflowLayout.md>)&nbsp; |
| **flowPart** | Usado em conjunto com “flowLayout”, define uma parte dinâmica do layout dinâmico.&nbsp; Leia mais em [Tag flowPart](<TagflowPart.md>)&nbsp; |
| **flowLineBreak** | Usado em conjunto com “flowLayout”, realiza uma quebra de linha no layout dinâmico.&nbsp; Leia mais em [Tag flowLineBreak](<TagflowLineBreak.md>)&nbsp; |
| **recordList** | Um controle que permite adicionar uma lista de registros à interface.&nbsp; Leia mais em [Tag recordList](<TagrecordList.md>)&nbsp; |
| **dataScopeBox** | Um controle que permite definir em qual objeto Nodo seus controles salvarão e lerão os dados (NodeDatabase).&nbsp; Leia mais em [tag dataScopeBox](<TagdataScopeBox.md>)&nbsp; |
| **timer** | Controle invisível que executa determinado código LUA de tempo em tempo.&nbsp; Leia mais em [Tag timer](<Tagtimer.md>)&nbsp; |
| **activityIndicator** | Controle que exibe uma animação na interface para indicar ao usuário que alguma atividade está sendo feita, como um carregamento ou uma espera.&nbsp; Leia mais em [Tag activityIndicator](<TagactivityIndicator.md>)&nbsp; |
| **progressBar** | Controle que exibe uma barra de progresso/estado na interface.&nbsp; Leia mais em [Tag progressBar](<TagprogressBar.md>)&nbsp; |


&nbsp;

### Tags especiais

| **Tag** | Descrição |
| --- | --- |
| **event** | Tag que associa um código lua a um evento de algum componente/tag.&nbsp; Leia mais em [Tag event](<Tagevent.md>)&nbsp; |
| **style** | Tag que permite a entrada de código de estilo em cascata, muito similar ao CSS em HTML.&nbsp; *Estude um pouco esta tag\! Irá ajudar **muito**\!*&nbsp; Leia mais em [Tag style](<Tagstyle.md>)&nbsp; |
| **template** | Tag avançada que permite a criação de novas tags para serem usadas no arquivo LFM\!&nbsp; *Estude um pouco esta tag\! Irá ajudar **muito**\!*&nbsp; Leia mais em [Tag template](<Tagtemplate.md>)&nbsp; |
| **import** | Importa um arquivo XML.&nbsp; Leia mais em [Tag import](<Tagimport.md>)&nbsp; |
| **group** | Tag simples cujo único propósito é organizar o XML do arquivo Lua Form.&nbsp; Leia mais em [Tag group](<Taggroup.md>)&nbsp; |
| **script** | Define um script/bloco de código em Lua.&nbsp; Leia mais em [Tag script](<Tagscript.md>)&nbsp; |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [News and information about help authoring tools and software](<https://www.helpauthoringsoftware.com>)_
