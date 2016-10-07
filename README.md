# locadora
Base de dados com 1,5 Milhão de Registros Relacionados<br>
a) tabela categoria:  10 regisros<br>
a) tabela filme:     100.000 regisros<br>
a) tabela cliente:     100.000 regisros<br>
a) tabela locacao:     1.500.000 regisros<br>

<br>
Antes de aplicar os scripts crie o banco de dados locadora_populado aplicando as instruções abaixo:<br>
**CREATE DATABASE locadora_populado**<br>
<br>
A criação de tabela e inclusão de dados foi realizada em um computaodr I7 com 8GB de Ram e Hd SATA de 1TB, utilizando-se do Windows 8.<br>
<br>
O consumo médio de Memória ram foi:<br>
a) prompt do windows:1 MB<br>
b) psql:1MB <br>
<br>
Tempo tempo de execução 
<br>
"inicio do processo" 14:30:41<br>
"final do processo" 14:42:47<br>
<br>

<br>
###Como executar os Scripts<br>

Baixe os aquivos **bd_locadora.zip** e  **bd_locadora2.zip**, descompacte na mesma pasta.
<br>
###ESQUEMA DO DATABASE<br>

![alt tag](https://github.com/discipbd2/base-de-testes-locadora/blob/master/esquema_locadora.png)

###ESTADO DO BANCO

![alt tag](https://github.com/discipbd2/base-de-testes-locadora/blob/master/estado_do_banco_bd_locadora.png)

<br>
### Trecho de código de exemplo para Script 
Tempo de execução para inserção na tabela clientes<br>
Start: 13:29:51<br>
Finish: 13:30:25<br>
<br>
EXEMPLO DE COIGO EXECUTADO:<br>
+++++++++++++++++++++++++++++++++++++++++++++++<br>
echo "inicio do processo" %time%<br>
set TEMP_INICIO=%time%<br>
psql -h localhost -d locadora_populado -U postgres -p 5432 -q -W -f script_InsertCliente.sql<br>
echo "inicio do processo" %TEMP_INICIO%<br>
echo "fim do processo" %time%<br>
+++++++++++++++++++++++++++++++++++++++++++++++<br>
<br>
