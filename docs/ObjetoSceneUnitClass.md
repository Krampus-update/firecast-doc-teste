# Objeto SceneUnitClass

# Objeto SceneUnitClass

Este objeto representa um item de scene 2 na biblioteca de uma mesa no RRPG Firecast.

&nbsp;

## Herança

O **Objeto SceneUnitClass** possui todas as características de um Objeto BibliotecaItem. Veja:

* [Objeto BibliotecaItem](<ObjetoBibliotecaItem.md>)
* [Objeto WrappedObject](<ObjetoWrappedObject.md>)

[](<Caracteristicasdetodasastagsvisu.md>)

## Características

Além das características herdadas, o Objeto SceneUnitClass também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **tamanhoX** | Double | (Somente leitura) Contém quantos metros o item ocupa em sua largura no tabuleiro de combate.&nbsp; |
| **tamanhoY** | Double&nbsp; | (Somente leitura) Contém quantos metros o item ocupa em sua altura no tabuleiro de combate. &nbsp; |
| **camada** | Enumerado: "tokens" "objects" "background"&nbsp; | (Somente leitura) Contém em qual camada o item pertence por padrão no tabuleiro de combate. |
| **descricao** | String | (Somente leitura) Contém um texto descritivo do item de scene.&nbsp; |
| **urlImg** | String | (Somente leitura) Contém a URL da imagem do item de scene.&nbsp; |
| **facing** | Enumerado: "rotate" "drawArrow" | (Somente leitura) Contém como o item deve se comportar quando for rotacionado no tabuleiro de combate.&nbsp; "rotate" - Rotacionar também a imagem do item.&nbsp; "drawArrow" - Não rotacionar a imagem e desenhar uma seta indicando a direção do item.&nbsp; |
| **snapToGrid** | Boolean | (Somente leitura) Contém true se o item deve se alinhar ao grid do tabuleiro de combate.&nbsp; |
| **direcaoImg** | Double | (Somente leitura) Contém, em graus, a direção do conteúdo da imagem... Isto é, "para onde a imagem está apontando"&nbsp; |
| **layoutCenterX** | Double | (Somente leitura) Contém onde o CENTRO do token está na imagem no eixo X.&nbsp; Exemplos de valores:&nbsp; 0.5 - O centro do token está no centro da imagem.&nbsp; 1.0 - O centro do token está no canto da direita da imagem.&nbsp; 0.0 - O centro do token está no canto esquerdo da imagem&nbsp; |
| **layoutCenterY** | Double | (Somente leitura) Contém onde o CENTRO do token está na imagem no eixo Y.&nbsp; Exemplos de valores:&nbsp; 0.5 - O centro do token está no centro da imagem.&nbsp; 1.0 - O centro do token está no canto inferior da imagem.&nbsp; 0.0 - O centro do token está no canto superior da imagem&nbsp; |
| **layoutTamX** | Double | (Somente leitura) Contém o tamanho da imagem em relação ao tamanho do token, no eixo X.&nbsp; Exemplos de valores:&nbsp; &nbsp; 1.0 - A largura da imagem é a mesma que a largura do token.&nbsp; 1.5 - A largura da imagem é 1.5x a largura do token&nbsp; 0.5 - A largura da imagem é 0.5x a largura do token.&nbsp; |
| **layoutTamY** | Double | (Somente leitura) Contém o tamanho da imagem em relação ao tamanho do token, no eixo Y.&nbsp; Exemplos de valores:&nbsp; &nbsp; 1.0 - A altura da imagem é a mesma que a altura do token.&nbsp; 1.5 - A altura da imagem é 1.5x a altura do token&nbsp; 0.5 - A altura da imagem é 0.5x a altura do token.&nbsp; |


&nbsp;

&nbsp;

### Métodos

&nbsp;

| **Método** | Descrição |
| --- | --- |
| **sceneUnitClass:isType(typeName)**&nbsp; | Retorna true se passado "sceneUnitClass" como parâmetro. |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Effortlessly upgrade your WinHelp HLP help files to CHM with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
