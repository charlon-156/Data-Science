# Banco de Dados

Olá, companheiros! 

# Introdução 

Todos os dias nós somos abordados por uma necessidade humana de armazernar informações, desde o tempo das primeiras sociedades da humanidade o ser humano vem buscando maneiras de armazenar informações, pois nem sempre o cérebro pode armazenar tudos os dados. *Quem lembra os digitos do cartão do SUS? Quem lembra os números de todos os amigos e conhecidos?* Por isso o século XX criou um sistema virtual de armazenamento de dados. 

Não se trata apenas de armazenar dados e mais dados, e sim num trabalho dedicado ao bom funcionamento. Evitar **repetição** de informações, **isolar** os dados, garantir **segurança**, tratar **anomalias** são finalidades dos sistemas de `database`. 

## História 
Foi durante o periodo pós meados do século XX da história nas quais as empresas verificaram que era necessário empregar muitas pessoas, além do alto custo para fazer trabalhos, tais como: armazenar e organizar seus arquivos. Por este motivo, eram importantes os esforços e investimentos em pesquisa para obter-se um meio mais barato e eficiente de armazenamento de dados.

Em 1970 a IBM publicou o primeiro trabalho sobre bancos de dados relacionais. Este trabalho tratava sobre o uso de cálculo e álgebra relacional para que usuários não técnicos pudessem manipular grande quantidade de informações. Dessa forma, banco de dados são importantes para substituir o armazenamento de dados em papéis ou até mesmo na mémoria.

# Modelagem

Antes de cair de cara nos códigos, veremos um pouco sobre a termologia da ciência de dados - SQL, DML... e muito mais.

## Abstração 

