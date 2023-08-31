# Criar um botão que esconde itens de uma lista dinâmica

# Criar um botão que esconde itens de uma lista dinâmica de alguns usuários.

&nbsp;

Atenção: Este é um tópico avançado e requer o conhecimento de [como criar uma lista dinâmica](<Criarumalistadinamicanaficha.md>).

&nbsp;

Este tipo de funcionalidade é útil quando em uma ficha ou em uma janela acoplável é necessário esconder certos itens de certos usuários, por exemplo:

* &nbsp;
  * NPCs - Talvez o mestre queira esconder determinado NPC dos jogadores
  * Equipamentos - Talvez um jogador de um grupo possua um equipamento que o Mestre deseja que os demais jogadores não saibam de sua existência.
  * Uma anotação secreta, que somente o mestre pode visualizar.

&nbsp;

&nbsp;

## Começando....

&nbsp;

Vamos supor que você já tenha implementado em seu código uma lista dinâmica com a seguinte aparência:

&nbsp;

![Image](<lib/NewItem208.png>)

&nbsp;

e com o seguinte código:

&nbsp;

| **Arquivo Principal “ficha.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**        &nbsp;         **\<layout** align="top" height="30"**\>**                 **\<button** align="left" text="Novo" onClick="self.rclLista:append();"**/\>**         **\</layout\>**       &nbsp;         **\<recordList** name="rclLista" align="client" field="itens"  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; templateForm="frmItem"**/\>** **\</form\>** |


&nbsp;

&nbsp;

| **Arquivo Secundário “item.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmItem" height="30" margins="{top=2,bottom=2}"**\>**            **\<edit** align="client" field="descricao" margins="{right=2}"**/\>**       **\<button** align="right" text="Apagar" width="80"            onClick="ndb.deleteNode(sheet);"**/\>** **\</form\>** |


&nbsp;

## Próximos passos

Para adicionar a funcionalidade de esconder item, você deverá fazer as seguintes alterações em seu arquivo equivalente ao "item.lfm" (aquele que repete para cada item na lista):

* &nbsp;
  * Criar um botão novo ou outra funcionalidade que permita o usuário clicar e realizar uma ação. Neste tutorial usaremos a [tag imageCheckBox](<TagimageCheckBox.md>) pelo simples fato de eu achá-la bacana =).\
&nbsp;

| **\<imageCheckBox** name="cbxInvisivel" align="right" width="25" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; margins="{left=2, right=2}"&nbsp;                checkedImage="images/invisivel.png"                     uncheckedImage="images/visivel.png"                autoChange="false"                onClick="self:alternarVisibilidade();" **/\>** |
| --- |


\
Esta é a imagem "images/invisivel.png": ![Image](<lib/NewItem209.png>)\
Esta é a imagem "images/visivel.png: ![Image](<lib/NewItem210.png>)\
Note que a propriedade autoChange foi setada para false para que a tag não mude automaticamente sua propriedade "checked".

Note também que ao clicar no imageCheckBox, será invocada a função "self:alternarVisibilidade"

&nbsp;

&nbsp;

