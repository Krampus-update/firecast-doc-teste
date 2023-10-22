---
title: Modelos de Fichas
---

# Modelos de Fichas

Cada modelo de ficha do SDK3 é um documento Lua Form (extensão ‘.lfm’) e toda vez que o usuário abre um personagem, o RRPG Firecast localiza o Lua Form adequado, cria uma nova instância e a exibe na tela.

Veja:
    * [Interfaces Visuais (Lua Forms)](<InterfacesVisuaisLuaForms.md>)
    * [Lua Form e Instâncias](<LuaFormeInstancias.md>)

## Criando um novo modelo de ficha
Para criar um novo modelo de ficha:

1. Crie um arquivo texto vazio de extensão ‘.lfm” dentro da pasta do projeto do plug-in.
2. Abra o arquivo em um editor de texto, copie e cole o seguinte documento:

| **\<?xml** version="1.0" encoding="UTF-8"**?\>**&nbsp; **\<form** formType="sheetTemplate" dataType="DATA\_TYPE\_AQUI"  &nbsp; &nbsp; &nbsp; title="TITULO\_AQUI" name="NOME\_AQUI"**\>**&nbsp; **\</form\>** |
| --- |

1. Preencha os campos “dataType”, “title” e “name”:
   1. *dataType* – Um texto que identifica qual é o tipo de conteúdo do seu modelo de ficha. Você **deve inventar** um Data Type único que possua ao menos cinco caracteres alfanuméricos, "\_" ou "." e que não comece com dígitos. Use a criatividade\! Exemplos: “br.com.rrpg.DnD5\_S3”, “br.com.rrpg.VampiroAMascara”, “br.com.meusite.MeuModeloDeFicha”, “meuplugin.FichaX”, etc..\
&nbsp;
   1. *title* – O título do seu modelo de ficha. Este texto aparecerá na lista de fichas quando o usuário criar um personagem. Exemplos: “DnD 5th”, “Vampiro a Máscara”, “Meu modelo de ficha”, etc..\
&nbsp;
   1. *name* – Nome interno do Lua Form. Deve conter apenas caracteres alfanuméricos ou "\_" e não deve começar com dígitos. Exemplos: “frmDnD5”, “frmVampiroAMascara”, “frmMeuModeloDeFicha”, etc.. Apesar de não ser exigida, a prática de colocar “frm” no início do name é recomendada.

&nbsp;

1. **Pronto\!** Você acaba de criar um modelo de ficha vazio.&nbsp;

&nbsp;

&nbsp;

Veja agora:

1. [Interfaces Visuais (Lua Forms) ](<InterfacesVisuaisLuaForms.md>)para saber mais sobre o arquivo .lfm e completar seu plug-in.
1. [Tutoriais](<Tutoriais.md>) para ter mais ideias para seu modelo de ficha =).

&nbsp;

&nbsp;

## Criando um novo modelo de ficha - Exemplo passo a passo

O exemplo a seguir utiliza o editor de texto Notepad++.

1. Criando o arquivo texto vazio de extensão ‘.lfm’ dentro da pasta do projeto de plug-in:

&nbsp;

![Image](<lib/NewItem16.png>)&nbsp; &nbsp; ![Image](<lib/NewItem15.png>)\
\
![Image](<lib/NewItem14.png>)

&nbsp;

1. Preenchendo o conteúdo do arquivo LFM:\
![Image](<lib/NewItem13.png>)

&nbsp;

1. Instalando o plug-in:\
![Image](<lib/NewItem12.png>)

&nbsp;

1. Testando a ficha no RRPG:

&nbsp;

![Image](<lib/NewItem11.png>)&nbsp; ![Image](<lib/NewItem10.png>)

&nbsp;

| &nbsp; |
| --- |


&nbsp;

\

***
_Created with the Personal Edition of HelpNDoc: [Easily create CHM Help documents](<https://www.helpndoc.com/feature-tour>)_
