# Macros

# Macros

Macros são atalhos criados pelo usuário para comandos/textos que são repetidos frequentemente. Por exemplo: Se o personagem de D\&D do usuário possui um ataque padrão, é conveniente criar uma macro de nome, digamos, "ataque" que faz:

&nbsp;

| /r 1d20 + 5: Rolagem do Ataque /r 1d8 + 5: Rolagem do Dano |
| --- |


&nbsp;

Quando o usuário digitar "/ataque" no chat do RRPG, estes comandos serão executados.

&nbsp;

## Criando e editando suas macros

digite "/macros" no chat do RRPG para abrir o gerenciador de macros\!

&nbsp;

&nbsp;

## Tipos de macros

Existem dois tipos de macros no RRPG:

* Macros Simples
* Macros em Lua

&nbsp;

A macros simples contém comandos que são enviados para o chat, linha a linha. São extremamente fáceis e intuitivas de serem feitas, porém são limitadas.

As macros em Lua contém código de [programação Lua](<AlinguagemdeprogramacaoLUA.md>) e requerem um pouco de conhecimento de programação, porem são flexíveis\!

&nbsp;

## Macros em Lua

As macros em Lua possuem um conjunto de funções utilitárias pré-definidas para serem utilizadas\!

Conheça as [funções disponíveis para as macros em lua](<BibliotecaparaMacrosemLua.md>).

&nbsp;

&nbsp;

Exemplo 1: Fazendo um teste com dificuldade igual a 15\
&nbsp;

| **local** resultado = rolar("1d20 + 5");  **if** resultado \>= 15 **then**         enviar("Acertou\!"); **else**         enviar("Errou\!"); **end**; |
| --- |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Documentation Capabilities with a Help Authoring Tool](<https://www.helpauthoringsoftware.com>)_
