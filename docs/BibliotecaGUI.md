# Biblioteca GUI

# Biblioteca GUI

A biblioteca gui provê funções relacionadas às interfaces Lua Form.

Todas as funções estão contidas na table/variável "GUI" da unidade "gui.lua".

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "gui.lua"* require("gui.lua");    *-- Agora é possível acessar as funções da biblioteca* GUI.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca gui
## &nbsp;

| **function** GUI.findControlByName(controlName, referenceControl) |
| --- |


&nbsp;

Procura outro controle através do nome passado pelo parâmetro “controlName” em toda a hierarquia de controles onde "referenceControl" está.

&nbsp;

Parâmetros:

* &nbsp;
  * controlName - uma cadeia de caracteres contendo o nome do controle que deseja procurar.
  * referenceControl - um controle para servir de referência durante a busca. O controle será procurado em toda a hierarquia de controles de "referenceControl", isto é, primeiro nos controles que estão dentro dele e depois nos controles pais de "referenceControl".

&nbsp;&nbsp; &nbsp;

Retorno:&nbsp;

* &nbsp;
  * o controle, se encontrado
  * **nil** caso não encontre.

&nbsp;

&nbsp;

| **function** GUI.newActivityIndicator() |
| --- |


&nbsp;

Cria e retorna um novo [objeto activityIndicator](<TagactivityIndicator.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto activityIndicator](<TagactivityIndicator.md>)

&nbsp;

| **function** GUI.newButton() |
| --- |


&nbsp;

Cria e retorna um novo [objeto button.](<Tagbutton.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto button.](<Tagbutton.md>)

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.newCheckBox() |
| --- |


&nbsp;

Cria e retorna um novo [objeto checkbox.](<TagcheckBox.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto checkbox.](<TagcheckBox.md>)

&nbsp;

&nbsp;

| **function** GUI.newComboBox() |
| --- |


&nbsp;

Cria e retorna um novo [objeto comboBox](<TagcomboBox.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto comboBox](<TagcomboBox.md>)

&nbsp;

| **function** GUI.newColorComboBox() |
| --- |


&nbsp;

Cria e retorna um novo [objeto colorComboBox](<TagcolorComboBox.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto colorComboBox](<TagcolorComboBox.md>)

&nbsp;

&nbsp;

| **function** GUI.newDataLink() |
| --- |


&nbsp;

Cria e retorna um novo [objeto dataLink](<TagdataLink.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto dataLink](<TagdataLink.md>)

&nbsp;

&nbsp;

| **function** GUI.newDataScopeBox() |
| --- |


&nbsp;

Cria e retorna um novo [objeto dataScopeBox](<TagdataScopeBox.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto dataScopeBox](<TagdataScopeBox.md>)

&nbsp;

&nbsp;

| **function** GUI.newEdit() |
| --- |


&nbsp;

Cria e retorna um novo [objeto edit](<Tagedit.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto edit](<Tagedit.md>)

&nbsp;

&nbsp;

| **function** GUI.newFlowLayout() |
| --- |


&nbsp;

Cria e retorna um novo [objeto flowLayout.](<TagflowLayout.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto flowLayout.](<TagflowLayout.md>)

&nbsp;

&nbsp;

| **function** GUI.newFlowLineBreak() |
| --- |


&nbsp;

Cria e retorna um novo [objeto flowLineBreak.](<TagflowLineBreak.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto flowLineBreak.](<TagflowLineBreak.md>)

&nbsp;

&nbsp;

| **function** GUI.newFlowPart() |
| --- |


&nbsp;

Cria e retorna um novo [objeto flowPart.](<TagflowPart.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto flowPart.](<TagflowPart.md>)

&nbsp;

&nbsp;

| **function** GUI.newForm(\[formName\]) |
| --- |


&nbsp;

Cria e retorna um novo [objeto form](<Tagform.md>).

&nbsp;

Parâmetros:

* &nbsp;
  * (OPCIONAL) formName - Se informado, contém uma cadeia de caracteres identificando o "name" de um dos Lua Forms do plug-in, fazendo com que a função busque em todos os arquivos ".lfm" a tag form ou tag popupForm que possuir o atributo name igual a este valor.

&nbsp;&nbsp; &nbsp;

Retorno:&nbsp;

