# Banco de Dados

Olá, companheiros! 

# Introdução 

Todos os dias nós somos abordados por uma necessidade humana de armazernar informações, desde o tempo das primeiras sociedades da humanidade o ser humano vem buscando maneiras de armazenar informações, pois nem sempre o cérebro pode armazenar tudos os dados. *Quem lembra os digitos do cartão do SUS? Quem lembra os números de todos os amigos e conhecidos?* Por isso o século XX criou um sistema virtual de armazenamento de dados. 

Não se trata apenas de armazenar dados e mais dados, e sim num trabalho dedicado ao bom funcionamento. Evitar **repetição** de informações, **isolar** os dados, garantir **segurança**, tratar **anomalias** são finalidades dos sistemas de `database`. 

## História 
Foi durante o periodo pós meados do século XX da história nas quais as empresas verificaram que era necessário empregar muitas pessoas, além do alto custo para fazer trabalhos, tais como: armazenar e organizar seus arquivos. Por este motivo, eram importantes os esforços e investimentos em pesquisa para obter-se um meio mais barato e eficiente de armazenamento de dados.

Em 1970 a IBM publicou o primeiro trabalho sobre bancos de dados relacionais. Este trabalho tratava sobre o uso de cálculo e álgebra relacional para que usuários não técnicos pudessem manipular grande quantidade de informações.

# Modelagem

Antes de cair de cara nos códigos, veremos um pouco sobre a termologia da ciência de dados - SQL, DML... e muito mais.

## Abstração 

Para que o sistema funcione perfeitamente, precisa-se que dados sejam recuperados de maneira eficiente. Para atingir essa eficiência os [projetistas de Banco de Dados](#usuários) vem a um bom tempo usando estruturas complexas de dados,tudo isso para o planejamento e a analise de sistemas de dados. Eu já escrevi um pouco sobre modelagem de dados em meu outro repositório. Leia o meu documento sobre aqui em: [Modelagem](https://github.com/charlon-156/MySQL/blob/main/Modelagem.md)

## Instância e esquemas

O banco de dados mudam constantemente, isso ocorre a medida em que as informações são inseridas e excluídas. Um agrupamento de dados em um determinado momento é chamado de **instância**. Já o **esquema** é um projeto geral do banco de dados, os esquemas são como diagramas que vão descrever o banco de dados.  

# Linguagem de banco de dados

Agora brota a duvida, qual é a linguagem de programação de um banco? Bem, não existe isso, existe na verdade o que chamamos de **SQL** - *Structured Query Language*. Traduzindo ao pé da letra: Linguagem de Consulta Estruturada. Nela existem diversos comando; criar banco, inserir dados e etc. são exemplos de comandos SQL, se você já viu o básico de Banco de Dados, vá estudar os comandos, para isso veja meu documento APENAS com comandos de SQL no SGBD chamado MySQL, clique aqui -> [Comandos SQL](https://github.com/charlon-156/MySQL/blob/main/Commands.md)

## Usuários 
O banco de dados vai possuir diferentes atores, pessoas que vão participar do banco, mas cada um de forma diferente, veja os 4 principais agora:

- **Analistas de bancos de dados** (projetistas): possuem a responsabilidade de identificar os dados a serem armazenados no BD e pela escolha da estrutura apropriada utilizada para armazená-los.
- **Administradores de bancos de dados** (DBA): Em um sistema de base de dados, o recurso primário é o `database` e os outros recursos são o `SGBD` e software relacionados. A administração desses recursos é de responsabilidade do DBA (“Database Administrator”). O DBA é responsável por autorizar acesso à base de dados e coordenar e monitorar seu uso, como também é responsável por problemas, tais como: quebra de segurança ou baixo desempenho.
- **Usuários finais**: existem profissionais que precisam ter acesso à base de dados para consultar, modificar e gerar relatórios. A base de dados existe para estes usuários. 
- **Analistas de sistemas e programadores de aplicações**: os analistas determinam os requisitos dos usuários finais e desenvolvem especificações para transações que atendam estes requisitos, e os programadores implementam estas especificações.

# SGBD 
O controlador do Banco de Dados são os famosos SGBDs, destrinchando fica *Sistema de Gerenciamento de Banco de Dados*. O SGBD é responsável por basicamente e simplesmente... TUDO. Fornecer uma interface, encriptar dados, controlar o acesso a informações, fazer e armazenar Backups, garantir transações de informações seguras e que garanta a proteção e evitar anomalias estruturais e de informações. 
O mais famosos SGBDs são:
- Mysql
- MariaDB
- SQL Server
- SQLite3

