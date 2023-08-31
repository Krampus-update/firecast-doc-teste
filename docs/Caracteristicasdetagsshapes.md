# Características de tags shapes

# Características de tags do tipo shape/forma

O SDK3 utiliza o conceito de orientação a objetos nos componentes visuais e alguns controles são controles shape (Exemplos: **rectangle**, **horzLine**, **etc..**).

## Herança

As tags shapes possuem **todas** as características de um controle qualquer. Veja [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

## Características

Além das características herdadas, todas as tags shapes também possuem as seguintes características:

### Propriedades e Atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **color** | String contendo uma cor | "silver" | Define a cor do conteúdo da forma.&nbsp; Veja [String de cores no Lua Form](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso.&nbsp; |
| **strokeColor** | String contendo uma cor | "black" | Define a cor das linhas da borda.&nbsp; Veja [String de cores no Lua Form](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso.&nbsp; |
| **strokeSize** | Float | &#48;.0 | Define a espessura das linhas da borda.&nbsp; |
| **strokeCap** | Enumerado: "flat" "round" | "flat" | Define o estilo gráfico usado ao desenhar o fim das linhas.&nbsp; "flat" - linhas com pontas retangulares "round" - linhas com pontas arredondadas.&nbsp; |
| **strokeJoin** | Enumerado: "miter" "round" "bevel" | "miter" | Define o estilo gráfico usado ao juntar segmentos de linha em uma forma.&nbsp; "miter" - As quinas/junções são "quadradas".&nbsp; "round" - As quinas/junções são arredondadas.&nbsp; "bevel" - As quintas/junções são ligadas de forma diagonal.&nbsp; |
| **strokeDash** | Enumerado: "solid" "dash" "dot" "dashDot" "dashDotDot" | "solid" | Define o estilo gráfico da linha.&nbsp; "solid" - A linha é sólida&nbsp; "dash" - A linha é tracejada&nbsp; "dot" - A linha é feita de pontos.&nbsp; "dashDot" - A linha é alternada entre traços e pontos.&nbsp; "dashDotDot" - A linha é alternada entre traço, ponto e ponto.&nbsp; |



***
_Created with the Personal Edition of HelpNDoc: [Transform your help documentation into a stunning website](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
