# Criar um modelo de ficha à partir de um PDF

# Criar um modelo de ficha à partir de um PDF editável

&nbsp;

&nbsp;

1. Você deve ter um projeto de plug-in já criado. Se você ainda não tem um projeto de plug-in, leia&nbsp; "[Criando um novo projeto de plug-in](<Criandoumnovoprojetodeplugin.md>)" e crie o seu antes (é bem fácil =\] )\
\
&nbsp;
1. Abra o prompt de comando e navegue até a pasta de seu projeto de plug-in.

&nbsp;

![Image](<lib/NewItem40.png>)\
&nbsp;

&nbsp;

1. Execute o [comando "rdk pdf"](<comandordkpdf.md>) sem áspas no prompt de comando\
&nbsp;

![Image](<lib/NewItem163.png>)\
&nbsp;

&nbsp;

Uma página como esta se abrirá no navegador de internet (Sempre utilize um browser mais atualizado. Experimente o Google Chrome):\
\
![Image](<lib/NewItem165.png>)

\
&nbsp;

1. Clique em "escolher arquivo" e selecione o PDF que deseja converter.

&nbsp;

![Image](<lib/NewItem166.png>)

&nbsp;

1. Se o Zoom padrão de 1,5x deixar o conteúdo muito pequeno, escolha outro valor de escala que melhor se encaixar em seu PDF e clique em "Aplicar Configurações". Experimente outras configurações também\!

![Image](<lib/NewItem167.png>)\
\
&nbsp;

1. Clique em "salvar todas as páginas". Um arquivo ".zip" que contém o PDF em formato .SVG será gerado\!

![Image](<lib/NewItem169.png>)

&nbsp;

&nbsp;

1. Copie o arquivo .zip (gerado no passo anterior) para a pasta do projeto do plug-in.

![Image](<lib/NewItem170.png>)

&nbsp;

&nbsp;

1. Volte no prompt de comando e execute "rdk lfm \<ArquivoZip.zip\>" sem as áspas e substituindo \<ArquivoZip.zip\> pelo nome do arquivo gerado no passo 6.\
![Image](<lib/NewItem171.png>)\
\
&nbsp;
1. Volte na pasta projeto do plug-in e entre no sub-diretório criado pelo comando no passo anterior (Local onde contém os arquivos .lfm convertidos)\
![Image](<lib/NewItem172.png>)\
&nbsp;
1. Edite o arquivo .lfm principal (aquele que contém o mesmo nome do arquivo .PDF):\
\
![Image](<lib/NewItem173.png>)\
\
&nbsp;
1. Altere os atributos "dataType" e "title" do form para valores adequados:\
&nbsp;

*dataType* – Um texto que identifica qual é o tipo de conteúdo do seu modelo de ficha. Você **deve inventar** um Data Type único que possua ao menos cinco caracteres alfanuméricos, "\_" ou "." e que não comece com dígitos. Use a criatividade\! Exemplos: “br.com.rrpg.DnD5\_S3”, “br.com.rrpg.VampiroAMascara”, “br.com.meusite.MeuModeloDeFicha”, “meuplugin.FichaX”, etc..\
&nbsp;

*title* – O título do seu modelo de ficha. Este texto aparecerá na lista de fichas quando o usuário criar um personagem. Exemplos: “DnD 5th”, “Vampiro a Máscara”, “Meu modelo de ficha”, etc..\
\
![Image](<lib/NewItem174.png>)\
&nbsp;

&nbsp;

1. Pronto\! Agora você já pode excluir o arquivo ".zip" que colocou na pasta projeto do plug-in e executar o comando ["rdk i" ](<comandordki.md>)para testar o modelo de ficha no RRPG =)\
&nbsp; &nbsp; ![Image](<lib/NewItem178.png>)

&nbsp;

![Image](<lib/NewItem176.png>)

&nbsp;

![Image](<lib/NewItem177.png>)

&nbsp;

&nbsp;

1. Se quiser, edite os arquivos ".lfm" gerados em um editor de texto para complementar a ficha gerada\!

&nbsp;

### Observações:

* &nbsp;
  * Os cálculos e scripts existentes no PDF não são convertidos automaticamente. Você deve recriá-los manualmente, se quiser. Leia o tutorial [Criar campos calculados em fichas](<Criarcamposcalculadosemfichas.md>).

&nbsp;

### Veja também:

* &nbsp;
  * [Testando o projeto de plug-in](<Testandooprojetodeplugin.md>)
  * Veja outros [tutoriais](<Tutoriais.md>) para completar seu plug-in.
  * Caso queira adicionar mais funcionalidades ao modelo de ficha que acabou de criar, leia[ Interfaces visuais (Lua Forms)](<InterfacesVisuaisLuaForms.md>)
  * [Disponibilizando o plug-in](<Disponibilizandoumplugin.md>)\

***
_Created with the Personal Edition of HelpNDoc: [Maximize Your Productivity with a Help Authoring Tool](<https://www.helpauthoringsoftware.com/articles/what-is-a-help-authoring-tool/>)_
