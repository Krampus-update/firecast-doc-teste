# Interfaces Visuais (Lua Forms)

# Interfaces Visuais (Lua Forms)

&nbsp; &nbsp; As interfaces visuais do SDK3, incluindo os modelos de fichas, são feitas usando Lua Forms (arquivos de extensões ‘.lfm’).

## Principais características do Lua Form

* Sua linguagem segue o padrão XML. Saiba mais sobre em [Documentos XML](<DocumentosXML.md>).
* Ao compilar um projeto de plugin ([Comando “rdk c”](<comandordkc.md>)) todos os documentos ‘.lfm’ são validados e compilados em arquivos “.lua”.
* Possui um conjunto próprio de tags e atributos. O plug-in não compila se alguma tag for utilizada incorretamente no arquivo ‘.lfm’. Ver [Tags suportadas pelo Lua Form](<TagssuportadaspeloLuaForm.md>).
* A tag raiz (a mais externa) deve ser “form” ou "popupForm". Ver [Tag FORM](<Tagform.md>) e [Tag popupForm](<TagpopupForm.md>) .
* A posição de cada controle é relativa à posição de sua tag pai/seu controle pai. Saiba mais em [Posição e Tamanho dos Controles](<PosicaoeTamanhodosControles.md>).

## Exemplo 1 – Olá mundo

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** formType="sheetTemplate" dataType="br.com.meusite.MeuDataType"       title="Ficha de Teste" name="frmFichaTeste"**\>**&nbsp;         **\<label** text="Olá mundo"**/\>**  &nbsp; **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem18.png>)

&nbsp;

## Exemplo 2 – Um layout, um label, um edit e um botão

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** formType="sheetTemplate" dataType="br.com.meusite.MeuDataType"           title="Ficha de Teste" name="frmFichaTeste"**\>**&nbsp;         **\<layout** height="30" width="200"**\>**                 **\<label** text="Força:" align="client" horzTextAlign="trailing"**/\>**                   **\<edit** align="right" margins="{left=10}" width="100"**/\>**         **\</layout\>** &nbsp;        **\<button** text="Eu sou um botão" top="40" left="50" width="150"**/\>**     **\</form\>** |
| --- |


\
![Image](<lib/NewItem17.png>)


***
_Created with the Personal Edition of HelpNDoc: [Effortlessly Create Encrypted, Password-Protected PDFs](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
