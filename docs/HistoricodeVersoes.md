# Histórico de Versões

# Firecast SDK 3 Version History

## SDK 3.6d (04/05/2023)

* &nbsp;
  * New library: [Async.Promise](<AsyncPromiselibrary.md>)
  * New library: [Log](<Loglibrary.md>)
  * New object: [Promise](<Promiseobject.md>)
  * New function in the Firecast library: [Firecast.asyncOpenUserNDB](<BibliotecaFirecast.md#asyncOpenUserNDB>)
  * New function in the Room object: [room:asyncOpenUserRoomNDB](<ObjetoMesa.md#asyncOpenUserRoomNDB>)
  * New function in VHD library: [VHD.copyFile](<BibliotecaVHD.md#copyFile>)
  * New macro functions:
    * [Log functions](<BibliotecaparaMacrosemLua.md#Log\_functions>)
    * [getUserNDB](<BibliotecaparaMacrosemLua.md#getUserNDB>)
    * [getUserRoomNDB](<BibliotecaparaMacrosemLua.md#getUserRoomNDB>)
    * [getRoomNDB](<BibliotecaparaMacrosemLua.md#getRoomNDB>)

## SDK 3.6c (17/06/2022)

* &nbsp;
  * New functions to [System](<BibliotecaSystem.md>) library:
    * [System.readClipboardAsDragNDrop](<BibliotecaSystem.md#System\_readClipboardAsDragNDrop>)
  * New functions to the [Scene Object](<ObjetoScene.md>):
    * [scene:sendDelayedUpdates](<ObjetoScene.md#scene\_sendDelayedUpdates>)
  * New functions to the [GUI](<BibliotecaGUI.md>) library:
    * [GUI.toast](<BibliotecaGUI.md#gui\_toast>)
  * New macro functions:
    * [toast](<BibliotecaparaMacrosemLua.md#toast>)
  * New Drag-and-Drop DataTypes:
    * [imageFile](<ArrastandoeSoltandoInformacoesDr.md#imageFile>)
    * [ImageFiles](<ArrastandoeSoltandoInformacoesDr.md#imageFiles>)

## SDK 3.6b (25/05/2022)

* &nbsp;
  * Fix: getChildren function was not working with [recordList Tag](<TagrecordList.md>).
  * New functions to [System](<BibliotecaSystem.md>) library:
    * [System.checkAPIVersion](<BibliotecaSystem.md#System\_checkAPIVersion>)
    * [System.getAPIVersion](<BibliotecaSystem.md#System\_getAPIVersion>)
    * [System.makeAPIVersionNumber](<BibliotecaSystem.md#System\_makeAPIVersion>)

&nbsp;

## SDK 3.6 (05/05/2022)

* &nbsp;
  * O[ arquivo module.xml](<Oarquivomodulexml.md>) agora permite o criador de plugin definir as informações de seu plugin em várias línguas.
  * Novas funções na biblioteca Firecast.Messaging:
    * [Firecast.Messaging.newReceiver](<BibliotecaFirecastMessaging.md#functionNewReceiver>)
  * Fix [Personagem.dataType](<ObjetoPersonagem.md#Personagem\_dataType>) always returning nil
  * Firecast 8.4 compatibility

&nbsp;

## SDK 3.5 (29/10/2018)

* &nbsp;
  * Novas propriedades para a [Tag label](<Taglabel.md>):
    * [format](<Taglabel.md#format>) e [formatFloat](<Taglabel.md#formatFloat>)
  * Novas propriedades para a [Tag image](<Tagimage.md>):
    * [animate](<Tagimage.md#animate>)
    * [naturalAnimated](<Tagimage.md#naturalAnimated>)
  * Novas propriedades para a [Tag dataScopeBox](<TagdataScopeBox.md>):
    * novos eventos [onNodeChanged](<TagdataScopeBox.md#onScopeNodeChanged>), [onNodeReady](<TagdataScopeBox.md#evento%20onNodeReady>) e [onNodeUnready](<TagdataScopeBox.md#onNodeUnready>)
  * Novas propriedades para a [Tag popup](<Tagpopup.md>):
    * novos eventos [onNodeChanged](<Tagpopup.md#onScopeNodeChanged>), [onNodeReady](<Tagpopup.md#evento%20onNodeReady>) e [onNodeUnready](<Tagpopup.md#onNodeUnready>)
  * Novos eventos na tag [dataLink](<TagdataLink.md>):
    * novos eventos: [onUserChange](<TagdataLink.md#onUserChange>) e [onPersistedChange](<TagdataLink.md#onPersistedChange>)
  * Novos eventos no objeto [NodeObserver](<ObjetoNodeObserver.md>)
    * [onUserChanged](<ObjetoNodeObserver.md#onUserChanged>), [onDeepUserChanged](<ObjetoNodeObserver.md#onDeepUserChanged>), [onPersistedChanged](<ObjetoNodeObserver.md#onPersistedChanged>) e [onDeepPersistedChanged](<ObjetoNodeObserver.md#onDeepPersistedChanged>)
  * Novas propriedades para a [Tag richEdit](<TagrichEdit.md>):
    * [animateImages](<TagrichEdit.md#property%20animateImages>)
  * Novas propriedades para a [Tag popup](<Tagpopup.md>)
    * [autoScopeNode](<Tagpopup.md#autoScopeNode>)
  * [String de cores](<StringdecoresnoLuaForm.md>) agoram aceitam o formato short-hand hex colors (Exemplo: #F0C é um short-hand que equivale a cor #FF00CC)
  * Novidades em macros:
    * [inRoom](<BibliotecaparaMacrosemLua.md#inRoom>)
  * Novidades na biblioteca fireDrive
    * [fireDrive.quickUpload](<BibliotecaFireDrive.md#quickUpload>)
  * A biblioteca RRPG foi renomeada para Firecast (mas será mantida compatibilidade com códigos antigos)
  * Novas funções na biblioteca NDB
    * [NDB.getPersistedAttributeValue](<BibliotecaNDB.md#ndb.getPersistedAttributeValue>)
    * [NDB.copy](<BibliotecaNDB.md#NDB.copy>)
    * [NDB.exportXML](<BibliotecaNDB.md#NDB.exportToXML>)
    * [NDB.importXML](<BibliotecaNDB.md#NDB.importXML>)
  * Novas funções na biblioteca Firecast
    * [Firecast.registerChatToolButton](<BibliotecaFirecast.md#registerCharToolButton>)
    * [Firecast.unregisterChatToolButton](<BibliotecaFirecast.md#unregisterChatToolButton>)
  * Novas informações na biblioteca [Firecast.Plugins](<BibliotecaFirecastPlugins.md>) a respeito dos plugins instalados:
    * compilationTimestamp, compilationTimestampStr e compilationDigest.
  * Modificações na biblioteca Internet
    * Novo parâmetro "cacheMode" na função [Internet.download](<BibliotecaInternet.md#internet.download>)
  * Mudanças na forma de instalação e carregamento dos plugins:
    * Agora o conteúdo original do arquivo .rpk não é mais extraído no HD físico do dispostivio. Arquivos que forem criados durante a execução do plugin são salvos no HD físico do usuário. O [VHD (HD Virtual)](<HDVirtual.md>) do plugin agora é composto pela união lógica do conteúdo do arquivo .rpk + arquivos que foram criados durante a execução. O Firecast faz essa união lógica automaticamente de forma transparente para que o programador não precise se preocupar.
    * Agora, durante o carregamento de um plugin instalado, se houver um arquivo "/init.lua" na raiz do plugin, ele é carregado antes dos outros arquivos \*.lua
  * Mudanças na biblioteca VHD
    * Nova função: [VHD.registerAlias](<BibliotecaVHD.md#VHD.registerAliases>)
  * Mudanças na biblioteca Locale
    * Nova função: [Locale.loadLangTexts](<BibliotecaLocale.md#Locale.loadLangTexts>) .
  * Mudanças na biblioteca Utils
    * Nova função [Utils.generateUniqueString](<BibliotecaUtils.md#Utils.generateUniqueString>)
  * Mudanças no comando rdk
    * Nova opção: lint - Faz uma verificação completa no código fonte do plugin
    * Nova opção: buildrep - Usado para compilar vários projetos SDK3 em um repositório, ideal para usar no github do firecast.
    * LuaCheck - Agora o rdk está integrado com o LuaCheck, uma biblioteca open-source que verifica e aponta coisas suspeitas no código lua.

&nbsp;

&nbsp;

## SDK 3.4b (13/11/2017)

* &nbsp;
  * Novo parâmetro para a função [Dialogs.choose](<BibliotecaDialogs.md#Dialogs.choose>): shortCircuit
  * Novo parâmetro para as macros: [choose,](<BibliotecaparaMacrosemLua.md#choose>) [chooseCharacterOfPlayer,](<BibliotecaparaMacrosemLua.md#chooseCharacterOfPlayer>) [chooseCharacter](<BibliotecaparaMacrosemLua.md#chooseCharacter>), [choosePlayer](<BibliotecaparaMacrosemLua.md#choosePlayer>): shortCircuit

## SDK 3.4 (04/09/2017)

* &nbsp;
  * Novas funções na biblioteca ndb:
    * [ndb.editPermissions](<BibliotecaNDB.md#ndb.editPermissions()>)
    * [ndb.broadcastMessage](<BibliotecaNDB.md#broadcastMessage>)
    * [ndb.newBroadcastListener](<BibliotecaNDB.md#newBroadcastListener>)
    * [ndb.onReady](<BibliotecaNDB.md#ndb.onReady>)
  * Novo evento no objeto [NodeObserver](<ObjetoNodeObserver.md>):
    * [onStateChanged](<ObjetoNodeObserver.md#onStateChanged>)
  * Novos eventos na tag Form
    * [onNodeReady](<Tagform.md#evento%20onNodeReady>)
    * [onNodeUnready](<Tagform.md#onNodeUnready>)
  * Novas funções no objeto Scene
    * [scene:broadcastMessage](<ObjetoScene.md#scene:broadcastMessage>)
    * [scene:newBroadcastListener](<ObjetoScene.md#scene:newBroadcastListener>)
  * Nova tag/componente visual:
    * [Tag richEdit](<TagrichEdit.md>)
  * Nova mensagem-evento:
    * ["HandleChatTextInput"](<MensagensdeChat.md#HandleChatTextInput>) que permite o programador alterar o texto digitado por um usuário antes dele ser processado pelo RRPG.
    * ["SessionLogin"](<MensagensdeConexao.md#SessionLogin>) que notifica o programador quando o usuário tiver feito Login com sucesso no servidor RRPG.
  * Novas funções na biblioteca VHD
    * [VHD.forceDirectory](<BibliotecaVHD.md#forceDirectory>)
    * [VHD.deleteFile](<BibliotecaVHD.md#deleteFile>)
    * [VHD.deleteDirectory](<BibliotecaVHD.md#deleteDirectory>)
    * [VHD.directoryExists](<BibliotecaVHD.md#directoryExists>)
    * [VHD.enumerateContent](<BibliotecaVHD.md#enumerateContent>)
  * Novas funções na biblioteca Dialogs
    * [Dialogs.saveFile](<BibliotecaDialogs.md#saveFile>)
    * [Dialogs.selectImageURL](<BibliotecaDialogs.md#selectImageURL>)
    * [Dialogs.choose](<BibliotecaDialogs.md#Dialogs.choose>)
    * [Dialogs.chooseMultiple](<BibliotecaDialogs.md#Dialogs.chooseMultiple>)
  * Novas funções no objeto Personagem:
    * [personagem:loadSheetNDB](<ObjetoPersonagem.md#loadSheetNDB>)
  * Novas funções no objeto Jogador:
    * [jogador:getBarValue](<ObjetoJogador.md#getBarValue>)
    * [jogador:requestSetBarValue](<ObjetoJogador.md#requestSetBarValue>)
    * [jogador:getEditableLine](<ObjetoJogador.md#getEditableLine>)
    * [jogador:requestSetEditableLine](<ObjetoJogador.md#requestSetEditableLine>)
  * Novas funções para serem usados em Macros Lua
    * [load](<BibliotecaparaMacrosemLua.md#load>)
    * [showMessage](<BibliotecaparaMacrosemLua.md#load>)
    * [alert](<BibliotecaparaMacrosemLua.md#alert>)
    * [confirmOkCancel](<BibliotecaparaMacrosemLua.md#confirmOkCancel>)
    * [confirmYesNo](<BibliotecaparaMacrosemLua.md#confirmYesNo>)
    * [inputQuery](<BibliotecaparaMacrosemLua.md#inputQuery>)
    * [selectImageURL](<BibliotecaparaMacrosemLua.md#selectImageURL>)
    * [choose](<BibliotecaparaMacrosemLua.md#choose>)
    * [chooseMultiple](<BibliotecaparaMacrosemLua.md#chooseMultiple>)
    * [invoke](<BibliotecaparaMacrosemLua.md#invokeMacro>)
    * [myCharacter](<BibliotecaparaMacrosemLua.md#myCharacter>)
    * [sheet](<BibliotecaparaMacrosemLua.md#sheet>)
    * [chooseCharacter](<BibliotecaparaMacrosemLua.md#chooseCharacter>)
    * [chooseCharacters](<BibliotecaparaMacrosemLua.md#chooseCharacters>)
    * [chooseCharacterOfPlayer](<BibliotecaparaMacrosemLua.md#chooseCharacterOfPlayer>)
    * [choosePlayer](<BibliotecaparaMacrosemLua.md#choosePlayer>)
    * [choosePlayers](<BibliotecaparaMacrosemLua.md#choosePlayer>)
    * [getCharacterOfPlayer](<BibliotecaparaMacrosemLua.md#getCharacterOfPlayer>)
    * [getCharacterSheet](<BibliotecaparaMacrosemLua.md#getSheetOfCharacter>)
  * Instalação de plug-ins no Android ficou mais fácil. Basta baixar o .rpk no celular e mandar abrí-lo (O app interceptará para instalar o plugin).
  * Agora o comando "rdk c" verifica se existem lua forms com nomes duplicados.
  * Para manter compatibilidade entre sistemas operacionais, O SDK3 ao verificar se um arquivo existe no HD Virtual, ele compara o nome do arquivo de forma case-sensitive mesmo no Windows.

&nbsp;

&nbsp;

## SDK 3.3 (06/12/2016)

&nbsp;

Grandes mudanças:

* &nbsp;
  * API para Scene 3
  * Possibilidade de realizar [drag and drop / arrastar e soltar](<ArrastandoeSoltandoInformacoesDr.md>) no SDK 3.

&nbsp;

Outras mudanças detalhadas:

* &nbsp;
  * Nova biblioteca: [Biblioteca SceneLib](<BibliotecaSceneLib.md>)
  * Nova biblioteca para lidar com idiomas e regiões: [Biblioteca Locale](<BibliotecaLocale.md>)
  * Alterações na biblioteca GUI:&nbsp;
    * Nova Classe [InertialMovement](<ObjetoInertialMovement.md>)
    * Nova função: [gui.newInertialMovement();](<BibliotecaGUI.md#newInertialMovement()>)
    * Nova função: [gui.newColorComboBox()](<BibliotecaGUI.md#newColorComboBox>)
    * Novos objetos: [Drag](<ObjetoDrag.md>), [Drop](<ObjetoDrop.md>).
    * Novos eventos: [onStartDrag](<Caracteristicasdetodasastagsvisu.md#onStartDrag>) e [onStartDrop](<Caracteristicasdetodasastagsvisu.md#onStartDrop>)
  * Alterações na biblioteca NDB:
    * Novos métodos: [ndb.newTransaction](<BibliotecaNDB.md#ndb.newTransaction()>), [ndb.pushTransaction,](<BibliotecaNDB.md#ndb.pushTransaction()>) [ndb.popTransaction](<BibliotecaNDB.md#ndb.popTransaction>), [ndb.getServerUTCTime](<BibliotecaNDB.md#ndb.getServerUTCTime>)
    * Novo objeto: [NodeTransaction](<ObjetoNodeTransaction.md>)
  * Agora os comandos "rdk c" e "rdk i" interpretam os arquivos ".lfm" e geram seus respectivos ".lfm.lua" em outro diretório dentro da pasta "output" do projeto.
  * Agora o SDK3 utiliza a versão Lua 5.3
  * Novas tags do Lua Form:
    * [Tag colorComboBox](<TagcolorComboBox.md>)
  * Alterações na [Tag edit](<Tagedit.md>):
    * Novas propriedades: decimalPlaces, asNumber
    * Novo type "float" para números reais.
  * Alterações na T[ag flowLayout](<TagflowLayout.md>):
    * Novas propriedades: contentWidth e contentHeight
  * Alterações na [Tag path](<Tagpath.md>):
    * Novas propriedades: roundToPixel
  * Alterações na [Tag form](<Tagform.md>):
    * Novas propriedades: isShowing
  * Alterações na biblioteca rrpg
    * Novos objetos: [SceneUnitClass](<ObjetoSceneUnitClass.md>)

&nbsp;

## SDK 3.2 (29/02/2016)

* &nbsp;
  * Alterações em todas as tags visuais:
    * Novas propriedades:&nbsp;
      * [cursor](<Caracteristicasdetodasastagsvisu.md#cursor>)
      * [hint](<Caracteristicasdetodasastagsvisu.md#propriedade%20hint>)
  * Alterações na tag progressBar:
    * Nova propriedade: [colorMode](<TagprogressBar.md#colorMode>)
  * Alterações na tag form:
    * Novo formType: [tablesDock](<Tagform.md#propriedade%20formType>)
  * Alterações na tag imageCheckBox
    * Nova propriedade: [autoChange](<TagimageCheckBox.md#propriedade%20autoChange>)
  * Alterações na tag edit:
    * Novo evento: [onUserChange](<Tagedit.md#onUserChange>)
  * Alterações no objeto Chat:
    * Novas funções que permitem o envio de mais tipos de mensagem para chats: [enviarAcao](<ObjetoChat.md#enviarAcao>), [enviarRisada](<ObjetoChat.md#enviarRisada>), [enviarNarracao](<ObjetoChat.md#enviarNarracao>), [enviarMensagemNPC](<ObjetoChat.md#enviarMensagemNPC>)
  * Alterações na biblioteca rrpg.plugins:
    * Novas funções:
      * rrpg.plugins.getInstalledTablesDock
  * Novas mensagens-eventos do RRPG:
    * [Mensagens de estado das mesas](<MensagensdeEstadodasMesas.md>)
  * Alterações no objeto Mesa:
    * Novas propriedades:&nbsp;
      * [podeTablesDock](<ObjetoMesa.md#podeTablesDock>)
      * [activeChat](<ObjetoMesa.md#activeChat>)
    * Novos métodos: [abrirNDBDeMesa](<ObjetoMesa.md#mesa:abrirNDBDeMesa>)
  * Alterações na biblioteca ndb:
    * Novas funções:
      * [ndb.getState](<BibliotecaNDB.md#ndb.getState>)
      * [ndb.newObserver](<BibliotecaNDB.md#ndb.newObserver>)
      * [Funções de gerenciamento de permissões](<BibliotecaNDB.md#funções%20de%20permissões>)
    * Novos objetos:
      * [NodeObserver](<ObjetoNodeObserver.md>)\
&nbsp;
  * Alterações na biblioteca system:
    * Novas funções:
      * [system.isMobile()](<BibliotecaSystem.md#isMobile()>)

&nbsp;

* &nbsp;
  * Novos tutoriais:
    * [Como criar um botão que esconde itens de uma lista dinâmica de alguns usuários](<Criarumbotaoqueescondeitensdeuma.md>)
    * [Como criar uma janela acoplável de mesa](<Criarumajanelaacoplaveldemesa.md>)

&nbsp;

&nbsp;

* &nbsp;
  * Alterações nas Macros:
    * Novas funções para serem utilizadas em Macros em Lua: [agir](<BibliotecaparaMacrosemLua.md#agir()>), [narrar](<BibliotecaparaMacrosemLua.md#narrar()>), [enviarNPC](<BibliotecaparaMacrosemLua.md#enviarNPC>)

## SDK 3.1 (31/10/2015)

&nbsp;

* &nbsp;
  * Novas funções na blblioteca utils:
    * [utils.zlibCompress](<BibliotecaUtils.md#utils.zlibCompress>)
    * [utils.zlibDecompress](<BibliotecaUtils.md#utils.zlibDecompress>)
    * [utils.zlibCompressAsync](<BibliotecaUtils.md#utils.zlibCompressAsync>)
    * [utils.zlibDecompressAsync](<BibliotecaUtils.md#utils.zlibDecompressAsync>)
    * [utils.newMemoryStream](<BibliotecaUtils.md#utils.newMemoryStream>)
    * [utils.newTempFileStream](<BibliotecaUtils.md#newTempFileStream>)
    * [tryFinally](<BibliotecaUtils.md#tryFinally>)
  * Alterações no objeto Stream
    * Novas funções:
      * [stream:readAsBase64](<ObjetoStream.md#stream:readAsBase64>)
      * [stream:writeBase64](<ObjetoStream.md#stream:writeBase64>)
      * [stream:copyFrom](<ObjetoStream.md#stream:copyFrom>)
    * Novas propriedades
      * [stream.md5](<ObjetoStream.md#propriedade%20md5>)
      * [stream.sha1](<ObjetoStream.md#propriedade%20sha1>)
  * Alterações na tag Image:
    * Novas propriedades: [naturalWidth](<Tagimage.md#propriedade%20naturalWidth>) e [naturalHeight](<Tagimage.md#propriedade%20naturalHeight>)
    * Novo evento: [onLoad](<Tagimage.md#Evento%20OnLoad>)
  * Alterações na tag recordList:
    * Novo evento: [onCompare](<TagrecordList.md#onCompare>)
    * Novo método: [recordList:sort](<TagrecordList.md#recordList:sort()>)
    * Novo método: [recordList:scrollToNode](<TagrecordList.md#recordList:scrollToNode>)
  * Alterações na tag flowLayout:
    * Novo evento: [onAfterLayoutCalc](<TagflowLayout.md#onAfterLayoutCalc>)
  * Alterações em todas as tags visuais:
    * Novo evento: [onMenu](<Caracteristicasdetodasastagsvisu.md#Evento%20onMenu>)
  * Novas funções na biblioteca internet:
    * [internet.newHTTPRequest](<BibliotecaInternet.md#newHTTPRequest>)
    * [internet.httpEncode](<BibliotecaInternet.md#internet.httpEncode>)
    * [internet.httpDecode](<BibliotecaInternet.md#internet.httpDecode>)
  * Novos objetos
    * [Objeto HTTPRequest](<ObjetoHTTPRequest.md>) (instanciado pela função [internet.newHTTPRequest](<BibliotecaInternet.md#newHTTPRequest>))
  * Novas funções na biblioteca rrpg.plugins:
    * [Funções para intercomunicação de plug-ins](<BibliotecaFirecastPlugins.md#Intercomunicação%20de%20plug-ins>)
  * Novas funções na biblioteca dialogs:
    * [dialogs.openFile](<BibliotecaDialogs.md#dialogs.openFile>)
    * [dialogs.saveFile](<BibliotecaDialogs.md#dialogs.saveFile>)
  * Novas bibliotecas:
    * [Biblioteca fireDrive](<BibliotecaFireDrive.md>)
    * [Biblioteca system](<BibliotecaSystem.md>)
  * Novas Tags do Lua Form:
    * [Tag progressBar](<TagprogressBar.md>)
  * Novas funções na biblioteca gui:
    * [gui.newProgressBar](<BibliotecaGUI.md#gui.newProgressBar>)
  * Novas funções na biblioteca ndb:
    * [ndb.beginUpdate](<BibliotecaNDB.md#ndb.beginUpdate>)
    * [ndb.endUpdate](<BibliotecaNDB.md#ndb.endUpdate>)
  * Novas funções na biblioteca rrpg:
    * [rrpg.getCurrentUser](<BibliotecaFirecast.md#rrpg.getCurrentUser>)
  * Correção de Bugs:
    * Corrigido o bug que impedia de manipular os eventos onMouseDown e onMouseUp dos controles
    * Corrigido o bug que impedia de alterar a cor do texto da tag textEditor

&nbsp;

## SDK 3.0d (22/08/2015)

* &nbsp;
  * Alterações na [tag recordList](<TagrecordList.md>)
    * Adicionado as propriedades [selectable](<TagrecordList.md#propriedade%20selectable>), [selectedNode](<TagrecordList.md#propriedade%20selectedNode>) e [selectedForm](<TagrecordList.md#propriedade%20selectedForm>)
    * Adicionado os eventos: [onSelect](<TagrecordList.md#Evento%20onSelect>), [onBeginEnumeration](<TagrecordList.md#Evento%20onBeginEnumeration>), [onItemAdded](<TagrecordList.md#evento%20onItemAdded>), [onItemRemoved](<TagrecordList.md#evento%20onItemRemoved>) e [onEndEnumeration](<TagrecordList.md#Evento%20onEndEnumeration>)
    * O método [append](<TagrecordList.md#método%20append>) agora retorna um [objeto nodo](<ObjetoNodo.md>)
  * Alterações na [tag form](<Tagform.md>):
    * Novas propriedades: [minWidth](<Tagform.md#propriedade%20minWidth>) e [maxWidth](<Tagform.md#propriedade%20maxWidth>).
  * Alterações na [tag popup:](<Tagpopup.md>)
    * Nova propriedade: [scopeNode](<Tagpopup.md#propriedade%20scopeNode>)
  * Alterações na tag [popupForm](<TagpopupForm.md>):
    * Nova propriedade: [resizable](<TagpopupForm.md#propriedade%20resizable>)
  * Nova tag do lua form: [dataScopeBox](<TagdataScopeBox.md>)
    * Novo método [gui.newDataScopeBox](<BibliotecaGUI.md#função%20gui.newDataScopeBox>)
  * Novas mensagem-eventos do RRPG:&nbsp;
    * [HandleChatCommand](<MensagensdeChat.md>)
    * [ChatMessage](<MensagensdeChat.md#evento%20ChatMessage>)
    * [ListChatCommands](<MensagensdeChat.md#%22ListChatCommands%22>)
  * Alterações no [Objeto Chat:](<ObjetoChat.md>)
    * Novo método: [chat:escrever](<ObjetoChat.md#função%20chat:escrever>)
  * Alterações no [Objeto mesa](<ObjetoMesa.md>):
    * Novos métodos: [mesa:requestSetModerada](<ObjetoMesa.md#função%20requestSetModerada>)
  * Alterações no [Objeto Jogador](<ObjetoJogador.md>):
    * Novos métodos: [jogador:requestSetCego](<ObjetoJogador.md#j:requestSetIsCego>), [jogador:requestSetMudo](<ObjetoJogador.md#j:requestSetIsMudo>), [jogador:requestSetVoz](<ObjetoJogador.md#j:requestSetHaveVoice>), j[ogador:requestSetJogador,](<ObjetoJogador.md#j:requestSetIsJogador>) [jogador:requestKick](<ObjetoJogador.md#jogador:requestKick>)
  * Novas funções utilitárias:
    * [utils.removerFmtChat()](<BibliotecaUtils.md#função%20removerTagsFmtChat>)
  * Novas funções na biblioteca [gui](<BibliotecaGUI.md>):
    * [gui.openInBrowser](<BibliotecaGUI.md#função%20openInBrowser>)

&nbsp;

* &nbsp;
  * Novos tutoriais:
    * [Criar uma lista dinâmica + painel de detalhes](<Criarumalistadinamicapaineldedet.md>)

&nbsp;

## SDK 3.0 (07/08/2015)

* &nbsp;
  * Alterações no [objeto Rolagem](<ObjetoRolagem.md>):
    * Nova função: [rolarLocalmente](<ObjetoRolagem.md#função%20rolarLocalmente>)
  * Alterações no [objeto Chat](<ObjetoChat.md>)
    * Novo parâmetro "callback" na [função rolarDados](<ObjetoChat.md#função%20rolarDados>)

&nbsp;

## SDK 3.0 beta 2 (31/07/2015)

* &nbsp;
  * Funções para exibir Lua Forms como popup na interface: [gui.showPopup](<BibliotecaGUI.md#função%20showPopup>) e [gui.closePopup](<BibliotecaGUI.md#função%20closePopup>)
  * Novas tags do lua form:
    * [radioButton](<TagradioButton.md>) e função [gui.newRadioButton](<BibliotecaGUI.md#função%20newRadioButton>)
    * [popupForm](<TagpopupForm.md>) e função [gui.newPopupForm](<BibliotecaGUI.md#função%20gui.newPopupForm>)
    * [activityIndicator](<TagactivityIndicator.md>) e função [gui.newActivityIndicator](<BibliotecaGUI.md#função%20newActivityIndicator>)
  * Mudanças na tag form:
    * Novos eventos: [OnShow](<Tagform.md#Evento%20OnShow>) e [OnHide](<Tagform.md#Evento%20OnHid>)
    * Novos métodos: [lockWithActivity](<Tagform.md#método%20lockWithActivity>) e [unlockWithActivity](<Tagform.md#método%20unlockWithActivity>)
  * Mudanças na [tag edit](<Tagedit.md>):
    * Novos atributos: [enterKeyType](<Tagedit.md#Propriedade%20enterKeyType>), [type](<Tagedit.md#propriedade%20type>), [min](<Tagedit.md#propriedade%20min>) e [max](<Tagedit.md#Propriedade%20max>)
  * Mudanças na [tag recordList](<TagrecordList.md>):
    * Novo atributo: [layout](<TagrecordList.md#propriedade%20layout>)
  * Novas funções utilitárias:
    * [utils.compareStringPtBr](<BibliotecaUtils.md#função%20compareStringPtBr>)
    * [setInterval](<BibliotecaUtils.md#função%20setInterval>) e [clearInterval](<BibliotecaUtils.md#função%20clearInterval>)
    * [setTimeout](<BibliotecaUtils.md#função%20setTimeout>) e [clearTimeout](<BibliotecaUtils.md#função%20clearTimeout>)
    * [utils.binaryEncode](<BibliotecaUtils.md#utils.binaryEncode>) , [utils.binaryDecode](<BibliotecaUtils.md#utils.binaryDecode>) e [utils.getBinarySize](<BibliotecaUtils.md#utils.getBinarySize>)
  * Mudanças no objeto Mesa:
    * Novas funções: findJogador e [findBibliotecaItem](<ObjetoMesa.md#função%20findBibliotecaItem>).
  * Novas bibliotecas para usar no código Lua:
    * [Biblioteca rrpg.messaging](<BibliotecaFirecastMessaging.md>)
    * [Biblioteca rrpg.plugins](<BibliotecaFirecastPlugins.md>)
    * [Biblioteca rrpg.requests](<BibliotecaFirecastRequests.md>)
    * [Biblioteca internet](<BibliotecaInternet.md>)
  * Mudanças na biblioteca ndb:
    * Novas funções: [ndb.newMemNodeDatabase](<BibliotecaNDB.md#função%20newMemNodeDatabase>)
  * Mudanças na biblioteca dialogs:
    * Novas funções: [dialogs.inputQuery](<BibliotecaDialogs.md#dialogs.inputQuery>)
  * Correção de bug na propriedade fontColor da tag comboBox.

&nbsp;

## SDK 3.0 beta 1 (01/06/2015)

Primeira versão do SDK 3


***
_Created with the Personal Edition of HelpNDoc: [Transform Your Word Document into a Professional eBook with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-word-docx-file-to-an-epub-or-kindle-ebook/>)_
