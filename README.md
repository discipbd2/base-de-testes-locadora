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
Tempo tempo de execução - Windows
<br>
"inicio do processo" 14:30:41<br>
"final do processo" 14:42:47<br>

Tempo tempo de execução - linux 
<br>
"inicio do processo" 20:48:19
"final do processo" 20:51:50
<br>

obs: para linux foi necessário aplicar \Set autocomit = off
<br>
### Como executar os Scripts<br>
#### No Windows
Baixe os aquivos **bd_locadora.zip** e  **bd_locadora2.zip**, descompacte na mesma pasta.<br>
Entre na pasta e execute:<br>
a) exec_cria_tabelas_insere_dados.bat

#### No Linux<br>
Baixe o arquivo linux_bd_locadora.tar.bz2 e descompacte o arquivo. <br>
Entre na pasta e execute:<br>
a) chmod +x exec_cria_tabelas_insere_dadosN.sh
b) ./exec_cria_tabelas_insere_dadosN.sh

<br>
###ESQUEMA DO DATABASE<br>

![alt tag](https://github.com/discipbd2/base-de-testes-locadora/blob/master/esquema_locadora.png)

###ESTADO DO BANCO

![alt tag](https://github.com/discipbd2/base-de-testes-locadora/blob/master/estado_do_banco_bd_locadora.png)

<br>
### Trecho de código de exemplo para Script no Windows 
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


### Trecho de código de exemplo para Script no Linux 
Tempo de execução para inserção na tabela clientes<br>
Start: 20:48:27<br>
Finish: 20:48:39<br>
<br>
EXEMPLO DE COIGO EXECUTADO:<br>
+++++++++++++++++++++++++++++++++++++++++++++++<br>
now=$(date +"%T")<br>
psql -h localhost -d locadora_populado -U postgres -p 5432 -q -W -f script_InsertClienteN.sql<br>
echo "inicio do processo de insercao cliente" $now<br>
fim=$(date +"%T")<br>
echo "fim do processo de insercao cliente" $fim<br>
+++++++++++++++++++++++++++++++++++++++++++++++<br>
<br>