* &nbsp;
  * Criar o código da função "self:alternarVisibilidade" que utiliza a função [ndb.setPermission](<BibliotecaNDB.md#ndb.setPermission>)

&nbsp;

| \<script\>         **function** self:alternarVisibilidade()                 **if** self.cbxInvisivel.checked **then**                         *-- o imageCheckbox está marcando como invisivel..*                         *-- Vamos mudar as permissões para tornar visivel então..*&nbsp;                                             *-- resetar as permissões de read dos jogadores e espectadores*                         ndb.setPermission(sheet, "group", "jogadores", "read", nil);                         ndb.setPermission(sheet, "group", "espectadores", "read", nil;                 **else**                         *-- o imageCheckbox está marcando como visível*                         *-- Vamos mudar as permissões para tornar invisível então...*                                                 *-- negar as permissões de read dos jogadores e espectadores*                         ndb.setPermission(sheet, "group", "jogadores", "read", "deny");                         ndb.setPermission(sheet, "group", "espectadores", "read", "deny");                 **end**;         **end**; \</script\> |
| --- |


&nbsp;

&nbsp;

* &nbsp;
  * Criar um código que fica responsável por atualizar o estado do imageCheckBox conforme as permissões existentes e alteradas:\
\
&nbsp;

| \<script\>         **function** self:atualizarCbxInvisivel()                 *-- Esta função é chamada em vários pontos para atualizar o estado do checkbox de invisibilidade*&nbsp;                               *-- Marcar o checkbox se existir uma permissão "read deny" para jogadores ou para espectadores*                 self.cbxInvisivel.checked = ndb.getPermission(sheet, "group", "espectadores", "read") == "deny" **or**                                             ndb.getPermission(sheet, "group", "jogadores", "read") == "deny";                                                                                        *-- Permitir o click no checkbox apenas se o usuário atual possuir a permissão "writePermissions"*                 self.cbxInvisivel.enabled = ndb.testPermission(sheet, "writePermissions");         **end**; \</script\> |
| --- |


\
Veja também:

* &nbsp;
  * &nbsp;
    * &nbsp;
      * Função [ndb.getPermission](<BibliotecaNDB.md#ndb.getPermission>)
      * Função [ndb.testPermission](<BibliotecaNDB.md#ndb.setPermission>)

&nbsp;

&nbsp;

* &nbsp;
  * Criar um [NodeObserver](<ObjetoNodeObserver.md>) que será responsável por invocar a função acima "self:atualizarCbxInvisivel" quando ocorrer alguma mudança nas permissões do NodeDatabase. O NodeObserver será criado no evento [onScopeNodeChanged](<Tagform.md#onScopeNodeChanged>) da [tag Form](<Tagform.md>)

&nbsp;

&nbsp;

| \<event name="onScopeNodeChanged"\>         **if** self.observer ~= nil **then**                 *-- Já tinhamos criado um observer, vamos desativá-lo.*                                self.observer.enabled = false;                 self.observer = nil;         **end**;                **if** sheet ~= nil **then**                 *-- O form foi ligado a um NodeDatabase\!*                 *-- Vamos criar um NodeObserver para este nodo.*                                self.observer = ndb.newObserver(sheet);                                self.observer.onPermissionListChanged =                         **function**(node)                                 *-- Esta função será chamada quando*                                 *-- as definições de permissões de sheet mudarem*                                                                 self:atualizarCbxInvisivel();                         **end**;                                        self.observer.onFinalPermissionsCouldBeChanged =                         **function**(node)                                 *-- Esta função será chamada quando*                                 *-- minhas permissões em sheet puderem*                                 *-- ter sido afetadas por alterações de permissões*                                 *-- no NodeDatabase ou porque me tornei * &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; *-- mestre/jogador/espectador*                                                                 self:atualizarCbxInvisivel();                         **end**;                                       *-- Devemos atualizar o checkbox agora também  *                 self:atualizarCbxInvisivel();           **end**; \</event\> |
| --- |


&nbsp;

&nbsp;

&nbsp;

## Resultado final

O que aparece para os Mestres da mesa:

![Image](<lib/NewItem211.png>)

&nbsp;

&nbsp;

O que os Jogadores e Espectadores da mesa veem:

![Image](<lib/NewItem212.png>)

&nbsp;

&nbsp;

&nbsp;

## Código fonte final (sem os comentários)

| **Arquivo Principal “ficha.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**        &nbsp;         **\<layout** align="top" height="30"**\>**                 **\<button** align="left" text="Novo" onClick="self.rclLista:append();"**/\>**         **\</layout\>**       &nbsp;         **\<recordList** name="rclLista" align="client" field="itens"  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; templateForm="frmItem"**/\>** **\</form\>** |


&nbsp;

&nbsp;

| **Arquivo Secundário “item.lfm”** |
| --- |
| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmItem" height="30" margins="{top=2,bottom=2}"**\>**            **\<script\>**          function self:alternarVisibilidade()          &nbsp; &nbsp; if self.cbxInvisivel.checked then               &nbsp; &nbsp; ndb.setPermission(sheet, "group", "jogadores", "read", nil);                   ndb.setPermission(sheet, "group", "espectadores", "read", nil);              else                   ndb.setPermission(sheet, "group", "jogadores", "read", "deny");                   ndb.setPermission(sheet, "group", "espectadores", "read", "deny");              end;        &nbsp; end;           function self:atualizarCbxInvisivel()                    &nbsp; &nbsp; self.cbxInvisivel.checked = ndb.getPermission(sheet, "group", "espectadores", "read") == "deny" or                                          ndb.getPermission(sheet, "group", "jogadores", "read") == "deny"                                                                                                   self.cbxInvisivel.enabled = ndb.testPermission(sheet, "writePermissions");          end;     **\</script\>**      **\<edit** align="client" field="descricao" margins="{right=2}"**/\>**            **\<imageCheckBox** name="cbxInvisivel" align="right" width="25" margins="{left=2, right=2}"                    checkedImage="images/invisivel.png"                     uncheckedImage="images/visivel.png"                    autoChange="false"                    onClick="self:alternarVisibilidade();" **/\>**            **\<button** align="right" text="Apagar" width="80" onClick="ndb.deleteNode(sheet);"**/\>**                            **\<event** name="onScopeNodeChanged"**\>**             if self.observer ~= nil then                        self.observer.enabled = false;                     self.observer = nil;             end;&nbsp;                           if sheet ~= nil then                        self.observer = ndb.newObserver(sheet);                     self.observer.onPermissionListChanged =            &nbsp;                function(node)                                                      self:atualizarCbxInvisivel();                             end;                                                    self.observer.onFinalPermissionsCouldBeChanged =                             function(node)                                     self:atualizarCbxInvisivel();                             end;                                                    self:atualizarCbxInvisivel();               end;     **\</event\>** **\</form\>** |



***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Productivity with HelpNDoc's Efficient User Interface](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
