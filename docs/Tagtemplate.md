# Tag template

# Tag template

Com esta tag, o programador pode criar seu próprio conjunto de tags do Lua Form que sempre que forem usada, serão substituídas pelo conteúdo do **template**.

&nbsp;

Observação: Esta tag **não** representa um componente do lua form e todas as tags que estão dentro do **template** só existirão de fato quando o modelo for invocado.

&nbsp;

## Características

### Propriedades e atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **name** | String | \<Não há valor padrão\> | Nome do template. É através deste campo que o programador consegue invocar o modelo posteriormente, usando uma tag de mesmo nome.&nbsp; O preenchimento deste campo é **obrigatório.** |


&nbsp;

## Definindo e invocando templates

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<template** name="MinhaTag"**\>**                 **\<label** text="Label da Minha Tag" align="top" horzTextAlign="center"**/\>**         **\</template\>** **\</form\>** |
| --- |


\
Neste exemplo, usando **template,** nós definimos um modelo chamado MinhaTag....&nbsp;

Mas só a definição do template não acarreta em nada\! Veja como o exemplo acima fica:

&nbsp;

![Image](<lib/NewItem111.png>)

&nbsp;

É preciso invocar o modelo....&nbsp;

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<template** name="MinhaTag"**\>**                 **\<label** text="Label da Minha Tag" align="top" horzTextAlign="center"**/\>**         **\</template\>**          **\<MinhaTag/\>**         **\<MinhaTag/\>**         **\<MinhaTag/\>**         **\<MinhaTag/\>** **\</form\>** |
| --- |


&nbsp;

Agora invocamos "MinhaTag" 4 vezes... Toda vez que usamos a tag "MinhaTag" no exemplo, ela foi substituída por uma cópia do conteúdo de **template.**

&nbsp;

![Image](<lib/NewItem112.png>)

&nbsp;

&nbsp;

Se adicionarmos um edit ao **template**, o resultado mudaria para:

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<template** name="MinhaTag"**\>**                 **\<label** text="Label da Minha Tag" align="top" horzTextAlign="center"**/\>**                 **\<edit** align="top"**/\>**         **\</template\>**          **\<MinhaTag/\>**         **\<MinhaTag/\>**         **\<MinhaTag/\>**         **\<MinhaTag/\>** **\</form\>** |
| --- |


&nbsp;

&nbsp;

![Image](<lib/NewItem113.png>)

&nbsp;

## Passando parâmetros para o template

&nbsp;

É possível passar parâmetros para o template na hora da substituição\! Para passar um parâmetro, basta definir um atributo ao invocar o modelo e para usar o parâmetro no modelo, o programador deve usar **$(nomeDoAtributo)** para a substituição parametrizada.

&nbsp;

Exemplo:

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<template** name="MinhaTag"**\>**                 **\<label** text="Atributo $(titulo)" align="top" horzTextAlign="center"**/\>**                 **\<edit** text="$(conteudo)" align="top" horzTextAlign="center"**/\>**         **\</template\>**          **\<MinhaTag** titulo="Força" conteudo="10"**/\>**         **\<MinhaTag** titulo="Destreza" conteudo="14"**/\>**         **\<MinhaTag** titulo="Inteligência" conteudo="17"**/\>**        **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem114.png>)

&nbsp;

Observação: Quando a tag template é invocada com um corpo texto (Exemplo: \<minhaTag\>Corpo Texto\</minhaTag\>), um parâmetro chamado "body" é criado com este conteúdo.

&nbsp;

&nbsp;

## Templates avançados usando LUA na hora da substituição.

É possível criar templates avançados usando [A linguagem de programação LUA](<AlinguagemdeprogramacaoLUA.md>) na hora da substituição.&nbsp;

Todo comentário de XML dentro de templates são tratados como códigos lua que devem ser executado no momento da substituição\!

&nbsp;

Exemplo:

