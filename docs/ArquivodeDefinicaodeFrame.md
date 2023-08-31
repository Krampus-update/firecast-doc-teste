# Arquivo de Definição de Frame

# Arquivo de Definição de Frame

Todo [frame](<Frames.md>) é definido por um documento [XML](<DocumentosXML.md>) que segue o padrão descrito neste tópico.

&nbsp;

**Importante**: Não é possível utilizar as tags do Lua Form na definição de frames. O documento de definição de frames possui seu próprio conjunto de tags e atributos.

&nbsp;

# Estrutura do documento XML de definição de frame

Todo documento de XML de definição de frame deve ter a [tag frame](<ArquivodeDefinicaodeFrame.md#Tag%20frame>) como tag raiz.

## Tag frame

&nbsp;

Atributos:

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **width** | Float | \<Não há valor padrão e deve ser preenchido\>&nbsp; | A largura em que o frame foi definido.&nbsp; Todo o restante do frame será interpretado usando esta largura como base.&nbsp; |
| **height** | Float | \<Não há valor padrão e deve ser preenchido\>&nbsp; | A altura em que o frame foi definido.&nbsp; Todo o restante do frame será interpretado usando esta altura como base.&nbsp; |
| **autoScaleX** | Boolean | false | Indica como o frame deve se comportar ao ser apresentado em um tamanho diferente do que foi definido.&nbsp; true - O conteúdo do frame será esticado ou comprimido no eixo X para equivaler à nova largura.&nbsp; false - O conteúdo do frame será reposicionado no eixo X, respeitando o ancoramento de cada item do conteúdo do frame.&nbsp; |
| **autoScaleY** | Boolean | false | Indica como o frame deve se comportar ao ser apresentado em um tamanho diferente do que foi definido.&nbsp; true - O conteúdo do frame será esticado ou comprimido no eixo Y para equivaler à nova altura.&nbsp; false - O conteúdo do frame será reposicionado no eixo Y, respeitando o ancoramento de cada item do conteúdo do frame.&nbsp; |


&nbsp;

Tags filhas:

| **Tag filha** | Quantidade | Descrição |
| --- | --- | --- |
| **borders** | &#48; ou 1. (opcional) | Descreve o tamanho das bordas que o frame possui.&nbsp; Leia mais em [Tag borders](<ArquivodeDefinicaodeFrame.md#Tag%20borders>)&nbsp; |
| **draw** | &#48; ou 1. (opcional) | Define os itens que serão desenhados no frame.&nbsp; Leia mais em [Tag draw](<ArquivodeDefinicaodeFrame.md#Tag%20draw>).&nbsp; Estes itens são desenhados embaixo dos controles Lua Form de onde o frame for aplicado.&nbsp; |
| **postdraw** | &#48; o ou 1. (opcional) | Define os itens que serão desenhados após o conteúdo do frame ser desenhado.&nbsp; Leia mais em [Tag postdraw](<ArquivodeDefinicaodeFrame.md#Tag%20postdraw>).&nbsp; Estes itens são desenhados em cima dos controles Lua Form de onde o frame for aplicado.&nbsp; |
| **regions** | &#48; ou 1. (opcional) | Define as [regiões que este frame possui](<FrameseRegioes.md>). Usado para alinhar controles Lua Form no lugar correto do frame.&nbsp; Leia mais em [Tag regions](<ArquivodeDefinicaodeFrame.md#Tag%20regions>).&nbsp; |


## &nbsp;
## Tag borders

&nbsp;

Atributos:

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **left** | Float | &#48;.0 | Define o tamanho da borda esquerda do frame.&nbsp; |
| **top** | Float | &#48;.0&nbsp; | Define o tamanho da borda superior do frame.&nbsp; |
| **right** | Float | &#48;.0 | Define o tamanho da borda da direita do frame.&nbsp; |
| **bottom** | Float | &#48;.0 | Define o tamanho da borda inferior do frame.&nbsp; |


&nbsp;

&nbsp;

## Tag draw

Esta tag contém todos os elementos que são desenhados no frame.

\
Atributos: Esta tag não possui atributos

&nbsp;

Tags filhas:

| **Tag filha** | Quantidade | Descrição |
| --- | --- | --- |
| **image** | &#48; ou várias vezes. (lista) | Cada tag image representa uma imagem que será desenhada.&nbsp; Leia mais em [Tag image](<ArquivodeDefinicaodeFrame.md#Tag%20image>).&nbsp; |


&nbsp;

&nbsp;

&nbsp;

## Tag postdraw

Esta tag contém todos os elementos que são desenhados no frame.

\
Atributos: Esta tag não possui atributos

&nbsp;

Tags filhas:

| **Tag filha** | Quantidade | Descrição |
| --- | --- | --- |
| **image** | &#48; ou várias vezes. (lista) | Cada tag image representa uma imagem que será desenhada acima do controles Lua Form.&nbsp; Leia mais em [Tag image](<ArquivodeDefinicaodeFrame.md#Tag%20image>).&nbsp; |


&nbsp;

&nbsp;

## Tag image

&nbsp;

Atributos:

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **left** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Define onde, no eixo X, a imagem será desenhada. |
| **top** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Define onde, no eixo Y, a imagem será desenhada. |
| **right** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Define onde, no eixo X, a borda direita da imagem será desenhada.&nbsp; A largura da imagem será equivalente a ("right" - "left")&nbsp; |
| **bottom** | Float | \<Não há, preenchimento obrigatório\> | Define onde, no eixo Y, a borda inferior da imagem será desenhada.&nbsp; A altura da imagem será equivalente a ("bottom" - "top")&nbsp; |
| **overflowX** | Enumerado: "none" "tile" "stretch" "center" | "tile"&nbsp; | Define como a imagem será desenhada no eixo X quando a largura a desenhar for diferente da largura definida.&nbsp; "none": A imagem será desenhada apenas uma vez, a cortando se o tamanho diminuir.&nbsp; "tile": A imagem será desenhada várias vezes para que ocupe o novo tamanho.&nbsp; "stretch": A imagem será encolhida ou espichada para o novo tamanho.&nbsp; "center": A imagem será desenhada apenas uma vez no centro.&nbsp; |
| **overflowY** | BoEnumerado: "none" "tile" "stretch" "center"&nbsp; | "tile" | Idem ao atributo "overflowX", porém agora analisando a altura e o eixo Y da imagem.&nbsp; |
| **zOrder** | Float | &#48;.0&nbsp; | Define a ordem em que esta imagem será desenhada.&nbsp; A image que tiver o menor zOrder será desenhada embaixo das outras, enquanto a que tiver maior zOrder será desenhada acima.&nbsp; |


&nbsp;

Tags filhas:

| **Tag filha** | Quantidade | Descrição |
| --- | --- | --- |
| **source** | &#49; vez (preenchimento obrigatório) | A tag source contém informações sobre qual imagem será desenhada.&nbsp; Leia mais em [tag source](<ArquivodeDefinicaodeFrame.md#Tag%20source>).&nbsp; Observação: Enquanto a tag image possui informações relacionadas ao "onde a imagem será desenhada", a tag source possui informações de qual imagem será desenhada.&nbsp; &nbsp; |
| **anchors** | &#48; ou 1 (opcional). | Define como a imagem será ancorada quando o frame for desenhado com um tamanho maior ou menor do que o definido.&nbsp; Leia mais em [tag anchors](<ArquivodeDefinicaodeFrame.md#Tag%20anchors>)&nbsp; A ausência desta tag implica no ancoramento "left e top". &nbsp; |


&nbsp;

## Tag source

&nbsp;

Atributos:

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **url** | String | \<Não há, preenchimento obrigatório\>&nbsp; | Caminho do arquivo da imagem que será desenhada na tela.&nbsp; Contém um caminho relativo à pasta em que se encontra o arquivo ".xml" de definição deste frame.&nbsp; |
| **left** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Este atributo é usado para definir qual parte da imagem, informada pelo atributo "url", será desenhada na tela. &nbsp; É possível desenhar a imagem inteira, ou apenas um pedaço/retângulo dela (o que é bastante útil).&nbsp; Medido em pixels, informa a posição **esquerda** do pedaço/retângulo que será desenhado na tela.&nbsp; |
| **top** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Medido em pixels, informa a posição **superior** do pedaço/retângulo que será desenhado na tela.&nbsp; Veja a descrição do atributo "left". |
| **right** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Medido em pixels, informa a posição **da direita** do pedaço/retângulo que será desenhado na tela.&nbsp; Veja a descrição do atributo "left".&nbsp; |
| **bottom** | Float | \<Não há, preenchimento obrigatório\> | Medido em pixels, informa a posição **inferior** do pedaço/retângulo que será desenhado na tela.&nbsp; Veja a descrição do atributo "left".&nbsp; |


&nbsp;

Tags filhas:&nbsp;

&nbsp; &nbsp; Não há tags filhas.

&nbsp;

&nbsp;

## Tag anchors

Define o ancoramento do componente. \
Quando o frame for desenhado com um tamanho diferente do desenhado, o componente mantém sua posição relativa baseada em sua âncora.

&nbsp;

&nbsp;

Atributos:

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **left** | Boolean | false | Quando true, define um âncora à esquerda.&nbsp; Leia as observações abaixo desta tabela.&nbsp; |
| **top** | Boolean | false&nbsp; | Quando true, define um âncora acima.&nbsp; Leia as observações abaixo desta tabela.&nbsp; |
| **right** | Boolean | false&nbsp; | Quando true, define um âncora à direita.&nbsp; Leia as observações abaixo desta tabela.&nbsp; |
| **bottom** | Boolean | false | Quando true, define um âncora abaixo.&nbsp; Leia as observações abaixo desta tabela.&nbsp; |


&nbsp;

Comportamento de âncora:

* &nbsp;
  * “left” = true, ”right” = false: O componente manterá sempre a mesma posição left/X.
  * “left” = false, “right” = true: A posição left será calculada automaticamente para manter sempre a mesma distância entre sua borda direita e a borda direita do pai/frame.
  * “left” e “right” ambos = true: O controle manterá tanto a distância entre (1) sua borda esquerda com a borda esquerda do pai/frame; (2) como sua borda direita com a borda direita do pai/frame. Para isso, a largura do componente será alterada conforme o tamanho de visualização do frame.
  * “left” e “right” ambos = false: O controle não está ancorado e ocorrerá um efeito similar ao de centralização.

&nbsp;

O comportamento das âncoras “top” e “bottom” é o mesmo das âncoras “left” e “right”, porém agora no eixo Y.

&nbsp;

&nbsp;

Tags filhas:&nbsp;

&nbsp; &nbsp; Não há tags filhas.

&nbsp;

&nbsp;

## Tag regions

Esta tag contém uma lista de tags region, que define regiões no frame que poderão ser usadas para alinhar tags/controles Lua Form posteriormente. Saiba mais em [Frames e Regiões](<FrameseRegioes.md>).

\
Atributos: Esta tag não possui atributos

&nbsp;

Tags filhas:

| **Tag filha** | Quantidade | Descrição |
| --- | --- | --- |
| **region** | &#48; ou várias vezes. (lista) | Cada tag image representa uma região do frame&nbsp; Leia mais em [Tag region](<ArquivodeDefinicaodeFrame.md#Tag%20region>).&nbsp; |


&nbsp;

&nbsp;

## Tag region

&nbsp;

Atributos:

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **name** | String | \<Não há, preenchimento obrigatório\>&nbsp; | Define um nome para esta região para que possa ser usada posteriormente por um controle Lua Form. Saiba mais em [Frames e Regiões](<FrameseRegioes.md>).&nbsp; |
| **left** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Define, onde no eixo X, é a posição esquerda desta região no frame. |
| **top** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Define, onde no eixo Y, é a posição superior desta região no frame. |
| **right** | Float | \<Não há, preenchimento obrigatório\>&nbsp; | Define, onde no eixo X, é a posição da direita desta região no frame.&nbsp; A largura da região será equivalente a ("right" - "left")&nbsp; |
| **bottom** | Float | \<Não há, preenchimento obrigatório\> | Define, onde no eixo Y, é a posição inferior desta região no frame.&nbsp; A altura da região será equivalente a ("bottom" - "top")&nbsp; |
| **autoScaleX** | Boolean | false&nbsp; | Indica como as sub-regiões desta região devem se comportar ao ser apresentadas em um tamanho de frame diferente do que foi definido.&nbsp; true - As sub-regiões serão esticadas ou comprimidas no eixo X para equivaler à nova largura.&nbsp; false - As sub-regiões serão reposicionadas no eixo X, respeitando seus ancoramentos.&nbsp; |
| **autoScaleY** | Boolean | false | Indica como as sub-regiões desta região devem se comportar ao ser apresentadas em um tamanho de frame diferente do que foi definido.&nbsp; true - As sub-regiões serão esticadas ou comprimidas no eixo Y para equivaler à nova altura.&nbsp; false - As sub-regiões serão reposicionadas no eixo Y, respeitando seus ancoramentos&nbsp; |


&nbsp;

Tags filhas:

| **Tag filha** | Quantidade | Descrição |
| --- | --- | --- |
| **anchors** | &#48; ou 1 (opcional). | Define como a região será ancorada quando o frame for desenhado com um tamanho maior ou menor do que o definido.&nbsp; Leia mais em [tag anchors](<ArquivodeDefinicaodeFrame.md#Tag%20anchors>)&nbsp; A ausência desta tag implica no ancoramento "left e top". &nbsp; |
| **regions** | &#48; ou 1 (opcional). | Define as sub-regiões desta região. &nbsp; Leia mais em [Tag regions](<ArquivodeDefinicaodeFrame.md#Tag%20regions>).&nbsp; |


&nbsp;

# Exemplos

Veja os exemplos em [Exemplos de frames.](<Exemplosdeframes.md>)

***
_Created with the Personal Edition of HelpNDoc: [Create cross-platform Qt Help files](<https://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework>)_