* &nbsp;
  * Se "formName" **não** for informado: Retorna um novo [objeto form](<Tagform.md>) que não possui nenhum outro componente/tag dentro dele.
  * Se "formName" for informado:
    * Se a busca encontrar o LuaForm, retorna um objeto form representando a nova instância do Lua Form.
    * Se a busca não encontrar o LuaForm, retorna **nil**.

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.newHorzLine() |
| --- |


&nbsp;

Cria e retorna um novo [objeto horzLine](<TaghorzLine.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto horzLine](<TaghorzLine.md>)

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.newImage() |
| --- |


&nbsp;

Cria e retorna um novo [objeto image](<Tagimage.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto image.](<Tagimage.md>)

&nbsp;

&nbsp;

| **function** GUI.newImageCheckBox() |
| --- |


&nbsp;

Cria e retorna um novo [objeto imageCheckbox.](<TagimageCheckBox.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto imageCheckbox.](<TagimageCheckBox.md>)

&nbsp;

&nbsp;

| **function** GUI.newLabel() |
| --- |


&nbsp;

Cria e retorna um novo [objeto label.](<Taglabel.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto label.](<Taglabel.md>)

&nbsp;

&nbsp;

| **function** GUI.newLayout() |
| --- |


&nbsp;

Cria e retorna um novo [objeto layout](<Taglayout.md>).

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto layout](<Taglayout.md>).

&nbsp;

&nbsp;

| **function** GUI.newPath() |
| --- |


&nbsp;

Cria e retorna um novo [objeto path](<Tagpath.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto path](<Tagpath.md>)

&nbsp;

&nbsp;

| **function** GUI.newPopup() |
| --- |


&nbsp;

Cria e retorna um novo [objeto popup](<Tagpopup.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto popup](<Tagpopup.md>)

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.newPopupForm(\[popupFormName\]) |
| --- |


&nbsp;

Cria e retorna um novo [objeto popupForm](<TagpopupForm.md>).

&nbsp;

Parâmetros:

* &nbsp;
  * (OPCIONAL) popupFormName - Se informado, contém uma cadeia de caracteres identificando o "name" de um dos Lua Forms do plug-in, fazendo com que a função busque em todos os arquivos ".lfm" a tag popupForm que possuir o atributo name igual a este valor.

&nbsp;&nbsp; &nbsp;

Retorno:&nbsp;

* &nbsp;
  * Se "popupFormName" **não** for informado: Retorna um novo [objeto popupForm](<TagpopupForm.md>) que não possui nenhum outro componente/tag dentro dele.
  * Se "popupFormName" for informado:
    * Se a busca encontrar o LuaForm e se for do tipo [popupForm](<TagpopupForm.md>), retorna um [objeto popupForm](<TagpopupForm.md>) representando a nova instância do Lua Form.
    * Se a busca não encontrar o LuaForm ou se encontrar mas tipo diferente de popupForm, retorna **nil**.

&nbsp;

&nbsp;

| **function** GUI.newRadioButton() |
| --- |


&nbsp;