&nbsp;

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<template** name="Municao"**\>**                 **\<layout** width="$(largura)" height="20" align="top"**\>**                                             **\<label** text="$(titulo) :" align="left" horzTextAlign="center" width="60"**/\>**&nbsp;                         *\<\!-- for  i = 1, quantidade, 1 do --\>*                                           **\<checkBox** align="left" width="20"**/\>**                                             *\<\!-- end; --\>*                 **\</layout\>**         **\</template\>**                **\<Municao** largura="300" titulo="Flechas" quantidade="20"**/\>**         **\<Municao** largura="300" titulo="Bombas" quantidade="4"**/\>**         **\<Municao** largura="300" titulo="Dardos" quantidade="10"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem115.png>)

&nbsp;

Neste exemplo, o parâmetro "quantidade" é utilizado em um código LUA para emitir várias vezes a tag \<checkBox\> durante o tempo de substituição. Vários checkBox foram emitidos com pouco esforço.

&nbsp;

## Exemplos

### Exemplo 1 - Uma pequena ficha usando templates

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                **\<template** name="LayoutUmCampo"**\>**                 **\<layout** width="64" align="left" margins="{left=2, right=2}"**\>**                         **\<edit** field="$(campo)" height="30" horzTextAlign="center" fontSize="20" align="top"**/\>**&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **\<label** text="$(titulo)" align="top" horzTextAlign="center" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; vertTextAlign="leading" autoSize="true"**/\>** &nbsp;               **\</layout\>**         **\</template\>**&nbsp;         **\<layout** left="10" top="10" width="200" height="64"**\>**                   **\<LayoutUmCampo** campo="combate.armadura" titulo="Armadura"**/\>**                 **\<LayoutUmCampo** campo="saude.pontosDeVida" titulo="Pontos de Vida"**/\>**                 **\<LayoutUmCampo** campo="equipamentos.carga" titulo="Carga (kg)"**/\>**                                 **\</layout\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem49.png>)

&nbsp;

### Exemplo 2 - Lista de perícias de D\&D 3.5 usando templates

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<template** name="CampoEmUmLayoutDeCampos"**\>**                               **\<layout** align="top" height="17" margins="{bottom=2}"**\>**                         **\<checkBox** width="17" align="left" margins="{right=5}"**/\>**                         **\<label** align="left" width="120" text="$(titulo):" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; horzTextAlign="trailing" margins="{right=5}"**/\>**                         **\<edit** align="left" horzTextAlign="center" fontSize="16" width="64"**/\>**                 **\</layout\>**         **\</template\>**                **\<template** name="LayoutDeCampos"**\>**                 **\<layout** left="20" top="20" width="250" height="800"**\>**                         *\<\!--*                                 *listaDeCampos = totable(body);*                                                                 *for k, v in pairs(listaDeCampos) do*                                         *CampoParaGerar = v;                            *                         *--\>*                                         **\<CampoEmUmLayoutDeCampos** titulo="$(CampoParaGerar)"**/\>**                         *\<\!--    *                             *end;*                         *--\>*                 **\</layout\>**         **\</template\>**                **\<LayoutDeCampos\>**                 {"Abrir Fechaduras", "Acrobacia", "Adestrar Animais",                  "Arte da Fuga", "Atuação", "Avaliação", "Blefar", "Cavalgar",                  "Concentração", "Conhecimento", "Cura", "Decifrar Escrita",                  "Diplomacia", "Disfarce", "Equilíbrio", "Escalar", "Esconder-se",                  "Falsificação", "Furtividade", "Identificar Magia", "Intimidar", "Natação",                  "Observar", "Obter Informação", "Ofícios", "Operar Mecanismo",&nbsp;                  "Ouvir", "Procurar", "Profissão", "Prestidigitação", "Saltar",                  "Sentir Motivação", "Sobrevivência"}         **\</LayoutDeCampos\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem116.png>)

***
_Created with the Personal Edition of HelpNDoc: [Easily create Qt Help files](<https://www.helpndoc.com/feature-tour>)_
