# Trabalho 4 de POO - Simulador de Supermercado Online
Repositório do Trabalho 4 da matéria de SSC0103 - Programação Orientada a Objetos.<br />
Descrição do trabalho: https://goo.gl/rzkrQR<br />

## Autores
João Victor Guimarães - 8936843<br />
Pedro Felipe Coloma - 8936781<br />

## Informações Gerais
### Versões usadas
Usamos a IDE Netbeans 8.0.2 e Java 8.

### Síntese
O programa é dividido em dois: Cliente e Servidor.
O primeiro é encarregado de interargir com o cliente do supermercado, i.e. permie cadastrar/logar usuários, listar os produtos e realizar compras.
O segundo é encarregado de interagir com o administrador do servidor do supermercado. i.e. permite cadastrar/atualizar produtos, gerar relatórios, listar produtos e usuáros.

### Uso de arquivos externos
O programa servidor registra todas as informações em três arquivos com extensão CSV: *products.csv*, *users.csv* e *sales.csv*.<br />
O programa servidor também registra um arquivo TXT auxiliar: *numberOfProducts.txt*. Esse arquivo contém o número de produtos já cadastrados.<br />

### Uso de um Padrão de Projeto
Usamos o padrão de Projeto Singleton no construtor da classe ServerAdm. Dessa forma, essa classe não pode ser instanciada mais de uma vez.

### Usuários Logados
Cada vez que um usuário realiza login com sucesso, ele é inserido em uma *ArrayList* chamada *LoggedUsers* que fica no servidor. Cada vez que o usuário faz logout, ele é removido dessa lista.

### Leitura e escrita de arquivos.
Com o intuito de otimizar os acessos a disco, optamos por criar duas listas do tipo *ArrayList* a partir dos arquivos CSV.
As listas *productList*,  *userList* são inicializados no início do programa servidor a partir dos arquivos de registros. As alterações nos usuários e nos livros são salvas nos respectivos arquivos ao clicar na Tecla Q.

### Relatório em PDF
O administrador pode criar um relatório de vendas (Sales Report) em pdf. Para isso basta apertar a tecla Q no terminal do Servidor.
Cada vez que uma venda é realizada, ela é automaticamente salva no *ArrayList* salesList e no arquivo sales.csv.
Quando o adminstrador manda salvar os relat´rorios (clicando a tecla Q) o arquivo SalesReport.pdf é gerado.
O arquivo pdf é gerado usando o itextpdf-5.5.6.jar.

### Interface e menus
A interação entre o programa e o usuário ocorre pelo terminal e através de um menu simples onde as ações são escolhidas por letra ou númeross. <br />

## Arquivos de registros
### users.csv
O aquivo *users.csv* está organizada da seguinte forma: *ID do usuário, senha, nome, telefone, endereço e email*. Com o intuito de facilitar a interpretação humana e diminuir o gap semânctico. <br />
Ex: *35,senhaBemDificil, Pedro Coloma, 0800 123456, R. da entrada da Matemática, pedro.felipe.araujo@usp.br* <br />

### products.csv
O aquivo *products.csv* está organizada da seguinte forma: *ID do produto, nome, quantidade, preço, Data de Vencimento e Distribuidor.*. Com o intuito de facilitar a interpretação humana e diminuir o gap semânctico. <br />
Ex: *487,Kinder ovo Joy, 230, 1,00, 07/07/2015, Kinder* <br />

### sales.csv
O aquivo *sales.csv* está organizada da seguinte forma: *Data, quantidade, produto e lucro.*. Com o intuito de facilitar a interpretação humana e diminuir o gap semânctico. <br />
Ex: *30;06;2015,1,Computador,2.0* <br />

<br />

##Arquivo .jar
Os Arquivo .jar estã dentro das pastas *dist* em *Trabalho4* E em *Client*

## Descrição dos arquivosde código:<br />
### Na pasta Trabalho4 (arquivos do servidor)
Trabalho4.java Contém o Middleman que é encarregado lidar com a conexão com o cliente. Chama os métodos do serverAdm para realizar login, signup, etc.
ServerAdm.java: Contém os métodos para login, signup, buyProduct, restockProduct, etc.
Product.java: Classe do produto.
User.java: Classe do usuário.

### Na pasta Client (arquivos do cliente)
Client.java:Classe encarregada de lidar com a comunicação do cliente com o servidor.<br />
ClientAdm.java: Classe encarregada de lidar com a interação com o cliente pelo terminal.<br />
<br />

## Instruções para executar o programa:<br />
- Verifique se a sua versão do Java é compativel.
### Para o Servidor
- Rode o arquivo *Trabalho4.jar* localizado na pasta Trabalho4/dist
### Para o cliente
- Rode o arquivo *Client.jar* localizado na pasta client/dist
