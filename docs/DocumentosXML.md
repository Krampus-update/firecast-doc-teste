# Documentos XML

# Documentos XML

XML são documentos usados para guardar e catalogar informações de forma intuitiva e flexível, e servem para diversas finalidades\!

&nbsp;

**Importante**: Os documentos XMLs possuem “um rosto” diferente para cada finalidade. Exemplo: Enquanto um XML de interface possui um conjunto de informações e marcações específicas, um XML de informações do plugin possui **outro** conjunto **distinto** de informações e marcações específicas. Haverá uma documentação própria para guiar seus passos em cada uma dessas finalidades\!

&nbsp;

Links úteis:

* XML na wikipedia: [http://pt.wikipedia.org/wiki/XML](<http://pt.wikipedia.org/wiki/XML>)
* Introdução ao XML: [http://www.macoratti.net/xml.htm](<http://www.macoratti.net/xml.htm>)&nbsp;

&nbsp;

Se você está tendo problemas com os documentos XML, eis aqui algumas dicas:

* Certifique que as marcações/tags abertas estão sendo fechadas corretamente. Nomes de marcações são case-sensitives e precisam ser exatamente iguais à marcação de abertura.
* Certifique que as marcações usadas são válidas para a finalidade desejada.
* Alguns caracteres são reservados para controle do XML. Se você precisar deles mesmo assim, é preciso fazer substituição por um código especial. Veja Lidando com caracteres reservados do XML.
* Em caso de erro relacionado à codificação do texto, cerifique-se que o documento possui um cabeçalho XML identificando corretamente a codificação do documento. O cabeçalho é a primeira linha do documento, onde:
  * Se o documento estiver codificado em UTF-8, o cabeçalho deve ser:
    * \<?xml version="1.0" encoding="UTF-8"?\>&nbsp;
  * Se você não sabe a codificação do documento, talvez o cabeçalho correto seja:
    * \<?xml version="1.0" encoding="ISO-8859-1"?\>&nbsp;

&nbsp;

&nbsp;

## Lidando com caracteres reservados do XML

&nbsp;

Alguns caracteres são reservados para controle do XML. Se você precisar deles mesmo assim, é preciso fazer substituição por um código especial:

&nbsp;

### Tabela de caracteres reservados:

| Caractere reservado | Substituição |
| :---: | :---: |
| \< | \&lt; |
| \> | \&gt; |
| \& | \&amp; |
| ‘ | \&apos; |
| “ | \&quot; |


#### Exemplos de substituição:

* \<label text=”D\&amp;D”/\> &nbsp; \
Substituição de "\&" por "\&amp;" ... Contém "D\&D"\
&nbsp;
* \<button text=”20 \&gt; 10”/\> \
Substituição de "\>" por "\&gt"; .... Contém "20 \> 10"

&nbsp;

### CDATA

Você também pode utilizar blocos CDATA para evitar fazer substituições, o que é útil em códigos LUA dentro de XML.&nbsp; \
Saiba mais em [http://en.wikipedia.org/wiki/CDATA](<http://en.wikipedia.org/wiki/CDATA>)

&nbsp;

#### Exemplo de CDATA

&nbsp;

| **\<event** name="onResize"**\>**         \<\!\[CDATA\[                 local teste = "D\&D";                                if (x \< y) or (x \> z) then                         local teste = 'D\&D 4.0';                 end;         \]\]\> **\</event\>** |
| --- |


&nbsp;

Não é preciso fazer nenhuma substituição de caracteres reservados dentro de um bloco CDATA.

&nbsp;

Observação: Só é possível utilizar CDATA no corpo de um nodo do XML. Não é possível usar CDATA no valor de um atributo, por exemplo.

&nbsp;

&nbsp;

&nbsp;

&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Create help files for the Qt Help Framework](<https://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework>)_
