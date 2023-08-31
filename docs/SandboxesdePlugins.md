# Sandboxes de Plug-ins

# Sandboxes de plug-ins

&nbsp;

O SDK3 utiliza sandboxes para a execução de plug-ins. Suas principais características são:

* &nbsp;
  * Um sandbox é um ambiente virtual que representa um plug-in em execução. São instanciados/criados quando o Firecast se inicia (e na instalação de plug-ins) e são destruídos quando o Firecast é fechado (ou na desinstalação de plug-ins).&nbsp;
  * Cada plug-in roda em sua própria sandbox.
  * Os sandboxes restringem o código dos plug-ins a fim de proteger o computador/dispositivo do usuário de acessos indevidos.&nbsp;
  * Cada plug-in está associado com seu próprio “[HD virtual](<HDVirtual.md>)”.
    * Cada sandbox enxerga APENAS o “HD virtual” do plugin que está em execução.
    * **Não** é possível acessar arquivos que estão fora do “HD virtual”
    * Os arquivos do “HD virtual” são persistentes, isto é, ficam salvos mesmo quando o sandbox é destruído.
    * Um sandbox **não** consegue acessar o “HD virtual” de outro sandbox.
    * Um sandbox **não** consegue acessar o “HD virtual” de outro plugin.
    * O conteúdo do “HD virtual” é perdido quando o plugin é desinstalado.
    * Saiba mais lendo o tópico [HD Virtual](<HDVirtual.md>).
  * Os objetos, tabelas e variáveis vivem isolados. Isto é, um sandbox não enxerga as variáveis e tabelas Lua de outro sandbox.
  * Os objetos, tabelas e variáveis de cada sandbox **não** são persistentes. Isto é, estas informações são perdidas quando o sandbox é destruído.
  * Durante o carregamento de uma sandbox, todos os arquivos de extensão “lua” do plug-in são automaticamente carregados.
    * Se existir o arquivo "/init.lua" na raiz do plugin, ele é carregado primeiro.
    * A ordem de carregamento dos demais arquivos respeita o uso da função “require”.
    * Observação: A tabela global Lua é compartilhada com todos os arquivos Lua do plug-in. Logo, um arquivo Lua enxerga as variáveis e tabelas de outro arquivo LUA (se o modificador “local” não for usado).
    * Apenas arquivos “lua” que estão na [pasta projeto do plug-in](<ProjetosdePlugin.md>) são carregados automaticamente.

&nbsp;

Por segurança, o sandbox oferece **APENAS** as seguintes funções nativas LUA:

* &nbsp;
  * Variáveis:
    * *\_G*
    * *&nbsp;\_VERSION*
  * Funções:
    * *next*
    * *pairs*
    * *ipairs*
    * *pcall*
    * *select*
    * *tonumber*
    * *tostring*
    * *type*
    * *unpack*
    * *xpcall*
    * *collectgarbage*
    * *assert*
    * *error*
    * *load*
    * *rawget*
    * *rawset*
    * *rawequal*
    * *setmetatable*
    * *getmetatable*
    * *require*
  * Biblioteca String
    * *string.byte*
    * *string.char*
    * *string.find*
    * *string.format*
    * *string.gmatch*
    * *string.gsub*
    * *string.len*
    * *string.lower*
    * *string.match*
    * *string.rep*
    * *string.reverse*
    * *string.sub*
    * *string.upper*
  * Biblioteca Table
    * *table.insert*
    * *table.maxn*
    * *table.remove*
    * *table.sort*
    * *table.concat*
    * *table.pack*
    * *table.unpack*
  * Biblioteca Math
    * *math.abs*
    * *math.acos*
    * *math.asin*
    * *math.atan*
    * *math.ceil*
    * *math.cos*
    * *math.deg*
    * *math.exp*
    * *math.floor*
    * *math.fmod*
    * *math.huge*
    * *math.log*
    * *math.log10*
    * *math.max*
    * *math.min*
    * *math.maxinteger*
    * *math.mininteger*
    * *math.modf*
    * *math.pi*
    * *math.rad*
    * *math.random*
    * *math.randomseed*
    * *math.sin*
    * *math.sqrt*
    * *math.tan*
    * *math.tointeger*
    * *math.type*
    * *math.ult*
  * Biblioteca debug
    * *debug.getmetatable*
    * *debug.setmetatable*
    * *debug.traceback*
  * Biblioteca OS
    * *os.clock*
    * *os.difftime*
    * *os.time*
    * *os.date*
  * Biblioteca Package
    * *package.loaded*
    * *package.config*
  * *Biblioteca coroutine*
    * *coroutine.create*
    * *coroutine.resume*
    * *coroutine.running*
    * *coroutine.status*
    * *coroutine.wrap*
    * *coroutine.yield*
  * *Biblioteca utf8*
    * *utf8.char*
    * *utf8.charpattern*
    * *utf8.codes*
    * *utf8.codepoint*
    * *utf8.len*
    * *utf8.offset*

## Veja também:

&nbsp; &nbsp; O SDK3 já provê algumas bibliotecas e funções LUA para você utilizar em seus plug-ins\! Saiba mais em [Bibliotecas LUA](<BibliotecasLUA.md>).

***
_Created with the Personal Edition of HelpNDoc: [Add an Extra Layer of Security to Your PDFs with Encryption](<https://www.helpndoc.com/step-by-step-guides/how-to-generate-an-encrypted-password-protected-pdf-document/>)_
