# Ponto Lógico vs Pixel

# Ponto Lógico vs Pixel

Todas as dimensões ligadas à interface do Lua Form são medidas em pontos lógicos ao invés de pixels.

## O que é um ponto lógico?

Ponto lógico é um "pixel virtual" que você deve usar quando estiver definindo as interfaces visuais para expressar tamanho ou posição de forma independente da **densidade da tela** dos dispositivos.

## O que é densidade da tela?

Representa a quantidade de pixels dentro de uma área física da tela de um dispositivo. A densidade é comumente medida em ppi (points per inch - pontos por polegada).

&nbsp;

Telas de alta densidade possuem mais pixels em uma área (uma polegada² ou centímetro², por exemplo) do que uma tela de menor densidade em uma mesma área. Quanto maior a densidade de pixels, mais definida e "bonita" é a tela.

Um monitor LED padrão de computador desktop possui por volta de 100ppi, um celular Motorolla Moto G possui 326ppi

## A quanto equivale um ponto lógico?

O valor real de um ponto lógico varia de dispositivo para dispositivo, conforme sua densidade de pixels.

&nbsp;

| **Densidade de Pixels** | Equivalência | Exemplos de dispositivos |
| --- | --- | --- |
| **Interface de baixa densidade de pixels.** | &#49; ponto lógico = 0,75 pixels | Celulares Androids de baixa densidade de pixels.&nbsp; |
| **Interface de média densidade de pixels.**&nbsp; | &#49; ponto lógico = 1 pixel | Computadores padrões, dispositivos iOS sem retina. |
| **Interface de alta densidade de pixels.** | &#49; ponto lógico = 1,5 pixels | Computadores configurados para textos ampliados, celulares Androids de alta resolução (Moto G ou Zenfone, por exemplo).&nbsp; |
| **Interface de altíssima densidade de pixels.** | &#49; ponto lógico = 2 pixels | Google Nexus 7, dispositivos iOS com retina.&nbsp; |
| **Interface de super densidade de pixels.**&nbsp; | &#49; ponto lógico = 3 pixels | Google Nexus 5, Galaxy S4. |


&nbsp;

## O que isso tudo significa?

Que o SDK 3 lida automaticamente com as diferentes densidades de telas automaticamente para você.&nbsp;

Normalmente você pode definir sua interface sem preocupações como se 1 ponto lógico equivalesse a 1 pixel.&nbsp;

&nbsp;

## Arquivo de imagens e pontos lógicos.

Os arquivos de imagens (.png, jpg, bmp, etc..) possuem dimensões medidas em pixels. Ao usar estas imagens em uma interface medida em pontos lógicos, o SDK3 poderá automaticamente fazer conversões de tamanho para você.

&nbsp;

Exemplo: O comportamento de uma imagem de 64x64 pixels usada em uma [tag image](<Tagimage.md>) de largura 64 e altura 64, será diferente para cada densidade de pixels:

&nbsp;

| Equivalência | Comportamento |
| --- | --- |
| **&#49; ponto lógico = 0,75 pixels** | A imagem será reduzida para 48x48 pixels antes de ser desenhada.&nbsp; |
| **&#49; ponto lógico = 1 pixel** | A imagem será desenhada como é, sem escala.&nbsp; |
| **&#49; ponto lógico = 1,5 pixels** | A imagem será ampliada para 96x96 pixels antes de ser desenhada.&nbsp; |
| **&#49; ponto lógico = 2 pixels** | A imagem será ampliada para 128x128 pixels antes de ser desenhada.&nbsp; |
| **&#49; ponto lógico = 3 pixels** | A imagem será ampliada para 192x192 pixels antes de ser desenhada.&nbsp; |



***
_Created with the Personal Edition of HelpNDoc: [Elevate Your Help Documentation with a Help Authoring Tool](<https://www.helpauthoringsoftware.com/articles/what-is-a-help-authoring-tool/>)_
