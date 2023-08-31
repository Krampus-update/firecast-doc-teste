# Objeto SceneDrawingOpText

# Objeto SceneDrawingOpText

O Objeto SceneDrawingOpText representa uma operação gráfica de um texto em um [SceneCanvas](<ObjetoSceneCanvas.md>) .

## Herança

O o**bjeto SceneDrawingOpText** herda de [SceneDrawingOp](<ObjetoSceneDrawingOp.md>) e possui também **TODAS** todas as suas características.

&nbsp;

Veja também:

* &nbsp;
  * [Objeto SceneDrawingOp](<ObjetoSceneDrawingOp.md>)
  * [Objecto SceneBaseObject](<ObjetoSceneBaseObject.md>)

&nbsp;

## Características

Além das características herdadas, o objeto SceneDrawingOpText também possui as seguintes características:

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **objectType** | String "opText" | (Somente Leitura) Contém um texto que identifica o tipo da operação gráfica - "opBitmap".&nbsp; |
| **text** | String | O texto a ser desenhado no canvas.&nbsp; |
| **color** | [String de Cor](<StringdecoresnoLuaForm.md>) | Define a cor do texto.&nbsp; Veja [String de cores](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso.&nbsp; Valor padrão: Black.&nbsp; |
| **fontStyle** | Uma tabela contendo de um ou mais dos seguintes valores: "bold" "italic" "underline" "strikeout"&nbsp; | Define o estilo que será aplicado ao texto e pode ser a combinação de 0 ou mais dos seguintes valores:&nbsp; "bold" - Texto negrito&nbsp; "italic" - Texto em itálico&nbsp; "underline" - Texto com underline.&nbsp; "strikeout" - Texto tachado.&nbsp; Exemplos: {} - (Valor padrão) {"bold", "italic"} -&nbsp; (negrito e itálico) {"bold"} - (apenas negrito)&nbsp; |
| **horzTextAlign** | Enumerado: "leading" "center" "trailing" | Define como será o alinhamento horizontal do texto.&nbsp; "leading" - Alinhado à esquerda&nbsp; "center" - Alinhado ao centro&nbsp; "trailing" - Alinhado à direita&nbsp; Valor padrão: "leading"&nbsp; |
| **vertTextAlign** | Enumerado: "leading" "center" "trailing" | Define como será o alinhamento vertical do texto.&nbsp; "leading" - Alinhado ao topo.&nbsp; "center" - Alinhado ao centro&nbsp; "trailing" - Alinhado ao fundo.&nbsp; Valor padrão: "center".&nbsp; |
| **aspect** | Double | (Somente Leitura) Retorna o aspecto do conteúdo do texto, isto é, a divisão entre a largura do texto por sua altura.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |
| &nbsp; | &nbsp; |


&nbsp;

## Exemplos

***
_Created with the Personal Edition of HelpNDoc: [Ensure High-Quality Documentation with HelpNDoc's Hyperlink and Library Item Reports](<https://www.helpndoc.com/feature-tour/advanced-project-analyzer/>)_