Para que o sistema funcione perfeitamente, precisa-se que dados sejam recuperados de maneira eficiente. Para atingir essa eficiência os [projetistas de Banco de Dados](#usuários) vem a um bom tempo usando estruturas complexas de dados,tudo isso para o planejamento e a analise de sistemas de dados — deve-se produzir diagramas e modelos conceituais e lógicos para se construir os bancos de dados, pois não se pode cair diretamente nos comandos. É preciso primeiramente esquematizar a base de dados. Eu já escrevi um pouco sobre modelagem de dados em meu outro repositório. Leia o meu documento sobre aqui em: [Modelagem](https://github.com/charlon-156/MySQL/blob/main/Modelagem.md)

## Instância e esquemas

O banco de dados mudam constantemente, isso ocorre a medida em que as informações são inseridas e excluídas. Um agrupamento de dados em um determinado momento é chamado de **instância**. Já o **esquema** é um projeto geral do banco de dados, os esquemas são como diagramas que vão descrever o banco de dados.  

# Linguagem de banco de dados

Agora brota a duvida, qual é a linguagem de programação de um banco? Bem, isso não existe, existe na verdade o que chamamos de **SQL** - *Structured Query Language*. Traduzindo ao pé da letra: Linguagem de Consulta Estruturada. Nela existem diversos comando; criar banco, inserir dados e etc. são exemplos de comandos SQL, se você já viu o básico de Banco de Dados, vá estudar os comandos, para isso veja meu documento APENAS com comandos de SQL no SGBD chamado MySQL, clique aqui -> [Comandos SQL](https://github.com/charlon-156/MySQL/blob/main/Commands.md)

## Usuários 
O banco de dados vai possuir diferentes atores, pessoas que vão participar do banco, mas cada um de forma diferente, veja os 4 principais agora:

- **Analistas de bancos de dados** (projetistas): possuem a responsabilidade de identificar os dados a serem armazenados no BD e pela escolha da estrutura apropriada utilizada para armazená-los.
- **Administradores de bancos de dados** (DBA): Em um sistema de base de dados, o recurso primário é o `database` e os outros recursos são o `SGBD` e software relacionados. A administração desses recursos é de responsabilidade do DBA (“Database Administrator”). O DBA é responsável por autorizar acesso à base de dados e coordenar e monitorar seu uso, como também é responsável por problemas, tais como: quebra de segurança ou baixo desempenho.
- **Usuários finais**: existem profissionais que precisam ter acesso à base de dados para consultar, modificar e gerar relatórios. A base de dados existe para estes usuários. 
- **Analistas de sistemas e programadores de aplicações**: os analistas determinam os requisitos dos usuários finais e desenvolvem especificações para transações que atendam estes requisitos, e os programadores implementam estas especificações.

# SGBD 
O controlador do Banco de Dados são os famosos SGBDs, destrinchando fica *Sistema de Gerenciamento de Banco de Dados*. O SGBD é responsável por basicamente e simplesmente... TUDO. Fornecer uma interface, encriptar dados, controlar o acesso a informações, fazer e armazenar Backups, garantir transações de informações seguras e que garanta a proteção e evitar anomalias estruturais e de informações. O mais famosos SGBDs são:
- Mysql
- MariaDB
- SQL Server
- SQLite3

# Normalização de Dados
Quando falaremos do Modelo Entidade Relacionamento (MER), considerando outro ponto de vista. Anteriormente, era apresentado o contexto em que tinha-se a ideia de modelar o banco e eram definidas as entidades, relacionamentos e atributos de forma bastante subjetiva. Para isso surgiu as Formas Normais, o que é as Formas Normais?? É um conjunto de regras cujo propósito é auxiliar na simplificação das estruturas de dados mais complexas – reduzindo as chances de anomalias.

Para atingir os objetivos, podemos dizer que um banco de dados está relacionado a alguns conceitos fundamentais:
- Banco de Dados = Coleção de Arquivos;
- Arquivos = Coleção de Registros;
- Registro = Coleção de Campos (Tuplas);
- Campo = Coleção de Caracteres;
- Caractere = Alfa-numéricos ou símbolos. 

## 1ª Forma Normal - 1FN
Existem situações em que nos deparamos com algumas informações que se repetem (atributo multivalorado) dentro de uma única linha, ligada a uma chave primária. A 1FN diz que cada ocorrência da chave primária deve corresponder a somente uma informação de cada atributo, ou seja, a entidade não deve conter atributos repetidos ou multivalorados, ou, ainda, os atributos não-chave deverão ser atômicos (únicos).

Ao observarmos que certo grupo de atributos não-chave não são atômicos, ao longo do processo de entrada de dados, verificamos que este atributo deverá ser **decomposto em uma nova entidade**.

Veja essa tabela, ela não está no 1FN: Endereço está composto e telefone multivalorado
| **Id_Pessoa** | **Nome** |      **Endereço**     |       **Telefones**      |
|---------------|:--------:|:---------------------:|:------------------------:|
| 1             |   Chico  |  Av. Carlos, Caicó-RN | 9-9324-5678, 9-9988-7533 |
| 2             |   Anna   | Rua Trio, Campinas-PB |        9-8863-2170       |

Para deixa-la na primeira 1FN deve-se destrinchar todos os dados do endereço
| **Id_Pessoa** | **Nome** |   **Rua**  | **Cidade** | **UF** |
|:-------------:|:--------:|:----------:|:----------:|:------:|
|       1       |   Chico  | Av. Carlos |    Caicó   |   RN   |
|       2       |   Anna   |  Rua Trio  |  Campinas  |   PB   |

Sobre os números deve fazer uma nova tabela de atributo composto
| **Id_Pessoa** | **Telefone** |
|:-------------:|:------------:|
|       1       |  9-9988-7533 |
|       1       |  9-9324-5678 |
|       2       |  9-8863-2170 |

## 2ª Forma Normal - 2FN

Pronto, os atributos multivalorados e redundantes foram destrinchados. Porém, ainda há redundâncias que podem ser corrigidas para melhorar o desempenho do SGBD. Segundo a segunda forma Normal, **Na tabela só pode haver atributos que dependem apenas da chave primária**. Por exemplo, dentro da tabela aluno: eu tenho o atributo, nome do professor, código da sala, nome do aluno e data de nascimento do aluno. Apenas esses dois ultimos atributos estam na segunda forma normal. Veja, essa tabela asseguir:

| **alu_codigo** | **alu_nome** | **alu_professor** | **alu_turma** | **alu_dataNascimento** |
|:--------------:|:------------:|:-----------------:|:-------------:|:----------------------:|
|        1       |    Charlon   |       Diego       |       1       |       2004-11-11       |
|        2       |    Beatrix   |        Iuri       |       2       |       2004-10-08       |
|        3       |    Augusto   |        Iuri       |       2       |       2005-01-02       |

Para corrigir, cada atributo deve movido até a tabela em que ele dependa apenas da chave primária, por exemplo, o atributo professor deve ser levado para a tabela professores, onde aquele nome, estará apenas relacionado a um unico nome. Pois no caso anterior, o mesmo professor estava duplicado na tabela, logo, causando redundância de dados.

## 3ª Forma Normal - 3FN

para estar na 3FN, é preciso estar na 2FN. Além disso, os atributos não chave de uma tabela devem ser mutuamente independentes e dependentes unicamente e exclusivamente da chave primária (um atributo B é funcionalmente dependente de A se, e somente se, para cada valor de A só existe um valor de B). Para atingir essa forma normal, é preciso identificar as colunas que são funcionalmente dependentes das outras colunas não chave e extraí-las para outra tabela. Considere, como exemplo, a tabela FUNCIONARIOS a seguir.

FUNCIONARIOS = { ID + NOME + ID_CARGO + DESCRICAO_CARGO }

O atributo DESCRICAO_CARGO depende exclusivamente de ID_CARGO (atributo não chave) e, portanto, deve-se criar uma nova tabela com esses atributos. Dessa forma, ficamos com as seguintes tabelas:

FUNCIONARIOS = { ID + NOME + ID_CARGO }
CARGOS = { ID_CARGO + DESCRICAO }