# Tag timer

# Tag timer

A tag **timer** representa um componente não visual (não é exibido na interface) que executa determinado código LUA de tempo em tempo.

## Características

### Propriedades e atributos

| **Propriedade** | Tipo | Valor Padrão | Descrição |
| --- | --- | --- | --- |
| **name** | String | \<string vazio\> | Define um nome para a componente.&nbsp; O nome deve ser único, isto é, dentro de um **form**, não é possível existir 2 controles com o mesmo nome. Se não for definido um nome para o controle no arquivo LFM, um nome único será gerado para ele em tempo de compilação. Nomear controles é especialmente útil quando se quer trabalhar com códigos LUA.&nbsp; |
| **interval** | Integer | &#49;000 | Intervalo, medido em milisegundos, de quando em quando o evento onTimer será disparado.&nbsp; 1000 = 1 segundo 500 = 0,5s 10000 = 10 segundos&nbsp; |
| **enabled** | Boolean | true | Quando true, o evento onTimer será disparado de acordo com o atributo interval.&nbsp; Quando false, o evento onTimer não será disparado.&nbsp; |


&nbsp;

### Eventos

| **Nome do evento** | Descrição |
| --- | --- |
| **onTimer** | Este evento é invocado de tempos em tempos, de acordo com o valor da propriedade "interval".&nbsp; |


&nbsp;

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

&nbsp;

## Exemplos

### Exemplo 1 - Um label "piscando"

&nbsp;

| **\<?xml** version="1.0" encoding="UTF-8"**?\>** **\<form** name="frmFichaTeste"**\>**                  **\<timer** interval="500" onTimer="self.labMeuLabel.visible = not self.labMeuLabel.visible;"**/\>**                **\<label** name="labMeuLabel" align="client" horzTextAlign="center" text="Olá\!"**/\>** **\</form\>** |
| --- |


&nbsp;

![Image](<lib/NewItem155.png>)&nbsp; ![Image](<lib/NewItem156.png>)

Veja [Tratando eventos do Lua Form](<TratandoeventosdoLuaForm.md>)

\
&nbsp;


***
_Created with the Personal Edition of HelpNDoc: [Full-featured multi-format Help generator](<https://www.helpndoc.com/help-authoring-tool>)_
