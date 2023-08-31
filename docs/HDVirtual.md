# HD Virtual

# HD Virtual

Cada plug-in possui seu próprio HD Virtual

## Principais características do HD Virtual

* Cada plugin possui um HD Virtual. Um plug-in **não** acessa o conteúdo do HD virtual de outro plug-in.
* Os plug-ins **não** conseguem acessar arquivos que estão fora de seu “HD Virtual” diretamente. Isto significa que o plugin não enxerga o drive de armazenamento real do dispositivo em que está rodando. A única forma do plug-in conseguir acessar arquivos no HD do usuário é através das funlções [dialogs.openFile](<BibliotecaDialogs.md#dialogs.openFile>) e [dialogs.saveFile](<BibliotecaDialogs.md#dialogs.saveFile>)
* Os arquivos do “HD virtual” são persistentes, isto é, ficam salvos mesmo quando o dispositivo é desligado.
* O conteúdo do “HD virtual” é perdido quando seu plug-in é desinstalado.
* Ao instalar uma um plug-in o conteúdo original do arquivo .rpk não é extraído no HD físico do dispostivio. Arquivos que forem criados durante a execução do plugin são salvos no HD físico do usuário. O [VHD (HD Virtual)](<HDVirtual.md>) do plugin é composto pela união lógica do conteúdo do arquivo .rpk + arquivos que foram criados durante a execução. O Firecast faz essa união lógica automaticamente de forma transparente para que o programador não precise se preocupar.
* Todos os arquivos originais do plug-in (aqueles que estão contidos na pasta projeto do plug-in) ficam no modo somente-leitura. Não é possível apagar e nem alterá-los.
* Ao instalar uma nova versão de plugin, os arquivos que foram criados durante execução do módulo são preservados.

&nbsp;

## Sobre o sistema de arquivos no HD Virtual

* O caractere separador de diretórios é “/”
* A raiz do HD virtual é o diretório “/”
* Os nomes de arquivos e pastas são case-sensitives, isto é, letras maiúsculas são diferentes das mesmas letras em sua forma minúscula. (Exemplo: “/arquivo.lua” e “/Arquivo.lua” são dois arquivos distintos)

&nbsp;

&nbsp;

## Manipulando o HD Virtual:

Para manipular o HD Virtual, o SDK3 [provê a biblioteca "VHD"](<BibliotecaVHD.md>) .


***
_Created with the Personal Edition of HelpNDoc: [Bring your WinHelp HLP help files into the present with HelpNDoc's easy CHM conversion](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
