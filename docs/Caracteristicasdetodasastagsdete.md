# Características de todas as tags de textos

# Características de todas as tags de textos

O SDK3 utiliza o conceito de orientação a objetos nos componentes visuais e alguns controles são controles de texto (Exemplos: **button**, **label**, **edit**).

## Herança

As tags de textos possuem **todas** as características de um controle qualquer. Veja [Características de todas as tags visuais](<Caracteristicasdetodasastagsvisu.md>)**.**

## Características

Além das características herdadas, todas as tags textos também possuem as seguintes características:

### Propriedades e Atributos

&nbsp;

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **text** | String | \<string vazio\> | Define o texto que será exibido no controle. |
| **fontColor** | String contendo uma cor&nbsp; | Em temas escuros, uma cor clara.&nbsp; Em temas claros, uma cor escura. | Define a cor do texto.&nbsp; Exemplos: Black White #FDFDFD&nbsp; Veja [String de cores no Lua Form](<StringdecoresnoLuaForm.md>) para obter a completa de cores e outras formas de uso. |
| **fontFamily** | String | \<Varia de Plataforma para Plataforma\> | Define a fonte que será usada nos textos.&nbsp; As fontes disponíveis variam de plataforma para plataforma (Android, iOS, Windows, etc..) |
| **fontSize** | Float | &#49;3.0 | Define o tamanho da fonte.&nbsp; |
| **fontStyle** | Conjunto de: “bold” “italic” “underline” “strikeout” | “” | Define o estilo da fonte...&nbsp; Exemplos: “bold” “bold italic” “italic underline bold” “”&nbsp; |
| **horzTextAlign** | Enumerado: “leading” “center” “trailing” | “leading” | Define o alinhamento horizontal do texto, onde: “leading” – alinhado à esquerda “center”- centralizado “trailing” – alinhado à direita&nbsp; |
| **vertTextAlign** | Enumerado: “leading” “center” “trailing” | “center” | Define o alinhamento vertical do texto, onde: “leading” – alinhado ao topo. “center”- centralizado “trailing” – alinhado ao rodapé.&nbsp; |
| **wordWrap** | Boolean | false | True = Quebra de linha automática quando o tamanho do texto ultrapassar a largura do controle&nbsp; False = Limitar o texto em apenas uma linha, mesmo que ultrapasse a largura do controle.&nbsp; |
| **textTrimming** | Enumerado: “none” “character” “word” | \<Varia de controle para controle\> | Quando o tamanho do texto ultrapassa a largura do controle, o que acontece com o texto?&nbsp; none&nbsp; - Nenhum tratamento especial, o desenho do texto será truncado de forma “cara-crachá” character – o caractere mais perto da linha de corte será substituído pelo símbolo “...” word – a palavra que estiver mais perto da linha de corte será substituída pelo símbolo “...”&nbsp; |


&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Experience the Power and Simplicity of HelpNDoc's User Interface](<https://www.helpndoc.com/feature-tour/stunning-user-interface/>)_
