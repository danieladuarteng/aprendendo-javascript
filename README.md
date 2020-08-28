# Aprendendo JavaScript

Este repositório tem como objetivo de guardar referências teóricas e práticas do JavaScript.

## Achou alguma coisa errada? Me ajude a corrigir 

Esse projeto é open source, basta alterar esse arquivo diretamente no Github e abrir um pull-request.

E se tiver alguma ideia de como melhorar este projeto abra uma Issue.

Isso acaba sendo uma das maneiras práticas de contribuir com a comunidade e aprender cada vez mais ;)


## Introdução do JavaScript

JavaScript ou JS é uma linguagem de programação dinâmica, ou seja, que se adapta rápido as mudanças, assim ela proporciona interações ao seu site quando aplicada a um documento HTML.

## Declarações

Para armazenar valores, existem 3 tipos de declarações que podemos usar no JavaScript, cada uma com seu propósito:

1. **Como declarar um valor global, ou seja, que esteja disponível em qualquer lugar do código, e ainda possa ser alterada a qualquer momento?**

   Utilize a palavra reservada VAR, seu uso é bem perigoso, pois como dito anteriormente pode ser alterado em qualquer lugar e momento do código, por isso não é recomendado seu uso.
2. **Ok, não é recomendado usar o VAR, mas então o que uso caso precise armazenar um valor que vai ser alterado futuramente?**

   Use o LET, pois ela pode ser alterada sempre que necessário, porém somente dentro do seu escopo ou bloco.

   Exemplo:

   ```javascript
   function alteraValor() {
   
     /* Criei uma declaração 
     chamada valorInicial do tipo LET */
     let valorInicial = 0; 
     
     /* Como ela é do tipo LET posso 
     alterar seu valor */
     valorInicial = 1;

     /* Peço para mostrar o valor 
     de valorInicial */
     console.log(valorInicial)
   }

   /* Quando chamo a função alteraValor 
   é exibido o valor de valorInicial como 1 */
   alteraValor() // 1
   ```

   Agora se eu quiser alterar o valor da declaração valorInicial fora das chaves {} que delimitam o escopo/bloco da função seu valor não será alterado pois só pode ser alterado dentro do bloco.

   Exemplo:

   ```javascript
   function alteraValor() {
    let valorInicial = 0; // Declarei 
    return valorInicial; // Retorno do valor
   }

   alteraValor() // Chamando a função seu retorno é 0

   /* Atribui um novo valor ao valorInicial 
   que declarei dentro da função */
   valorInicial = 1 

   /* Chamo a função novamente para ver se mudou o valor, 
   e o valor continuar sendo 0, pois ele só pode ser alterado 
   quando está dentro da função */
   alteraValor() 

   /* Agora se eu quiser imprimir 
   o valorInicial aqui fora da função, 
   irá dar um erro, falando que o 
   valorInicial não está definido 
   ou seja declarado */
   console.log(valorInicial) // valorInicial is not defined
   ```
3. **E se eu quiser declarar um valor que não vai mudar?**

   Eu uso a CONST, pois ela só pode ser criada uma vez, e é obrigatório a atribuição de um valor inicial a ela, diferente da VAR e LET, pois quando criada ela somente pode ser lida e não alterada.
   
   Exemplo:

   ```javascript
   /* Aqui declaro a variável soma 
   como const, pois ela já inicia 
   com um valor, no caso uma operação 
   aritmética, que não irá ser alterada */
   const soma = 15 + 8;
   ```

## Tipos de dados

   Além dos tipos de declaração, também existe os tipos de dados/valores que podem ser armazenados nessas declarações.

   Exemplo:

   ```javascript
   /* Aqui declarei minhaVariavel com 
   o valor 2, ou seja ela é do tipo de 
   dado NUMBER, pois é um número */
   let minhaVariavel = 2;
   ```

   Os tipos de dados, são classificados por dois tipos:

   1. Tipo primitivo:

      * **number**: guarda números:

         `let numero = 6;`
      * **string**: textos, frases:

         `let nome = 'Daniela';`
      * **boolean**: guarda valores boleanos verdadeiro ou falso:

        `let valorBooleano = false;`
      * **null**: indica que não há valor numa declaração:

        `let semValor = null;`
      * **undefined**: indica que a declaração não existe ou não tem tipo:

        `let a;`

   2. Tipo primitivo:

      * **object**: guarda um conjunto de propriedades (que podem ser tanto de tipo primitivo ou objeto) e métodos que representam o mundo real:
      
         ```javascript
        const pessoa = 
        { 
          nome: 'Dani',
          idade: 25,
          falar: function falar() {
            return 'Oi' 
          }
        };
        ```
      * **array**: é um objeto global usado na construção de listas:

        ```javascript
        const frutas = ['morango', 'laranja', 'banana'];
        ```
