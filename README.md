# mock - Implementação de uma camada de Serviço com Testes que usam Mocks

Considerando o mesmo modelo da atividade de teste de integração:

![image](https://user-images.githubusercontent.com/75092912/199726605-a95fef5a-936a-4cc9-a653-80ce8698c98a.png)

## Tarefas

- Criar um pacote de serviço (por exemplo, empresa.sistema.servico)

- É fundamental explorar a API do mockito para montar os cenários com os dublês, verificar a chamada de métodos e testar cenários de exceções e organizar as classes e interfaces da camada de serviço.
  - EnviadorDeEmail: deverá ter, no mínimo a funcionalidade de enviar email a todos para todos os clientes que não pagaram o aluguel na data prevista.
  - Tratando Exceção: Usando Mock Objects crie um teste, que verifique se uma exceção foi lançada, O EnviadorDeEmail continuará funcionando da mesma forma, caso um email seja rejeitado. Os outros emails deverão ser enviados.
  - GeradorDePagamento: Uma exceção deverá ser lançada, caso o valor_pago seja menor que o valor do aluguel.
  - Valor a ser pago com multa: Dado a data de vencimento e a data de pagamento, calcule o valor a ser pago, incluindo a multa. Se o pagamento estiver dentro do prazo, deverá ser retornado o valor do aluguel sem acréscimo de multas.
  
>
> ## Observações importantes:
>
> #### 1. A multa deve possuir uma estrutura para o valor de pagamento:
>```
>0,33% por dia de atraso, limitada a 80% do valor do aluguel
>```
>
> #### 2. Para quem estiver usando o Java a partir da vesão 9 ao invés de usar a biblioteca do mockito:
>```
><dependency>
>      <groupId>org.mockito</groupId>
>      <artifactId>mockito-all</artifactId>
>      <version>1.10.19</version>
>      <scope>test</scope>
></dependency>-->
>```
> 
>**** Use a biblioteca do power mock
>```
><dependency>
>     <groupId>org.powermock</groupId>
>     <artifactId>powermock-api-mockito2</artifactId>
>     <version>2.0.9</version>
>     <scope>test</scope>
></dependency>
>```
>
> #### 3. Para quem tiver usando o driver JDBC para o MySQL 8 adicione a seguinte propriedade na URL ";allowPublicKeyRetrieval=true"
>```
><property name="javax.persistence.jdbc.url"
>   value="jdbc:mysql://localhost/locadoratest?
>   useSSL=false&amp;serverTimezone=UTC&amp;createDatabaseIfNotExist=true&amp;allowPublicKeyRetrieval=true"/>
>```
>
