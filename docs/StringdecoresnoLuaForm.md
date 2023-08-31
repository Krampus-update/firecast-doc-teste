# String de cores no Lua Form

# String de cores

As cores usadas nas tags do Lua Form são definidas por um string, e podem ter 2 formatos:

* &nbsp;
  * Formato hexadecimal
  * Formato literal

&nbsp;

## Formato hexadecimal

As cores no formato hexadecimal são uma mistura de RED, GREEN, BLUE e opcionalmente ALPHA no seguintes formatos:

&nbsp;

### Formato hexadecimal 1 —  dois caracteres por canal de cor

\#RRGGBB ou 0xRRGGBB

\
onde:

* &nbsp;
  * RR - código hexadecimal em 2 caracteres (valor entre 00 e FF) da porção vermelha
  * GG - código hexadecimal em 2 caracteres (valor entre 00 e FF) da porção verde
  * BB - código hexadecimal em 2 caracteres (valor entre 00 e FF) da porção azul

### Formato hexadecimal 2 — dois caracteres por canal de cor + opacidade

Também possível especificar a opacidade da cor (ALPHA), seguindo o padrão:

&nbsp;

\#RRGGBBAA ou 0xRRGGBBAA

&nbsp;

onde:

* &nbsp;
  * RR - código hexadecimal em 2 caracteres (valor entre 00 e FF) da porção vermelha
  * GG - código hexadecimal em 2 caracteres (valor entre 00 e FF) da porção verde
  * BB - código hexadecimal em 2 caracteres (valor entre 00 e FF) da porção azul
  * AA - código hexadecimal em 2 caracteres (valor entre 00 e FF) do valor alpha/opacidade, onde 00 = 100% transparente e FF = 100% opaco.

### Formato hexadecimal 3 — um caracter por canal de cor (também conhecido como shorthand hex color)

\#RGB ou 0xRGB

\
onde:

* &nbsp;
  * R - código hexadecimal em 1 caracter (valor entre 0 e F) da porção vermelha
  * G - código hexadecimal em 1 caracter (valor entre 0 e F) da porção verde
  * B - código hexadecimal em 1 caracter (valor entre 0 e F) da porção azul

### Formato hexadecimal 4 —  um caracter por canal de cor + Opacidade (também conhecido como shorthand hex color)

\#RGBA ou 0xRGBA

&nbsp;

onde:

* &nbsp;
  * R - código hexadecimal em 1 caracter (valor entre 0 e F) da porção vermelha
  * G - código hexadecimal em 1 caracter (valor entre 0 e F) da porção verde
  * B - código hexadecimal em 1 caracter (valor entre 0 e F) da porção azul
  * A - código hexadecimal em 1 caracter (valor entre 0 e F) do valor alpha/opacidade, onde 0 = 100% transparente e F = 100% opaco.

&nbsp;

Exemplos:

* &nbsp;
  * \#FF0000 - cor vermelha (Formato 1 — dois caracteres por canal de cor)
  * \#F00 - cor vemelha (Formato 3 — um caracter por canal de cor)
  * \#00FF00 - cor verde (Formato 1 — dois caracteres por canal de cor)
  * \#0F0 - cor verde (Formato 3 — um caracter por canal de cor)
  * \#0000FF - cor azul (Formato 1 — dois caracteres por canal de cor)
  * \#00F - cor azul (Formato 3 — um caracter por canal de cor)
  * \#FF00007F - cor vermelha 50% transparente (Formato 2 — dois caracteres por canal de cor + opacidade)
  * \#F007 - cor vermelha 47% transparente (Formato 4 — um caracter por canal de cor + opacidade)

&nbsp;

## Formato literal

O SDK3 também provê algumas constantes que identificam facilmente algumas cores\! São elas:

&nbsp;

