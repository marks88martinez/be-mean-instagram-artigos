# Artigo
**autor**: Ramon Portela Santos


## Hoisting

Hoisting � o comportamento padr�o da linguagem JavaScript que move todas as declara��es de vari�veis ou fun��es para o topo do escopo. O hoist acontece como resultado de como � implementado o interpretador de c�digo, onde primeiro o interpretador procura pelas declara��es das vari�veis e fun��es e s� depois executa o c�digo. Ent�o mesmo que uma vari�vel seja usada antes de ser declarada o interpretador vai ler a declara��o dela primeiro.

**exemplo:**
```
numero = 10;
var numero;

funcaoQualquer();

function funcaoQualquer(){
   console.log("faz qualquer coisa");
}

```

## Closure

Closure � uma fun��o que � salva em mem�ria para ser referenciada depois mesmo ap�s ter encerrado sua execu��o.

**exemplo:**
```
function gerarMensagem(nome, idade) {
  var messagem = nome + ", que tem " + idade + " anos de idade, disse ol�!";

  return function exibir() {
    console.log(messagem);
  };
}

// gera o closure
var exibeMensagem = gerarMensagem("Bob", 47);

// faz uso da fun��o salva
exibeMensagem();

```
De acordo com o que aprendi das pesquisas eu usaria para encapsular fun��es dentro de outras, fazendo que elas sejam privadas e n�o acess�veis de qualquer parte do c�digo.

## Vari�vel Global

Vari�vel global � uma vari�vel que est� dipon�vel e acess�vel e todo o c�digo, podendo ser usando dentro de fun��es ou n�o.

**exemplo:**
```
var numero = 10;

mostraNumero();

function mostraNumero(){
   console.log(numero);
}

```

## Vari�vel por par�metro

Quando um par�metro � passado para uma fun��o o valor do par�metro � passado para dentro de uma vari�vel da fun��o que � chamado de argumento, caso n�o seja passado par�metro e a fun��o possua argumento o valor do argumento ser� undefined. Caso uma vari�vel global seja passada por par�metro, o argumento da fun��o receber� uma c�pia do conte�do da vari�vel e todas as altera��es feitas valer�o somente dentro do escopo da fun��o, e a vari�vel global permace inalterado. 

**exemplo:**
```
var numero = 10;

function funcaoQualquer(num){
   num = num + 5
   console.log(num);
   //vai ser exibido 15
}

modificaNumero(numero);

console.log(num);
//vai ser exibido 10

```

## Instancia��o usando uma IIFE

IIFE � sigla para �Immediately-Invoked Function Expression", ela funciona como uma fun��o normal por�m � executada de forma imediata, ela � bastante usada quando � preciso fazer algo com uma vari�vel tempor�ria, por�m fora de uma fun��o j� declara e tamb�m sem ter que instanciar uma nova vari�vel global.

Uma vari�vel pode receber o valor de uma IIFE se a IIFE retornar um valor e a vari�vel receber o resultado da fun��o.

Para passar uma vari�vel como par�metro para uma IIFE basta coloca-la nos parenteses ap�s a declara��o da IIFE, ela � copiada pra dentro do argumento da IIFE e seu valor s� � alterado no escopo da fun��o mantendo seu valor fora dela.

**exemplo:**
```
var numero = (function(num) {
    return num;
}(10));
console.log(numero);

```

## Considera��es

Com as pesquisas para este artigo sobre instacia��es foi poss�vel aprender mais sobre algumas particularidades do como funcionam as coisas no JavaScript 