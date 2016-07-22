# Artigo - Herança

**Autor**: Marcos Antonio Martinez Florentin - [githubuser](https://github.com/marks88martinez)

**Data**: 1469201830220

A herança é uma forma de criar uma classe como uma versão especializada de uma ou mais classes (JavaScript permite apenas herança simples ) . A classe especializada é comunmente chamada de filha ou secundária, e o outro tipo é chamado de um dos pais ou primária. Em JavaScript herança é conseguida através da atribuição de uma instância da classe pai para a classe média , em seguida, a especialização é feita.

No exemplo a seguir se define a classe Estudiante como uma classe filha de Persona. Em seguida, redefinimos o método diHola () e adicionar o método diAdios ().

´´´js
// Nós definimos o construtor Persona
function Persona(primerNombre) {
  this.primerNombre = primerNombre;
}

// Nós adicionamos um par de métodos para Persona.prototype
Persona.prototype.caminar = function() {
  alert("Estou caminhando!");
};
Persona.prototype.diHola = function(){
  alert("Hola, Soy" + this.primerNombre);
};

// Definimos o construtor Estudiante
function Estudiante(primerNombre, asignatura) {
  // Nós chamamos o construtor pai , asseguramos (utilização Function#call) que "this" se
  // Estabeleceu com sucesso durante a chamada
  Persona.call(this, primerNombre);

  // Nós inicializamos as propriedades específicas de Estudiante
  this.asignatura = asignatura;
};

// Nós criamos o objeto Estudiante.prototype que herda de Persona.prototype
// Nota: Um erro comum é usar "new Persona()" para criar Estudiante.prototype
// Isso é errado por várias razões, e não menos que não estamos a gastar nada
// uma Persona a partir do argumento "primerNombre". O lugar certo para chamar Persona
// é arriba lá pra cima, onde chamamos Estudiante.
Estudiante.prototype = Object.create(Persona.prototype);

// Definimos a propriedade "constructor" para referenciar Estudiante
Estudiante.prototype.constructor = Estudiante;

// Substituir o método "diHola"
Estudiante.prototype.diHola = function(){
  alert(" Oi sou " + this.primerNombre + ". Estou estudando " + this.asignatura + ".");
};

// Nós adicionamos o método "diAdios"
Estudiante.prototype.diAdios = function() {
  alert("¡ Adeus !");
};

// Exemplos de utilização
var estudiante1 = new Estudiante("Carolina", "Física Aplicada");
estudiante1.diHola();    // mostra "Oi sou  Carolina. Estou estudando Física Aplicada."
estudiante1.caminar();   // mostra "Estou caminhando !"
estudiante1.diAdios();   // mostra "¡ Adeus !"

// Nós verificamos que os casos funcionam corretamente
alert(estudiante1 instanceof Persona);      // retorna true
alert(estudiante1 instanceof Estudiante);   // retorna true
´´´



