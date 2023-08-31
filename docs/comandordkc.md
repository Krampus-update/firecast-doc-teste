# comando "rdk c"

Este comando compila o diretório corrente e empacota todo o conteúdo em um único arquivo de extensão ‘.rpk’ em “\<DiretorioCorrente\>\\output\\\<NomeDoModulo\>.rpk”

&nbsp; &nbsp; Observações:

* O comando percorre todos os arquivos de extensão “lfm” e gera arquivos de extensão “lua” equivalentes.
* O comando realiza validações antes de empacotar o conteúdo do diretório, como:
  * O arquivo “module.xml” deve existir e estar preenchido corretamente ([O arquivo “module.xml”](<Oarquivomodulexml.md>)**)** .
  * Os arquivos de extensão “lua” devem estar sintaticamente corretos.
  * Os arquivos de extensão “lfm” devem estar sintaticamente corretos, e possuir tags e atributos válidos.
* Os arquivos e subdiretórios de nomes iniciados com dois underlines (“\_\_”) e o diretório “output” são ignorados por este comando.&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Transform Your CHM Help File Creation Process with HelpNDoc](<https://www.helpndoc.com/feature-tour/create-chm-help-files/>)_
