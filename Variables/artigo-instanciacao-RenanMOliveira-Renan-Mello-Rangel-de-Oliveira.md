#Artigo

**autor:** Renan Mello Rangel de Oliveira

##Hoisting

**Hoisting** � a forma com que a linguagem JavaScript lida por padrao com as vari�veis declaradas no meio do escopo, levando-as diretamente ao inicio do mesmo. O hoisting acontence atrav�s do interpretador da linguagem que antes da execu��o do codigo procura por todas as vari�veis no condigo, isso permite o uso da variavel antes de sua instacia��os.

**exemplo:**
```
menssagem = "Ol� a todos do be-mean";
var menssagem;

funcaoHello();

function funcaoHello(){
   alert(menssagem);
}
```

##Closure

**Closure** � uma fun��o que ap�s ser encerrada ainda pode ser chamada pois ela est� salvada na mem�ria.

**exemplo:**
```
function gerarMensagem() {
  menssagem = "Ol� a todos do be-mean";

  return function exibir() {
    console.log(messagem);
  };
}
var exibeMensagem = gerarMensagem();

exibeMensagem();

O closure pode ser usado para encapsular fun��es deixando-as pricadas aquela funcao, ou seja, fazendo com que ela nao fique acess�vel de qualquer parte do codigo

```

##Vari�vel Global

Vari�vel global � uma vari�vel que est� dipon�vel e acess�vel e todo o c�digo. 

**exemplo:**
```

var numero = 10;

mostraNumero();

function mostraNumero(){
   console.log(numero);
}
```

##Vari�vel por par�metro

Quando o valor de uma variavel � passada por parametro, fazendo com que a assinatura da fun��o tenha um parametro que recebe o valor da que foi referenciada, esse valor recebido � chamado de argumento. Caso a funcao chamada tenha um argumento, mas em sua chamada o argumento nao foi passado o valor recebido ser� undefined.Uma variavel global pode ser usada para passagem de parametro por uma funcao, porem quando isso acontece, o argumento recebido � apenas uma copia da mesma, inalterando seu valor inicial.

**exemplo:**
```
function monstraMenssagem(menssagem){
   alert(menssagem);
}

monstraMenssagem("Ol� a todos do be-mean");
```

##Instancia��o usando uma IIFE

IIFE � sigla para �Immediately-Invoked Function Expression", ela funciona como uma fun��o normal por�m � executada de forma imediata, ela � bastante usada quando � preciso trabalhar com variaveis auxiliates ou temporarias. Uma variavel pode receber o valor de uma IIFE caso a mesma retorne um valor.Para passar uma vari�vel como par�metro para uma IIFE basta coloca-la nos parenteses ap�s a declara��o da IIFE.A variavel passada por parametro pra IIFE s� � alterada dentro do escopo da mesma fun��o.

**exemplo:**
```

var numero = (function(num) {
    return num;
}(10));
console.log(numero);
```

##Considera��es

Atrav�s da pesquisa realizada sobre instancia��es pude aprender e aprofundar o meu conhecimentro sobre os recursos de instancia��es de variaveis 