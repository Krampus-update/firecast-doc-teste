# O arquivo "module.xml"

# Structure

\
Todo projeto de plugin deve conter um arquivo de nome “module.xml” em sua raiz que contém as informações sobre o mesmo. A estrutura das tags/marcações deste documento é:

* **module**
  * **id** – Uma identificação global e única do plug-in. É um texto que contém apenas caracteres alfanuméricos, underlines, pontos e deve conter ao menos 5 caracteres e um máximo de 40. Você deve inventar um valor único para este campo, e, uma vez definido, o ID não deve mudar. Exemplos: “br.com.rrpg.DnD5\_SDK3”, “br.com.outrosite.storytellerX”.
  * **version** – Um texto que identifica a versão do seu plug-in. Não se esqueça de atualizar este campo quando for lançar uma nova versão do seu plug-in =). Exemplos: “1.0”, “1.1”, “1.2b”
  * **info** – Tag que reúne as informações do puglin traduzidas em uma determinada língua. Pode aparecer mais de uma vez, uma para cada tradução. Ela contém as seguintes tags filhas:
    * **name** – O um texto curto que nomeia seu plug-in. Exemplos: “DnD 5”, “Plugin de Mighty Blade”, “Plugin X”, etc..
    * **description** – Um texto breve que descreve o que seu plug-in faz. Exemplos: “Adiciona suporte a fichas de DnD 5”.
    * **author** – Seu nome/nickname
    * **site** – Você possui um site? Coloq-ue aqui o endereço dele se tiver
    * **contact** – Como se faz contato com você? Adicione endereço de e-mail, facebook, twitter, etc..
  * &nbsp; &nbsp; **settings** – A tag to configure the behaviors of your plugin. Available settings are:
    * **automaticStringLocalization** – When true, it allows the Firecast to automatically translate attributes of LFM files and strings passed to the API calls. It's a very cool feature to make your plugin multi-language but may produce inconsistent behaviors. Default: false. See [Criando um plug-in para vários idiomas](<Criandoumnovoprojetodeplugin.md>)\
\
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;

&nbsp;

Exemplo:

| \<?xml version="1.0" encoding="UTF-8"?\> \<**module** sdkVersion="**3.6**"\> &nbsp; &nbsp; \<\!--***O id identifica seu módulo globalmente. Deve ser único, conter apenas caracteres alfanuméricos, underlines, pontos e deve conter ao menos 5 caracteres e um máximo de 40. Uma vez definido o ID, você não deve alterar ele ;)*** --\> &nbsp; &nbsp; \<**id**\>**br.com.rrpg.DnD5\_SDK3**\</**id**\>&nbsp; &nbsp; &nbsp; \<\!--***version é a versão do seu módulo. Quando for lançar uma nova versão do seu módulo, altere aqui =)*** --\> &nbsp; &nbsp; \<**version**\>**1.0**\</**version**\>&nbsp; &nbsp; &nbsp; \<**settings**\> &nbsp; &nbsp; &nbsp; &nbsp; \<**automaticStringLocalization**\>**true**\</**automaticStringLocalization**\> &nbsp; &nbsp; \</**settings**\>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \<**info** lang="**pt-BR**"\> &nbsp; &nbsp; &nbsp; &nbsp; \<\!--***Informações do plugin na língua "pt-BR". Você pode ter várias tags "info", uma para cada tradução que quiser.***--\> &nbsp; &nbsp; &nbsp; &nbsp; \<**name**\>**D\&amp;D 5e**\</**name**\> &nbsp; &nbsp; &nbsp; &nbsp; \<**description**\>**Modelo de ficha de D\&amp;D 5ª edição**\</**description**\> &nbsp; &nbsp; &nbsp; &nbsp; \<**author**\>**Firecast**\</**author**\> &nbsp; &nbsp; &nbsp; &nbsp; \<**site**\>**https://firecast.app/**\</**site**\> &nbsp; &nbsp; &nbsp; &nbsp; \<**contact**\>**https://www.facebook.com/AlyssonRPG**\</**contact**\> &nbsp; &nbsp; \</**info**\>&nbsp; &nbsp; &nbsp; \<**info** lang="**en**"\> &nbsp; &nbsp; &nbsp; &nbsp; \<\!--***Informações do plugin na língua "en". Você pode ter várias tags "info", uma para cada tradução que quiser.***--\> &nbsp; &nbsp; &nbsp; &nbsp; \<**name**\>**D\&amp;D 5th Edition**\</**name**\> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \<**description**\>**D\&amp;D 5th edition character sheet for firecast**\</**description**\> &nbsp; &nbsp; \</**info**\>&nbsp; \</**module**\> |
| --- |


\

***
_Created with the Personal Edition of HelpNDoc: [Single source CHM, PDF, DOC and HTML Help creation](<https://www.helpndoc.com/help-authoring-tool>)_
