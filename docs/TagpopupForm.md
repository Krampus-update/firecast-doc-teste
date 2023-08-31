# Tag popupForm

# Tag popupForm

A tag/componente **popupForm** é uma especialização da [tag form](<Tagform.md>) que contém propriedades próprias para exibir uma janela popup na interface do usuário .

Você pode usar esta tag como tag raiz de um arquivo LFM.

## Herança

O **popupForm** possui **todas** as características da Tag form.&nbsp;

&nbsp;

Veja:

* &nbsp;
  * [Tag form](<Tagform.md>)
  * [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

## Características

Além das características herdadas, o **popupForm** possui também as seguintes características:

### Propriedades e atributos da tag popupForm

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **drawContainer** | Boolean | true | Define se o popupForm deve desenhar uma borda que delimita seu conteúdo. &nbsp; |
| **cancelable** | Boolean | true | Define se o popupForm pode ser cancelado pelo usuário.&nbsp; Quando true, o popupForm fecha automaticamente quando o usuário fizer uma ação de cancelamento de popup (tecla ESC, clique no botão X da janela em desktop, tecla voltar em celulares/tablets, click fora do Popup em dispositivos móveis, etc..).&nbsp; Quando false, o popupForm não fecha automaticamente quando o usuário fizer uma ação padrão de cancelamento do popup. Assim, a única maneira de fechar o popupForm é invocar o método "close" ou "[gui.closePopup](<BibliotecaGUI.md#função%20closePopup>)" via programação.&nbsp; O evento "onCancelRequest" é disparado apenas quando "cancelable" for false.&nbsp; |
| **placement** | String enumerado: "center" "bottom" "top" "left" "right" "topLeft" "topRight" "bottomLeft" "bottomRight" "mouse" "mouseCenter" | "center" | Define onde o popupForm deve ser exibido.&nbsp; "center" - no centro da tela&nbsp; "bottom" - na parte de baixo da tela "top" - na parte de cima da tela "left" - à esquerda na tela "right" - à direita na tela "topLeft" -&nbsp; no canto superior esquerdo da tela "topRight - no canto superior direito da tela "bottomLeft" - no canto inferior esquerdo da tela "bottomRight" - no canto inferior direito da tela "mouse" - onde o mouse está atualmente "mouseCenter" - centralizado onde o mouse está atualmente.&nbsp; |
| **resizable** | Boolean | false | Define se o usuário pode redimensionar o popup form manualmente.&nbsp; Funciona somente se a propriedade "drawContainer" for true.&nbsp; Observações: Por enquanto, esta propriedade não possui efeito no Firecast Mobile.&nbsp; |


&nbsp;

&nbsp;

### Métodos da tag popupForm

| **Método** | Descrição |
| --- | --- |
| **popupForm:show();** | Exibe o popup na interface do usuário&nbsp; Retorna true se o popupForm não estava visível e passou a ficar visível na interface.&nbsp; |
| **popupForm:close();** | Fecha o popup da interface do usuário.&nbsp; Retorna true o popupForm estava visível na interface e passou a não ficar visível.&nbsp; |


&nbsp;

### Eventos da tag popupForm

| **Nome do evento** | Descrição |
| --- | --- |
| **onCancelRequest** | Se o atributo "cancelable" for false, este evento é invocado quando o usuário fizer uma ação sinalizando que deseja fechar o popup.&nbsp; Você pode realizar ações "bacanas" aqui, como, por exemplo:&nbsp; Invocar o método "close" apenas se o usuário não tiver preenchido nenhum campo da interface Perguntar ao usuário se ele realmente deseja cancelar (usando [dialogs.confirmYesNo](<BibliotecaDialogs.md#função%20confirmYesNo>)) e só depois então fechar o popup invocando o método "close".&nbsp; |


&nbsp;

Veja também [Tratando eventos do Lua Form.](<TratandoeventosdoLuaForm.md>)

***
_Created with the Personal Edition of HelpNDoc: [Effortlessly upgrade your WinHelp HLP help files to CHM with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
