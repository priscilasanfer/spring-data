# Curso Spring Data JPA: Repositórios, Consultas, Projeções e Specifications


### *01. Primeiro Repositório*

*P:* Dentro da nossa classe SpringDataAplication temos nosso método main, que no Java é utilizado para iniciar uma aplicação. Dentro desse método adicionamos uma linha relacionada ao Spring:  
SpringApplication.run(SpringDataApplication.class, args)  
Qual a função dessa linha?  
  
*R:* Ela faz com que o framework do Spring seja inicializado junto a nossa aplicação.  
Precisamos inicializar o framework para conseguirmos utilizar suas ferramentas dentro da nossa aplicação.  
Além disso, existem algumas anotações como a @SpringBootApplication que devemos usar.  

*P:* Qual a principal vantagem que temos em utilizar a interface CrudRepository dentro do nosso projeto?  
*R:* Realizar métodos CRUD sem a necessidade de criar os objetos do JPA. Sem a necessidade de criar nenhum objeto do JPA, conseguimos realizar métodos do CRUD.  



### *02. Operações CRUD*
*P:* No framework do Spring Data, quais métodos são utilizados para quais operações? Marque apenas uma alternativa.
obs.: caso esteja com dúvidas, por favor consulte a documentação: https://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/repository/CrudRepository.html

*R:* Para inserir ou atualizar usamos o método save. O método save serve para entidades transient e detached

*P:*  Qual a finalidade de utilizarmos o Optional retornado pelo método findById?  
*R:* O comando pode retornar um elemento, se existir, por isso é usado Optional. O findById sempre devolve um Optional, que sabe se o elemento existe ou não. Assim, não precisamos lidar com null ou tratar uma exceção.  


### *03. Derived Queries, JPQL e Native Queries*

*P:* Qual a diferença entre Derived Query, JPQL e Native Query?  
*R:* *Derived Queries* - queries criadas através de comandos Java  
*JPQL* - queries criadas através de uma estrutura SQL, porém com os nomes das entidades Java  
*Native Query* - queries padrões SQL que conseguimos executar no nosso Client SQL  
As queries são executadas, cada uma utilizando sua estrutura.  

### *04. Paginação e Ordenação*  

*P:*  Quando utilizamos o repositório PagingAndSortingRepository, adicionamos à nossa aplicação todo o poder da paginação. Porém, para utilizarmos de fato esse poder, devemos passar um atributo no método findAll.  
Qual o atributo e por que o usamos?  

*R:* Pageable - enviamos esse objeto pois nele encapsulamos a página, a quantidade de itens por página e qual o tipo de ordenação.  
Enviamos esse objeto como parâmetro para informarmos ao nosso repository as informações que queremos receber na nossa paginação.  


### *05. Trabalhando com Projeções*
*P:* Quando fazemos projeções com o Spring Data, temos que criar uma interface dentro do nosso projeto. Qual é a função dessa interface?

*R:* Criar uma entidade projetada contendo os atributos que queremos apresentar. O objetivo de criar essa interface é encapsular os valores de retorno da consulta dentro de métodos.  



### *06. Consultas dinâmicas*
*P:* Quando criamos consultas dinâmicas, utilizamos a Specification. Qual é o seu papel na criação das consultas dinâmicas?
*R:* Ter um objeto com todos os itens necessários para realizar uma consulta dinâmica, como por exemplo root, criteriaQuery e criteriaBuilder. O objetivo é entregar, ao desenvolver um objeto pronto, para que ele só tenha que se preocupar com qual operação SQL ele deseja executar.

