# Aprendendo JavaScript

Este repositório tem como objetivo de guardar referências teóricas e práticas do JavaScript.

## Achou alguma coisa errada? Me ajude a corrigir 

Esse projeto é open source, basta alterar esse arquivo diretamente no Github e abrir um pull-request.

E se tiver alguma ideia de como melhorar este projeto abra uma Issue.

Isso acaba sendo uma das maneiras práticas de contribuir com a comunidade e aprender cada vez mais ;)


## Introdução do JavaScript

JavaScript ou JS é uma linguagem de programação dinâmica, ou seja, que se adapta rápido as mudanças, assim ela proporciona interações ao seu site quando aplicada a um documento HTML.


## Sumário
* [Como guardar valores?](#id01)
* [Quais valores posso guardar?](#id02)
* [Como fazer contas com esses valores?](#id03)

## Como guardar valores? <a name="id01"></a>

Para guardar valores, seja para fazer um cálculo com ele ou mesmo enviar para o servidor, utilizamos declarações, que são estruturas compostas por tipo, nome e valor.

### Estrutura de uma declaração:

**tipo** *nomeDaDeclaracao* = **valorDaDeclaracao**

Como fica no código:

**var** *pessoa* = **'Daniela'**

### Tipos de declarações

Existem 3 tipos de declarações que podemos usar no JavaScript, cada uma com seu propósito:

   O tipo **VAR** é utilizado quando queremos guardar um valor que vai estar disponível para acessá-lo e alterá-lo em qualquer lugar do código, seu uso é bem perigoso, pois pode ser alterado em qualquer lugar e momento do código o que pode gerar erros, por isso não é recomendado seu uso.
   
   Exemplo: 
   `var valorInicial = 0;`
   
   
   Ok, não é recomendado usar o VAR, mas então o que uso caso precise armazenar um valor que vai ser alterado futuramente?

   Use o **LET**, pois esse tipo pode ser alterado sempre que necessário, porém somente dentro do seu escopo ou bloco.

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
   E se eu quiser declarar um valor que não vai mudar?

   Use o **CONST**, com esse tipo a declaração só pode ser criada uma vez com o seu um valor inicial, podendo ser lida e nunca alterado seu valor.
   
   Exemplo:

   ```javascript
   /* Aqui declaro a variável soma 
   como const, pois ela já inicia 
   com um valor, no caso uma operação 
   aritmética, que não irá ser alterada */
   const soma = 15 + 8;
   ```

## Quais valores posso guardar? <a name="id02"></a>

   Além dos tipos de declaração, também existe os tipos de valores/dados que podem ser armazenados nessas declarações.

   Exemplo:

   ```javascript
   /* Aqui declarei minhaVariavel com 
   o valor 2, ou seja ela é do tipo de 
   dado NUMBER, pois é um número */
   let minhaVariavel = 2;
   ```

   Os tipos de valores, são classificados por dois tipos:

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

   2. Tipo objeto:

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
        
        *Para acessar uma propriedade do objeto basta colocar o nomeDoObjeto.nomeDaPropriedade que você quer acessar.
        
        Exemplo:
        
        Quero acessar o nome do objeto pessoa coloco assim:
        
        `pessoa.nome // será exibido Dani`
        
        Também temos a opção de acessar o objeto como acessado um array, porém é usado em casos mais específicos:
        
        `pessoa['nome'] // será exibodo Dani`
        
      * **array**: é um objeto global usado na construção de listas:

        ```javascript
        const frutas = ['morango', 'laranja', 'banana'];
        ```
        
        *Para acessar uma propriedade do array, basta colocar o `nomeDoArray[índice]`, o índice é a ordem em que a propriedade está, que é sempre iniciada com o valor 0.
        
        Exemplo:
        
        Quero como retorno morango, e ele é o primeiro item coloco assim:
        
        ```javascript
         /* Como quero o primeiro item e o índice 
         começa com zero, coloco o zero no 
         valor do índice e é exibido morango` */
         frutas[0]
        ```
        
## Como fazer contas com esses valores? <a name="id03"></a>

Além de armazenar valores, por meio das declarações também conseguimos fazer contas, entre uma declaração e outra ou atribuindo valores números a uma declaração.
       
Exemplo:

`let resultado = 15 + 8;`

Agora se quisermos somar o valor de `resultado`com mais 1, podemos fazer assim:

`resultado++ // aqui é lido o valor de resultado primeiro e depois é adicionado mais 1 ao valor`

ou

`++resultado // aqui adiciona primeiro o valor 1 e depois o soma com o valor de resultado`

E se quisermos subtrair o valor de `resultado`por menos 1, é só trocar o + pelo -

Porém se quisermos, adicionar um valor diferente de 1, seja somando, subtraindo, multiplicando, ou dividindo o valor de soma, podemos fazer também de um forma reduzida, conforme mostrado na tabela abaixo:

| Normal              | Abreviado    |
| ------------------- | ------------ |
| `resultado = resultado + 3` | `resultado += 3` |
| `resultado = resultado - 3` | `resultado -= 3` |
| `resultado = resultado * 3` | `resultado *= 3` |
| `resultado = resultado / 3` | `resultado /= 3` |
        
