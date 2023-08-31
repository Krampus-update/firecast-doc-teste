# Biblioteca Locale

# Biblioteca Locale

Biblioteca que contém funções para lidar com idiomas e regiões, incluindo funcionalidade para permitir um plug-in em várias línguas

&nbsp;

Exemplo de uso:

| *\-- Primeiro, é necessário usar a unidade "locale.lua"* require("locale.lua");    *-- Agora é possível acessar as funções da biblioteca* Locale.FUNCAO\_DA\_BIBLIOTECA(Parametro1, Parametro2, ...); |
| --- |


&nbsp;

&nbsp;

## Funções da biblioteca Locale

&nbsp;

| **function** lang(txtId) ou **function** LANG(txtId) ou **function** Locale.lang(txtId) |
| --- |


&nbsp;

Percorre todos os arquivos ".lang" do plug-in à procura de um texto cuja identificação seja igual à passada como parâmetro e que combine com o idioma atual do usuário.

Esta função é a principal para você obter strings correto para o idioma do usuário.

&nbsp;

Parâmetros:

* &nbsp;
  * txtId - Uma cadeia de caracteres que identifica o texto que deseja obter

&nbsp;

Retorno:

* &nbsp;
  * Uma cadeia de caracteres contendo o texto para o idioma do usuário.

&nbsp;

Observações:

* &nbsp;
  * A busca ocorre em todos os arquivos de extensão .lang de forma eficiente.
  * Caso a busca não encontre o texto para o idioma do usuário, a busca retornará uma cadeia de caracteres de outro idioma. A função emite um erro se "txtId" não for conhecido em nenhum idioma.
  * Leia o tutorial de [como criar um plug-in multi-línguas](<Criandoumpluginparavariosidiomas.md>) para exemplo\!

&nbsp;

&nbsp;

| **function** Locale.loadLangTexts(langTexts) |
| --- |


&nbsp;

Carrega, em tempo de execução, um arquivo ".lang" para que mais textos traduzidos possam ser encontrados pelas funções [Locale.lang](<BibliotecaLocale.md#lang()>) e [Locale.tryLang](<BibliotecaLocale.md#Locale.tryLang>).

&nbsp;

Parâmetros:

* &nbsp;
  * langTexts - Uma cadeia de caracteres com o conteúdo do arquivo .lang que será carregado em tempo de execução.

&nbsp;

&nbsp;

Observações:

* &nbsp;
  * Leia o tutorial de [como criar um plug-in multi-línguas](<Criandoumpluginparavariosidiomas.md>) para exemplo\!

&nbsp;

&nbsp;

| **function** tryLang(txtId) ou **function** tryLANG(txtId) ou **function** Locale.tryLang(txtId) |
| --- |


&nbsp;

Idêntico à função [lang](<BibliotecaLocale.md#lang()>), porém retorna **nil** ao invés de um erro quando não encontra a tradução.


***
_Created with the Personal Edition of HelpNDoc: [Easily share your documentation with the world through a beautiful website](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