| **Constante** | **Hexadecimal equivalente** | **Cor** |
| --- | --- | --- |
| AliceBlue  | [\#F0F8FF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F0F8FF>) |   |
| AntiqueWhite  | [\#FAEBD7](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FAEBD7>) |   |
| Aqua  | [\#00FFFF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00FFFF>) |   |
| [Aquamarine](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Aquamarine>)  | [\#7FFFD4](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=7FFFD4>) |   |
| [Azure](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Azure>)  | [\#F0FFFF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F0FFFF>) |   |
| [Beige](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Beige>)  | [\#F5F5DC](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F5F5DC>) |   |
| [Bisque](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Bisque>)  | [\#FFE4C4](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFE4C4>) |   |
| [Black](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Black>)  | [\#000000](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=000000>) |   |
| [BlanchedAlmond](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=BlanchedAlmond>)  | [\#FFEBCD](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFEBCD>) |   |
| [Blue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Blue>)  | [\#0000FF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=0000FF>) |   |
| [BlueViolet](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=BlueViolet>)  | [\#8A2BE2](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=8A2BE2>) |   |
| [Brown](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Brown>)  | [\#A52A2A](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=A52A2A>) |   |
| [BurlyWood](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=BurlyWood>)  | [\#DEB887](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DEB887>) |   |
| [CadetBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=CadetBlue>)  | [\#5F9EA0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=5F9EA0>) |   |
| [Chartreuse](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Chartreuse>)  | [\#7FFF00](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=7FFF00>) |   |
| [Chocolate](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Chocolate>)  | [\#D2691E](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=D2691E>) |   |
| [Coral](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Coral>)  | [\#FF7F50](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF7F50>) |   |
| [CornflowerBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=CornflowerBlue>)  | [\#6495ED](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=6495ED>) |   |
| [Cornsilk](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Cornsilk>)  | [\#FFF8DC](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFF8DC>) |   |
| [Crimson](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Crimson>)  | [\#DC143C](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DC143C>) |   |
| [Cyan](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Cyan>)  | [\#00FFFF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00FFFF>) |   |
| [DarkBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkBlue>)  | [\#00008B](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00008B>) |   |
| [DarkCyan](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkCyan>)  | [\#008B8B](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=008B8B>) |   |
| [DarkGoldenRod](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkGoldenRod>)  | [\#B8860B](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=B8860B>) |   |
| [DarkGray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkGray>)  | [\#A9A9A9](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=A9A9A9>) |   |
| [DarkGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkGreen>)  | [\#006400](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=006400>) |   |
| [DarkKhaki](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkKhaki>)  | [\#BDB76B](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=BDB76B>) |   |
| [DarkMagenta](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkMagenta>)  | [\#8B008B](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=8B008B>) |   |
| [DarkOliveGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkOliveGreen>)  | [\#556B2F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=556B2F>) |   |
| [DarkOrange](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkOrange>)  | [\#FF8C00](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF8C00>) |   |
| [DarkOrchid](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkOrchid>)  | [\#9932CC](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=9932CC>) |   |
| [DarkRed](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkRed>)  | [\#8B0000](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=8B0000>) |   |
| [DarkSalmon](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkSalmon>)  | [\#E9967A](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=E9967A>) |   |
| [DarkSeaGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkSeaGreen>)  | [\#8FBC8F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=8FBC8F>) |   |
| [DarkSlateBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkSlateBlue>)  | [\#483D8B](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=483D8B>) |   |
| [DarkSlateGray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkSlateGray>)  | [\#2F4F4F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=2F4F4F>) |   |
| [DarkTurquoise](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkTurquoise>)  | [\#00CED1](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00CED1>) |   |
| [DarkViolet](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DarkViolet>)  | [\#9400D3](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=9400D3>) |   |
| [DeepPink](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DeepPink>)  | [\#FF1493](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF1493>) |   |
| [DeepSkyBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DeepSkyBlue>)  | [\#00BFFF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00BFFF>) |   |
| [DimGray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DimGray>)  | [\#696969](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=696969>) |   |
| [DodgerBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=DodgerBlue>)  | [\#1E90FF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=1E90FF>) |   |
| [FireBrick](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=FireBrick>)  | [\#B22222](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=B22222>) |   |
| [FloralWhite](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=FloralWhite>)  | [\#FFFAF0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFAF0>) |   |
| [ForestGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=ForestGreen>)  | [\#228B22](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=228B22>) |   |
| [Fuchsia](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Fuchsia>)  | [\#FF00FF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF00FF>) |   |
| [Gainsboro](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Gainsboro>)  | [\#DCDCDC](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DCDCDC>) |   |
| [GhostWhite](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=GhostWhite>)  | [\#F8F8FF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F8F8FF>) |   |
| [Gold](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Gold>)  | [\#FFD700](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFD700>) |   |
| [GoldenRod](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=GoldenRod>)  | [\#DAA520](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DAA520>) |   |
| [Gray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Gray>)  | [\#808080](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=808080>) |   |
| [Green](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Green>)  | [\#008000](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=008000>) |   |
| [GreenYellow](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=GreenYellow>)  | [\#ADFF2F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=ADFF2F>) |   |
| [HoneyDew](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=HoneyDew>)  | [\#F0FFF0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F0FFF0>) |   |
| [HotPink](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=HotPink>)  | [\#FF69B4](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF69B4>) |   |
| [IndianRed ](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=IndianRed>)  | [\#CD5C5C](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=CD5C5C>) |   |
| [Indigo ](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Indigo>)  | [\#4B0082](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=4B0082>) |   |
| [Ivory](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Ivory>)  | [\#FFFFF0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFFF0>) |   |
| [Khaki](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Khaki>)  | [\#F0E68C](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F0E68C>) |   |
| [Lavender](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Lavender>)  | [\#E6E6FA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=E6E6FA>) |   |
| [LavenderBlush](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LavenderBlush>)  | [\#FFF0F5](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFF0F5>) |   |
| [LawnGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LawnGreen>)  | [\#7CFC00](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=7CFC00>) |   |
| [LemonChiffon](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LemonChiffon>)  | [\#FFFACD](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFACD>) |   |
| [LightBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightBlue>)  | [\#ADD8E6](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=ADD8E6>) |   |
| [LightCoral](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightCoral>)  | [\#F08080](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F08080>) |   |
| [LightCyan](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightCyan>)  | [\#E0FFFF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=E0FFFF>) |   |
| [LightGoldenRodYellow](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightGoldenRodYellow>)  | [\#FAFAD2](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FAFAD2>) |   |
| [LightGray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightGray>)  | [\#D3D3D3](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=D3D3D3>) |   |
| [LightGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightGreen>)  | [\#90EE90](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=90EE90>) |   |
| [LightPink](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightPink>)  | [\#FFB6C1](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFB6C1>) |   |
| [LightSalmon](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightSalmon>)  | [\#FFA07A](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFA07A>) |   |
| [LightSeaGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightSeaGreen>)  | [\#20B2AA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=20B2AA>) |   |
| [LightSkyBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightSkyBlue>)  | [\#87CEFA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=87CEFA>) |   |
| [LightSlateGray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightSlateGray>)  | [\#778899](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=778899>) |   |
| [LightSteelBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightSteelBlue>)  | [\#B0C4DE](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=B0C4DE>) |   |
| [LightYellow](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LightYellow>)  | [\#FFFFE0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFFE0>) |   |
| [Lime](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Lime>)  | [\#00FF00](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00FF00>) |   |
| [LimeGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=LimeGreen>)  | [\#32CD32](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=32CD32>) |   |
| [Linen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Linen>)  | [\#FAF0E6](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FAF0E6>) |   |
| [Magenta](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Magenta>)  | [\#FF00FF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF00FF>) |   |
| [Maroon](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Maroon>)  | [\#800000](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=800000>) |   |
| [MediumAquaMarine](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumAquaMarine>)  | [\#66CDAA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=66CDAA>) |   |
| [MediumBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumBlue>)  | [\#0000CD](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=0000CD>) |   |
| [MediumOrchid](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumOrchid>)  | [\#BA55D3](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=BA55D3>) |   |
| [MediumPurple](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumPurple>)  | [\#9370DB](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=9370DB>) |   |
| [MediumSeaGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumSeaGreen>)  | [\#3CB371](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=3CB371>) |   |
| [MediumSlateBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumSlateBlue>)  | [\#7B68EE](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=7B68EE>) |   |
| [MediumSpringGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumSpringGreen>)  | [\#00FA9A](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00FA9A>) |   |
| [MediumTurquoise](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumTurquoise>)  | [\#48D1CC](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=48D1CC>) |   |
| [MediumVioletRed](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MediumVioletRed>)  | [\#C71585](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=C71585>) |   |
| [MidnightBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MidnightBlue>)  | [\#191970](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=191970>) |   |
| [MintCream](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MintCream>)  | [\#F5FFFA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F5FFFA>) |   |
| [MistyRose](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=MistyRose>)  | [\#FFE4E1](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFE4E1>) |   |
| [Moccasin](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Moccasin>)  | [\#FFE4B5](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFE4B5>) |   |
| [NavajoWhite](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=NavajoWhite>)  | [\#FFDEAD](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFDEAD>) |   |
| [Navy](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Navy>)  | [\#000080](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=000080>) |   |
| [OldLace](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=OldLace>)  | [\#FDF5E6](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FDF5E6>) |   |
| [Olive](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Olive>)  | [\#808000](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=808000>) |   |
| [OliveDrab](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=OliveDrab>)  | [\#6B8E23](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=6B8E23>) |   |
| [Orange](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Orange>)  | [\#FFA500](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFA500>) |   |
| [OrangeRed](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=OrangeRed>)  | [\#FF4500](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF4500>) |   |
| [Orchid](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Orchid>)  | [\#DA70D6](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DA70D6>) |   |
| [PaleGoldenRod](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PaleGoldenRod>)  | [\#EEE8AA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=EEE8AA>) |   |
| [PaleGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PaleGreen>)  | [\#98FB98](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=98FB98>) |   |
| [PaleTurquoise](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PaleTurquoise>)  | [\#AFEEEE](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=AFEEEE>) |   |
| [PaleVioletRed](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PaleVioletRed>)  | [\#DB7093](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DB7093>) |   |
| [PapayaWhip](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PapayaWhip>)  | [\#FFEFD5](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFEFD5>) |   |
| [PeachPuff](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PeachPuff>)  | [\#FFDAB9](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFDAB9>) |   |
| [Peru](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Peru>)  | [\#CD853F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=CD853F>) |   |
| [Pink](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Pink>)  | [\#FFC0CB](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFC0CB>) |   |
| [Plum](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Plum>)  | [\#DDA0DD](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=DDA0DD>) |   |
| [PowderBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=PowderBlue>)  | [\#B0E0E6](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=B0E0E6>) |   |
| [Purple](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Purple>)  | [\#800080](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=800080>) |   |
| [RebeccaPurple](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=RebeccaPurple>)  | [\#663399](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=663399>) |   |
| [Red](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Red>)  | [\#FF0000](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF0000>) |   |
| [RosyBrown](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=RosyBrown>)  | [\#BC8F8F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=BC8F8F>) |   |
| [RoyalBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=RoyalBlue>)  | [\#4169E1](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=4169E1>) |   |
| [SaddleBrown](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SaddleBrown>)  | [\#8B4513](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=8B4513>) |   |
| [Salmon](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Salmon>)  | [\#FA8072](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FA8072>) |   |
| [SandyBrown](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SandyBrown>)  | [\#F4A460](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F4A460>) |   |
| [SeaGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SeaGreen>)  | [\#2E8B57](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=2E8B57>) |   |
| [SeaShell](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SeaShell>)  | [\#FFF5EE](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFF5EE>) |   |
| [Sienna](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Sienna>)  | [\#A0522D](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=A0522D>) |   |
| [Silver](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Silver>)  | [\#C0C0C0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=C0C0C0>) |   |
| [SkyBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SkyBlue>)  | [\#87CEEB](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=87CEEB>) |   |
| [SlateBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SlateBlue>)  | [\#6A5ACD](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=6A5ACD>) |   |
| [SlateGray](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SlateGray>)  | [\#708090](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=708090>) |   |
| [Snow](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Snow>)  | [\#FFFAFA](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFAFA>) |   |
| [SpringGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SpringGreen>)  | [\#00FF7F](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=00FF7F>) |   |
| [SteelBlue](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=SteelBlue>)  | [\#4682B4](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=4682B4>) |   |
| [Tan](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Tan>)  | [\#D2B48C](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=D2B48C>) |   |
| [Teal](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Teal>)  | [\#008080](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=008080>) |   |
| [Thistle](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Thistle>)  | [\#D8BFD8](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=D8BFD8>) |   |
| [Tomato](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Tomato>)  | [\#FF6347](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FF6347>) |   |
| [Turquoise](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Turquoise>)  | [\#40E0D0](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=40E0D0>) |   |
| [Violet](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Violet>)  | [\#EE82EE](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=EE82EE>) |   |
| [Wheat](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Wheat>)  | [\#F5DEB3](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F5DEB3>) |   |
| [White](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=White>)  | [\#FFFFFF](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFFFF>) |   |
| [WhiteSmoke](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=WhiteSmoke>)  | [\#F5F5F5](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=F5F5F5>) |   |
| [Yellow](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=Yellow>)  | [\#FFFF00](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=FFFF00>) |   |
| [YellowGreen](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?color=YellowGreen>)  | [\#9ACD32](<http://www.w3schools.com/tags/ref\_color\_tryit.asp?hex=9ACD32>) |   |
| None  | \#00000000 | &nbsp; |
| Transparent | \#00000000 | &nbsp; |
| Null | \#00000000 | &nbsp; |


&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Experience the power of a responsive website for your documentation](<https://www.helpndoc.com/feature-tour/produce-html-websites/>)_
