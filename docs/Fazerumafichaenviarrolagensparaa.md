# Fazer uma ficha enviar rolagens para a mesa

# Fazer uma ficha enviar rolagens para a mesa

&nbsp;

&nbsp;

1. Adicione uma [tag button](<Tagbutton.md>) ao [Lua Form](<InterfacesVisuaisLuaForms.md>)
1. [Manipule o evento](<TratandoeventosdoLuaForm.md>) "onClick" da tag button
1. Utilize o código abaixo:

&nbsp;

|        **\<button\>**                 **\<event** name="onClick"**\>**                         **local** rolagem = rrpg.interpretarRolagem(sheet.ataqueDoPersonagem);                          **if** **not** rolagem.possuiAlgumDado **then**                                 *-- se o usuario não tiver preenchido qual dado rolar,*                                 *-- vamos adicionar um 1d20 + na "fórmula da rolagem"*                                 rolagem = rrpg.interpretarRolagem("1d20"):concatenar(rolagem);                         **end**;                          **local** mesaDoPersonagem = rrpg.getMesaDe(sheet); &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **if** mesaDoPersonagem ~= nil **then**                        &nbsp; &nbsp; &nbsp; &nbsp; mesaDoPersonagem.chat:rolarDados(rolagem, "Ataque do personagem"); &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **end**;                 **\</event\>**         **\</button\>** |
| --- |


&nbsp;

&nbsp;

1. Altere o código conforme a necessidade

&nbsp;

## O que o código acima faz?

&nbsp;

1. Utiliza a função [interpretarRolagem](<BibliotecaFirecast.md#rrpg.interpretarRolagem>) da biblioteca "[rrpg"](<BibliotecaFirecast.md>) para interpretar o campo "ataqueDoPersonagem" como uma [rolagem de dados](<ObjetoRolagem.md>).
1. Verifica se a rolagem utiliza algum dado (d4, d6, d8, etc..)... Se não possuir dado na rolagem (Exemplos: "+5", ou "-2"), faz:
   1. Interpreta uma nova rolagem "1d20" e a concatena/junta ao inicio (Para ficar, por exemplo, "1d20 + 5" ou "1d20 - 2").
1. Usando a ficha atual (sheet), tenta localizar o [objeto mesa](<ObjetoMesa.md>) à qual a ficha pertence. É usado a [função getMesaDe](<BibliotecaFirecast.md#função%20getMesaDe>) da [biblioteca rrpg](<BibliotecaFirecast.md>) para isso.
1. Se conseguiu localizar o objeto mesa à qual a ficha atual pertence:
   1. invoca o [método rolarDados](<ObjetoChat.md#função%20rolarDados>) do [chat da mesa](<ObjetoMesa.md#propriedade%20chat>), passando a rolagem que queremos e um texto adicional "Ataque do personagem".

&nbsp;

## Mudanças que você pode querer fazer no código acima

* &nbsp;
  * O código acima usa o texto da rolagem contido no campo chamado "ataqueDoPersonagem". Talvez a rolagem de sua ficha esteja em outro campo.
  * Quando a rolagem não usar nenhum dado (d4, d6, d8, etc..) o código adiciona "1d20" ao inicio dela. Talvez o sistema da sua ficha não utiliza 1d20 nesta rolagem\!
  * Que tal alterar o texto "Ataque do personagem"?
  * Talvez você queira que somente o mestre e o jogador dono da ficha possam rolar dados desta ficha.
    * Você pode utilizar a [função getPersonagemDe](<BibliotecaFirecast.md#função%20getPersonagemDe>) da [biblioteca rrpg](<BibliotecaFirecast.md>) e verificar se sua [propriedade dono](<ObjetoBibliotecaItem.md#propriedade%20dono>) é igual à [propriedade meuJogador](<ObjetoMesa.md#propriedade%20meuJogador>) da variável [mesaDoPersonagem](<ObjetoMesa.md>). Se for igual, é porque a ficha pertence ao usuário.
    * Você pode utilizar a [propriedade isMestre](<ObjetoJogador.md#propriedade%20isMestre>) do [objeto meuJogador](<ObjetoMesa.md#propriedade%20meuJogador>) para verificar se o usuário é mestre da mesa.
    * O código que faz esta verificação seria parecido com:&nbsp;

| local personagem = rrpg.getPersonagemDe(sheet); &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; if (personagem ~= nil) then &nbsp; &nbsp; local mesa = personagem.mesa; &nbsp; &nbsp; if ((personagem.dono == mesa.meuJogador) or (mesa.meuJogador.isMestre)) then&nbsp; &nbsp; &nbsp; &nbsp; -- permitir enviar a rolagem&nbsp; &nbsp; &nbsp; &nbsp; end; end; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |
| --- |


&nbsp;

&nbsp;

## Veja também:

* &nbsp;
  * [Orientações ao usar código LUA em um Lua Form](<OrientacoesaousarcodigoLUAemumLu.md>)
  * [Lua Form e NodeDatabase](<LuaFormeNodeDatabase.md>)
  * [Biblioteca rrpg](<BibliotecaFirecast.md>)
  * [Objeto Mesa](<ObjetoMesa.md>)
  * [Objeto Rolagem](<ObjetoRolagem.md>)
  * [Objeto Chat](<ObjetoChat.md>)


***
_Created with the Personal Edition of HelpNDoc: [Leave the tedious WinHelp HLP to CHM conversion process behind with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
