# Objeto InertialMovement

# Objeto InertialMovement

Este objeto é responsável por calcular movimentos inerciais em janelas e scrolls de janela. Movimento Inercial é aquele movimento produzido quando você "joga" o dedo numa tela touchscreen e a tela continua "scrollando" por conta própria.

&nbsp;

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| **active** | Boolean | Define se o objeto está ativo ou não. Seu valor padrão é **true** e quando for **false** não invoca eventos.&nbsp; |
| **animated** | Boolean | **true** - O objeto irá calcular movimentações inerciais&nbsp; **false** - O objeto não irá calcular movimentações inerciais.&nbsp; Valor padrão: true&nbsp; |
| **decelerationRate** | Double | Um número que define a desaceleração do movimento inercial.&nbsp; O valor padrão é 5.75 e quanto maior este número, mais rápido o movimento inercial chega ao fim.&nbsp; |


&nbsp;

&nbsp;

### Métodos

| **Método** | Descrição |
| --- | --- |
| **inertialMov:setPos(x, y)** | Define onde se encontra a posição do item/scroll.&nbsp; Parâmetros: x - um número contendo a posição no eixo X. y - um número contendo a posição no eixo Y.&nbsp; |
| **inertialMov:getPos()** | Retorna onde está a posição atual do item/scroll.&nbsp; Retorna: Dois números, o primeiro contendo a posição no eixo X e o segundo contendo a posição no eixo Y.&nbsp; Exemplo de uso: local posX, posY = inertialMov:getPos();&nbsp; |
| **inertialMov:setBounds(minX, minY, maxX, maxY)** | Define os limites de posição do item/scroll.&nbsp; Parâmetros: minX - Posição mínima no eixo X minY - Posição mínima no eixo Y maxX - Posição máxima no eixo X maxY - Posição máxima no eixo Y&nbsp; |
| **inertialMov:pointerDown(x, y)** | Invoque este método quando o mouse/touch for pressionado em algum lugar.&nbsp; Parâmetros: x - um número contendo a posição no eixo X do clique/toque. y - um número contendo a posição no eixo Y do clique/toque.&nbsp; |
| **inertialMov:pointerMove(x, y)** | Invoque este método quando o mouse/touch se mover pela tela.&nbsp; Parâmetros: x - um número contendo a NOVA posição no eixo X do mouse/dedo. y - um número contendo a NOVA posição no eixo Y do mouse/dedo.&nbsp; |
| **inertialMov:pointerUp(x, y)** | Invoque este método quando o botão do mouse for solto/quando o dedo soltar da tela.&nbsp; Parâmetros: x - um número contendo a onde no eixo X o mouse/toque foi liberado. y - um número contendo a onde no eixo Y o mouse/toque foi liberado.&nbsp; |
| **inertialMov:pointerLeave()** | Invoque este método quando o mouse/toque sair dos limites do controle da tela.&nbsp; |
| **inertialMov:pointerWheel(deltaX, deltaY)** | Invoque este método quando o usuário rolar a rodinha do mouse.&nbsp; Parâmetros: deltaX - um número contendo a variação do eixo X, isto é, o quanto se pretende scrollar no eixo X. deltaY - um número contendo a variação do eixo Y, isto é, o quanto se pretende scrollar no eixo Y.&nbsp; |


&nbsp;

&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onChange** | Este evento é invocado quando o objeto possuir novas coordenadas para seu item/scroll.&nbsp; Utilize o método "getPos" para descobrir a nova posição.&nbsp; |


&nbsp;

## Exemplos

***
_Created with the Personal Edition of HelpNDoc: [Easily create PDF Help documents](<https://www.helpndoc.com/feature-tour>)_
