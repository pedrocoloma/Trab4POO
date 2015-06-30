# Trabalho 4 de POO - Simulador de Supermercado Online
Repositório do Trabalho 4 da matéria de SSC0103 - Programação Orientada a Objetos.<br />
Descrição do trabalho: https://goo.gl/rzkrQR<br />

## Autores
João Victor Guimarães - 8936843<br />
Pedro Felipe Coloma - 8936781<br />

## VERSÃO 1.0 - Disponível na seção de Release
## Informações Gerais
### Versões usadas
Usamos a IDE Netbeans 8.0.2 e Java 8.

### Uso de arquivos externos
O programa servidor registra todas as informações em dois arquivos com extensão CSV: *products.csv* e *users.csv*.<br />
O programa servidor também registra um arquivo TXT auxiliar: *numberOfProducts.txt*. Esse arquivo contém o número de produtos já cadastrados.<br />

### Divisão de tarefas
O trabalho está dividido em dois programas: servidor e cliente.

### Uso de um Padrão de Projeto
Usamos o padrão de Projeto Singleton no construtor da classe ServerAdm. Dessa forma, essa classe não pode ser instanciadas mais de uma vez.

### Usuários Logados
Cada vez que um usuário realiza login com sucesso, ele é inserido em uma *ArrayList* chamada *LoggedUsers* que fica no servidor. Cada vez que o usuário faz logout, ele é removido dessa lista.

### Leitura e escrita de arquivos.
Com o intuito de otimizar os acessos a disco, optamos por criar duas listas do tipo *ArrayList* a partir dos arquivos CSV.
As listas *productList* e *userList* são inicializados no início do programa servidor a partir dos arquivos de registros. As alterações nos usuários e nos livros são salvas nos respectivos arquivos ao encerrar o programa, por isso <b>é importante encerrar o programa através do menu (usando a tecla Q).</b>

### Relatório em PDF
O administrador pode criar um relatório de vendas (Sales Report) em pdf. Para isso basta apertar a tecla Q no terminal do Servidor.
Cada vez que uma venda é realizada, ela é automaticamente salva no *ArrayList* salesList e no arquivo sales.csv.
Quando o adminstrador encerra a sessão (clicando a tecla Q) o arquivo SalesReport.pdf é gerado.

### Interface e menus
A interação entre o programa e o usuário ocorre pelo terminal e através de um menu simples onde as ações são escolhidas por letra ou númeross. <br />

## Arquivos de registros
## users.csv
O aquivo *users.csv* está organizada da seguinte forma: *ID do usuário, senha, nome, telefone, endereço e email*. Com o intuito de facilitar a interpretação humana e diminuir o gap semânctico. <br />
Ex: *35,senhaBemDificil, Pedro Coloma, 0800 123456, R. da entrada da Matemática, pedro.felipe.araujo@usp.br* <br />

productID = Integer.parseInt(data[0]);
                name = data[1];
                qty = Integer.parseInt(data[2]);
                price = Double.parseDouble(data[3]);;
                expirationDate = data[4];
                distribuitor = data[5];


## products.csv
O aquivo *products.csv* está organizada da seguinte forma: *ID do produto, nome, quantidade, preço, Data de Vencimento e Distribuidor.*. Com o intuito de facilitar a interpretação humana e diminuir o gap semânctico. <br />
Ex: *487,Kinder ovo Joy, 230, 1,00, 07/07/2015, Kinder* <br />

## sales.csv
O aquivo *sales.csv* está organizada da seguinte forma: *Data, quantidade, produto e lucro.*. Com o intuito de facilitar a interpretação humana e diminuir o gap semânctico. <br />
Ex: *30;06;2015,1,Computador,2.0* <br />

###.jar
O Arquivo.jar está dentro do arquivo *dist* em *Trabalho4*

## Descrição dos arquivos:<br />
Client.java:Classe encarregada de lidar com a comunicação do cliente com o servidor.<br />
ClientAdm.java: Classe encarregada de lidar com a interação com o cliente pelo terminal.<br />
<br />
Book.java: Classe livro<br /> 
TextBook.java: Contem a classe do livro texto que herda da classe *Book*<br />
GeneralBook: Contem a classe do livro genérico que herda da classe *Book*<br />
<br />
User.java: Classe usuário <br />
AcademicUser.java: Contem a classe do usuário acadêmico que herda da classe *User*.<br />
CommonUser.java: Contem a classe do usuário comum (comunidade) que herda da classe *User*<br />

Log.txt: Contém todos os *logs* dos empréstimos e devoluções.<br />

## Instruções para executar o programa:<br />
- Verifique se a sua versão do Java é compativel.
- Clique duas vezes no arquivo *trabalho.jar*
- Interaja com o programa através do menu.
- Encerre o program clicando Q + Enter