Cria e retorna um novo objeto [radioButton](<TagradioButton.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um objeto [radioButton](<TagradioButton.md>)

&nbsp;

&nbsp;

| **function** GUI.newRecordList() |
| --- |


&nbsp;

Cria e retorna um novo [objeto recordList](<TagrecordList.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto recordList](<TagrecordList.md>)

&nbsp;

&nbsp;

| **function** GUI.newRectangle() |
| --- |


&nbsp;

Cria e retorna um novo [objeto rectangle](<Tagrectangle.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto rectangle](<Tagrectangle.md>)

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.newScrollBox() |
| --- |


&nbsp;

Cria e retorna um novo [objeto scrollBox](<TagscrollBox.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto scrollBox](<TagscrollBox.md>)

&nbsp;

| **function** GUI.newTab() |
| --- |


&nbsp;

Cria e retorna um novo [objeto tab](<Tagtab.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto tab](<Tagtab.md>)

&nbsp;

&nbsp;

| **function** GUI.newTabControl() |
| --- |


&nbsp;

Cria e retorna um novo [objeto tabControl](<TagtabControl.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto tabControl](<TagtabControl.md>)

&nbsp;

&nbsp;

| **function** GUI.newTextEditor() |
| --- |


&nbsp;

Cria e retorna um novo [objeto textEditor](<TagtextEditor.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto textEditor](<TagtextEditor.md>)

&nbsp;

&nbsp;

| **function** GUI.newTimer() |
| --- |


&nbsp;

Cria e retorna um novo [objeto timer](<Tagtimer.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto timer](<Tagtimer.md>)

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.newProgressBar() |
| --- |


&nbsp;

Cria e retorna um novo [objeto progressBar](<TagprogressBar.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto progressBar](<TagprogressBar.md>)

&nbsp;

&nbsp;

| **function** GUI.newInertialMovement() |
| --- |


&nbsp;

Cria e retorna um novo [objeto InertialMovement](<ObjetoInertialMovement.md>)

&nbsp;

Parâmetros:

&nbsp; &nbsp; Não há parâmetros

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Retorna um [objeto InertialMovement](<ObjetoInertialMovement.md>)

&nbsp;

&nbsp;

| **function** GUI.showPopup(form \[, options\]) |
| --- |


&nbsp;

Exibe uma janela na interface do usuário na forma de um Popup

&nbsp;

Parâmetros:

* &nbsp;
  * form - O formulário a ser exibido na interface. Pode ser um [objeto Lua Form já instanciado](<Tagform.md>) ou um string contendo o nome do form a ser exibido.
    * Caso seja passado o nome do formulário em uma cadeia de caracteres, a função percorre todos os "lfm" do plug-in à procura da tag form que possuir name igual ao informado. Se encontrado, uma nova instância é criada para a exibição.
  * (OPCIONAL) options - Uma tabela/objeto LUA contendo as opções da exibição do popup. As opções são:
    * onClose - \[function, padrão = nil\] - Uma função lua que será invocada quando o popup for fechado.
    * placement - \[string enumerado\] - Onde o popup será exibido.. Os possíveis valores são:
- &nbsp;
  - &nbsp;
    - &nbsp;
      - "center" - no centro da tela
      - "bottom" - na parte de baixo da tela
      - "top" - na parte de cima da tela
      - "left" - à esquerda na tela
      - "right" - à direita na tela
      - "topLeft" -&nbsp; no canto superior esquerdo da tela
      - "topRight - no canto superior direito da tela
      - "bottomLeft" - no canto inferior esquerdo da tela
      - "bottomRight" - no canto inferior direito da tela
      - "mouse" - onde o mouse está atualmente
      - "mouseCenter" - centralizado onde o mouse está atualmente.

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Se conseguir exibir o form como um popup na interface, retorna **true**; Senão retorna **false**.

&nbsp;

Observações:

* &nbsp;
  * A função não espera o popup fechar para retornar. Após esta chamada, o código LUA continuará sua execução normal enquanto o form é mostrado.
  * Se o parâmetro *form* for uma [tag popupForm](<TagpopupForm.md>), os seguintes parâmetros em *options* são ignorados (e são usados os atributos correspondentes da tag no lugar):
    * *options*.placement

&nbsp;

&nbsp;

| **function** GUI.closePopup(form) |
| --- |


&nbsp;

Fecha uma janela popup que foi previamente aberta pela da função [gui.showPopup](<BibliotecaGUI.md#função%20showPopup>).

&nbsp;

Parâmetros:

* &nbsp;
  * form - O formulário a ser fechado/tirado da interface. Pode ser um [objeto Lua Form já instanciado](<Tagform.md>) ou um string contendo o nome do form que foi exibido.
    * Caso seja passado o nome do formulário em uma cadeia de caracteres, a função percorre todos os popups abertos e fecha àqueles que possuírem o nome informado.

&nbsp;&nbsp; &nbsp;

Retorno: \
&nbsp; &nbsp; Se conseguir fechar o form, retorna **true**; Senão retorna **false**.

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.openInBrowser(url) |
| --- |


&nbsp;

Abre um determinado URL/página web no browser do usuário.

&nbsp;

Parâmetros:

* &nbsp;
  * url - cadeia de caracteres contendo a URL/caminho da página web que deve ser aberta. Exemplo "http://www.rrpg.com.br".

&nbsp;

Observações:

* &nbsp;
  * Se o parâmetro "url" não começar com "http://" e nem com "https://", automaticamente "http://" será adicionado no inicio da URL antes da abertura da página.

&nbsp;

&nbsp;

&nbsp;

| **function** GUI.toast(message) |
| --- |


&nbsp;

Show a quick informative message to the user that does not require user interaction and hides automatically after a short time

&nbsp;

Parameters

* &nbsp;
  * message - The message string to be shown


***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Create Professional Documentation with HelpNDoc's Clean UI](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
