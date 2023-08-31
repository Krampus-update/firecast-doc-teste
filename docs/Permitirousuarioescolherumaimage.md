# Permitir o usuário escolher uma imagem dentro da ficha

# Permitir o usuário escolher uma imagem dentro da ficha

&nbsp;

É necessário o usar a [tag image](<Tagimage.md>), colocar sua propriedade "editable" para "true" e definir um "field" para ela.

Adicionalmente, você poderá definir a propriedade "style" da tag como "autoFit" para que o a imagem ocupe todo o espaço definido para ela.

&nbsp;

Exemplo:

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFTeste"**\>**          **\<image** field="imagemDoPersonagem" editable="true" style="autoFit" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; left="20" top="20" width="200" height="200" **/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem184.png>) &nbsp;

&nbsp;

O usuário poderá alterar a imagem quando clicar nela:

&nbsp;

![Image](<lib/NewItem185.png>)

&nbsp;

&nbsp;

Veja também:

* &nbsp;
  * [Interfaces Visuais (Lua Forms)](<InterfacesVisuaisLuaForms.md>)
  * [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)

***
_Created with the Personal Edition of HelpNDoc: [Easily create Qt Help files](<https://www.helpndoc.com/feature-tour>)_
