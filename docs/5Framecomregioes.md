# 5 - Frame com regiões

# Frame com regiões

Deseja-se montar um frame com 2 [regiões](<FrameseRegioes.md>) com a seguinte aparência:

&nbsp;

| ![Image](<lib/pecaCobre\_show.png>) |
| --- |


&nbsp;

&nbsp;

O exemplo utiliza um arquivo de imagem "pecaCobre.png" de tamanho 228x94

&nbsp;

&nbsp;

Arquivo de definição de frame:

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<frame** width="228" height="94" autoScaleY="true" autoScaleX="true"**\>**         **\<borders** left="6" top="7" bottom="6" right="39" **/\>**         **\<draw\>**                          *\<\!-- fundo --\>* &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **\<image** left="0" top="0" right="228" bottom="94" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; overflowX="stretch" overflowY="stretch" zOrder="-1"**\>**                         **\<anchors** left="true" top="true" bottom="true" right="true"**/\>**                         **\<source** url="pecaCobreBckBlack.png" left="0" right="228" top="0" bottom="94"**/\>**                 **\</image\>**                                                **\</draw\>**                **\<regions\>**                 **\<region** name="RegiaoSmallTitulo" left="15" top="30" right="45" bottom="64"**\>**                         **\<anchors** left="true" top="true" bottom="true" right="true"**/\>**                  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **\</region\>**                                **\<region** name="RegiaoValor" left="85" top="7" right="187" bottom="89"**\>**                         **\<anchors** left="true" top="true" bottom="true" right="true"**/\>**&nbsp;                 **\</region\>**               **\</regions\>**      **\</frame\>** |
| --- |


&nbsp;

&nbsp;

Uso no Lua Form:

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<layout** align="top" frameStyle="/frames/meuframe.xml"  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; margins="{left=30, top=30, right=30, bottom=5}"**\>**                 **\<label** horzTextAlign="center" text="PO" frameRegion="RegiaoSmallTitulo"**/\>**                               **\<label** horzTextAlign="center" text="500" frameRegion="RegiaoValor"**/\>**          &nbsp; &nbsp; &nbsp; &nbsp; **\</layout\>**                **\<layout** align="top" frameStyle="/frames/meuframe.xml"  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; margins="{left=30, top=5, right=30, bottom=5}"**\>**                 **\<label** horzTextAlign="center" text="PP" frameRegion="RegiaoSmallTitulo"**/\>**                               **\<label** horzTextAlign="center" text="8" frameRegion="RegiaoValor"**/\>**    &nbsp;       **\</layout\>**       **\</form\>** |
| --- |


&nbsp;

\
![Image](<lib/NewItem154.png>)\
\
Os labels foram automaticamente alinhados às regiões definidas no frame.


***
_Created with the Personal Edition of HelpNDoc: [Elevate Your CHM Help Files with HelpNDoc's Advanced Customization Options](<https://www.helpndoc.com/feature-tour/create-chm-help-files/>)_
