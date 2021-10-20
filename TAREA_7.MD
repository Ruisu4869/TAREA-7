# Tarea #7

## Autor
1. Luis German Henao Ortiz

## Ejercicio 1

```javascript
class Person {
	constructor(nombre, edad, cedula) {
		this._nombre = nombre;
		this._edad = edad;
		this._cedula = cedula;
	}

	get nombre() {
		return this._nombre
	}

	set nombre(value) {
		this._nombre = value;
	}

	get edad() {
		return this._edad
	}

	set edad(value) {
		this._edad = value;
	}

	get cedula() {
		return this._cedula
	}

	set cedula(value) {
		this._cedula = value;
	}


	mostrar() {
		console.log(`Nombre: ${this.nombre}`);
		console.log(`Edad: ${this.edad}`);
		console.log(`Cedula: ${this.cedula}`);
	}

	es_mayor_de_edad() {
		if (this.edad >= 18) {
			console.log('Es mayor de edad');
		}
		else {
			console.log('NO es mayor de edad');
		}
	}
}

let persona = new Person('Juan', 20, '1002563489');	

persona.mostrar();
persona.es_mayor_de_edad();

```

![I1](https://github.com/Ruisu4869/TAREA-7/blob/master/E%201.png)

## Ejercicio #2

```javascript
class Cuenta {
	constructor(titular, cantidad) {
		this.titular = titular;
		this.cantidad = cantidad;
	}

	validacion() {
		while (this.titular.length == 0) {
			console.log('El titular no puede estar vacio');
			this.titular = prompt('Ingrese el titular: ');
			break;
		}		
	}

	mostrar() {
		console.log(`Titular: ${this.titular}`);
		console.log(`Cantidad: ${this.cantidad}`);
	}

	ingresar(quan) {
		if (quan > 0) {
			this.cantidad = this.cantidad + quan;
		}
		return this.cantidad
	}

	retirar(retiro) {
		this.cantidad = this.cantidad - retiro;
		return this.cantidad
	}
}

const pers = new Cuenta('Carlos', 0);

quan = prompt('Ingrese la cantidad: ');
pers.ingresar(quan);
pers.validacion();
pers.mostrar();
retiro = prompt('Cuanto va a retirar: ');
pers.retirar(retiro);
pers.mostrar();
```

![I2](https://github.com/Ruisu4869/TAREA-7/blob/master/E%202.png)

## Ejercicio #3

```javascript
class Formula {
	constructor(resul) {
		this.resul = resul;
	}

	sumar(num1, num2) {
		this.resul = num1 + num2;
		console.log('La suma es: ' + this.resul);
	}

	fibonacci(cant) {
		var numa = 0;
		var numb = 1;
		var res = 0;
		for (var i=2; i<=cant; i++) {
			res = numa + numb;
			numa = numb;
			numb = res;
			console.log('Serie Fabonacci: ' + res);
		}
	}

	operacion_modulo(cant) {
		var resul = 0;
		for (var i=0; i<=cant; i++) {
			resul = i%2;
			if (resul==0) {
				console.log(i);
			}	
		}
	}

	primos(cant) {
		for (var i=0;i<=cant;i++) {
			var conti = 0;
			for (var u=2;u<i;u++) {
				if(i%u == 0) {
					conti = 1;
					break;
				}
			}
			if(i>1 && conti == 0) {
				console.log(i + ' es primo');
			}
		}
	}
}

const oper = new Formula;

sum1 = prompt('Ingrese un numero: ');
sum2 = prompt('Ingrese otro numero: ');
cant = prompt('Ingrese una cantidad: ');
oper.sumar(sum1, sum2);
oper.fibonacci(cant);
oper.operacion_modulo(cant);
oper.primos(cant);

```

![I3](https://github.com/Ruisu4869/TAREA-7/blob/master/E%203.png)

## Ejercicio #4


```javascript
class Persona {
	constructor(nombre, edad, dni, sexo, peso, altura) {
		this.nombre = nombre;
		this.edad = edad;
		this.dni = dni;
		this.sexo = sexo;
		this.peso = peso;
		this.altura = altura;
	}

	calcularIMC() {
		var pesoIdeal = this.peso/(this.altura*this.altura);
		if (pesoIdeal < 20) {
			console.log('-1');
		}
		else if (pesoIdeal >= 20 && pesoIdeal <= 25 ) {
			console.log('0');
		}
		else {
			console.log('1');
		}
	}

	esMayorDeEdad() {
		if (this.edad >= 18) {
			console.log('Es mayor de edad: ' + true);
		}
		else {
			console.log('No es mayor de edad: ' + false);
		}
	}

	comprobarSexo() {
		if (this.sexo == 'h') {
			console.log('Es hombre');
		}
		else if (this.sexo == 'm') {
			console.log('Es mujer');
		}
		else {
			console.log('Es hombre')
			this.sexo = 'h';
		}
		return this.sexo
	}

}

const people = new Persona('Andres', 25, '1002563489', 'j', 75, 1.52);

people.calcularIMC();
people.esMayorDeEdad();
people.comprobarSexo();

```

![I4](https://github.com/Ruisu4869/TAREA-7/blob/master/E%204.png)


## Ejercicio #5


```javascript

class Contraseña {
	constructor(longitud, password) {
		this.longitud = longitud;
		this.password = password;
	}

	esFuerte() {
		var space = false;
		var cont = 0;
		var numeros = [0,1,2,3,4,5,6,7,8,9];
		var letraMinus = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
		var letraMayus = ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'];
		var caracterEsp = ['-','_','*','/'];

		while (!space && (cont<this.password.length)) {
			if (this.password.charAt(cont) == ' ') {
				space = true;
				cont++
			}
			break;
		}
		if (space) {
			console.log('La contraseña no puede tener espacios vacios ' + false);
			return false
		}
		else if (this.password.length == 0) {
			console.log('No puede estar en blanco ' + false);
			return false
		}
		else if (this.password.charAt() != numeros) {
			return console.log(false)
		}
		else if (this.password.charAt() != letraMinus) {
			return console.log(false)
		}
		else if (this.password.charAt() != letraMayus) {
			return console.log(false)
		}
		else if (this.password.charAt() != caracterEsp) {
			return console.log(false)
		}
		else {
			return console.log(true)
		}
	}

	generarPassword(longitud, tipo) {
		switch(tipo) {
			case '':
				break;
			default:
				characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
				break;
		}
		var pass = "";
		for (var i=0;i<longitud;i++) {
			if(tipo == '') {
				pass += String.fromCharCode((Math.floor((Math.random() * 100)) % 94) + 33);
        	}
        	else {
            	pass += characters.charAt(Math.floor(Math.random()*characters.length));   
        	}
		}
		return pass
	}

	seguridadPassword() {
		if (this.password.length >= 0 && this.password.length <= 5) {
			console.log('Contraseña debil');
		}
		else if (this.password.length >= 7 && this.password.length <= 10) {
			console.log('Contraseña media');
		}
		else if (this.password.length >= 11 && this.password.length <= 20) {
			console.log('Contraseña fuerte');
		}
		else {
			console.log('No puede tan grande');
		}
	}
}

const contra = new Contraseña;

var contraseñaNueva = 'Juan1256/*/';
var longitudNueva = 15;
contra.password = contraseñaNueva;
contra.longitud = longitudNueva;

contra.esFuerte();
contra.generarPassword(longitudNueva, '');
contra.seguridadPassword();

```

![I5](https://github.com/Ruisu4869/TAREA-7/blob/master/E%205.png)

## Ejercicio #6

```javascript
class Contador{
    reset(){
        this.numero = 0;
    }
    inc(){
        this.numero ++;
    }
    dec(){
        this.numero --;
    }
    valorActual(ent1){
        if(ent1 != null) {
            this.numero = ent1;
        }else{
            console.log(this.numero);
        }
    }
}

const contador1 = new Contador();
contador1.reset();
contador1.valorActual(20);
contador1.inc();
contador1.inc();
contador1.dec();
contador1.inc();
contador1.valorActual();
```

![i6](https://github.com/Ruisu4869/TAREA-7/blob/master/E%206.png)

## Ejercicio #7

```javascript
class Contador{
    constructor(id){
        this.id = id;
    }
    reset(){
        this.numero = 0;
        this.id=0;
    }
    inc(){
        this.numero ++;
        this.id=1;
    }
    dec(){
        this.numero --;
        this.id=2;
    }
    valorActual(ent1){
        this.id=3;
        if(ent1 != null) {
            this.numero = ent1;
        }else{
            console.log(this.numero);
        }
    }
    ultimoComando(){
        let day;
        switch(this.id){
            case 0:
                day = "Reset";
                break;
            case 1:
                day = "Incremento";
                break;
            case 2:
                day = "Decremento";
                break;
            case 3:
                day = "Actualizacion";
                break;
        }
        console.log(day);
    }
}

const contador1 = new Contador();
contador1.reset();
contador1.valorActual(30);
contador1.inc();
contador1.inc();
contador1.dec();
contador1.inc();
contador1.valorActual();
contador1.inc();
contador1.ultimoComando();
```

![i7](https://github.com/Ruisu4869/TAREA-7/blob/master/E%207.png)


## Ejercicio #8

```javascript
class Dragon {
	constructor(energia) {
		this.energia = energia;
	}

	comer(comida) {
		var resulEnergia = comida*4
		this.energia = resulEnergia;
		return this.energia
	}

	volar(distancia) {
		var resulDist = 0;
		if (distancia > this.energia) {
			console.log('Chimuela no puede volar');
		}
		else {
			resulDist = this.energia-distancia-10;
			this.energia = resulDist;
		}
		return this.energia
	}

	energy() {
		console.log('La energia de Chimuela es: ' + this.energia + ' Joules');
	}
}

const chimuela = new Dragon(0)

chimuela.comer(1200);
chimuela.volar(20);
chimuela.volar(50);
chimuela.energy();
```

![i8](https://github.com/Ruisu4869/TAREA-7/blob/master/E%208.png)


## Ejercicio #9

```javascript
class Dragon {
	constructor(energia) {
		this.energia = energia;
	}

	comer(comida) {
		var resulEnergia = comida*4
		this.energia = resulEnergia;
		return this.energia
	}

	volar(distancia) {
		var resulDist = 0;
		if (distancia > this.energia) {
			console.log('Chimuela no puede volar');
		}
		else {
			resulDist = this.energia-distancia-10;
			this.energia = resulDist;
		}
		return this.energia
	}

	energy() {
		console.log('La energia de Chimuela es: ' + this.energia + ' Joules');
	}

	estaDebil() {
		if (this.energia < 50) {
			console.log('Chimuela esta debil');
		}
		else {
			console.log('Chimuela esta bien');
		}
	}

	estaFeliz() {
		if (this.energia >= 500 && this.energia <= 1000) {
			console.log('Chimuela esta feliz');
		}
		else {
			console.log('Chimuela esta bien');
		}
	}

	cuantoQuiereVolar() {
		var resulCuenta = this.energia/5;
		if (this.energia >= 300 && this.energia <= 400) {
			resulCuenta = resulCuenta + 10;
		}
		if (this.energia%20 == 0) {
			resulCuenta = resulCuenta + 15;
		}
		console.log('Quiere volar '+ resulCuenta + ' Km')
	}
}

const chimuela = new Dragon(0)

chimuela.comer(162);
chimuela.volar(20);
chimuela.volar(50);
chimuela.energy();
chimuela.estaDebil();
chimuela.estaFeliz();
chimuela.cuantoQuiereVolar();
```

![I9](https://github.com/Ruisu4869/TAREA-7/blob/master/E%209.png)

## Ejercicio #10

```javascript
class calculadora{
    constructor(carga,suma,resta,multiplicacion,valorActual){
        this.carga=carga;
        this.suma=suma;
        this.resta=resta;
        this.multiplicacion=multiplicacion;
        this.valorActual=valorActual;
    }
    cargar(ent1){
        this.resultado = ent1;
    }
    sumar(ent2){
        this.resultado = this.resultado + ent2;
    }
    restar(ent2){
        this.resultado =this.resultado - ent2;
    }
    multiplicar(ent2){
        this.resultado = this.resultado* ent2;
    }
    valorActuali(){
        console.log(this.resultado);
    }
}

calc = new calculadora();
calc.cargar(0);
calc.sumar(4);
calc.multiplicar(5);
calc.restar(8);
calc.multiplicar(2);
calc.valorActuali();
```

![I10](https://github.com/Ruisu4869/TAREA-7/blob/master/E%2010.png)


## Ejercicio #11

```javascript
class Libro{
    constructor(tituloLibro, autorLibro, numEjemplares, numEjemplaresPrestamo){
        this.titulo = tituloLibro;
        this.autor = autorLibro;
        this.ejemplares = numEjemplares;
        this.ejemplaresPrestamo = numEjemplaresPrestamo;
    }
    prestamo(){
        if(this.ejemplares>=1){
            this.ejemplaresPrestamo ++;
            this.ejemplares --;
            console.log(true);
        }else{
            console.log(false);
        }
    }
    devolucion(){
        if(this.ejemplares>=1 || this.ejemplaresPrestamo>=1){
            this.ejemplaresPrestamo --;
            this.ejemplares ++;
        }
    }
    toString(){
        console.log(
            this.titulo,
            this.autor,
            this.ejemplares,
            this.ejemplaresPrestamo
        );
    }
}

let libro1 = new Libro("Juana de macho", "Luis German Henao", 5, 0);
libro1.prestamo();
libro1.prestamo();
libro1.devolucion();
libro1.toString();
```

![I11](https://github.com/Ruisu4869/TAREA-7/blob/master/E%2011.png)


## Ejercicio #12

```javascript
class Juego {
	constructor(potencia, coraza) {
		this.potencia = potencia;
		this.coraza = coraza;
	}

	potencia() {
		if (this.potencia < 0 && this.potencia > 100) {
			console.log('La potencia no es un valor accesible');
		}
	}

	coraza() {
		if (this.coraza < 0 && this.coraza > 20) {
			console.log('La coraza no es un valor accesible');
		}
	}

	pilaAtomica() {
		var aumento = this.potencia + 25;
		if (aumento > 100) {
			aumento = 100;
		}
		this.potencia = aumento;
		return this.potencia
	}

	encontrarEscudo() {
		var corazaAumento = this.coraza + 10;
		if (corazaAumento > 20) {
			corazaAumento = 20;
		}
		this.coraza = corazaAumento;
		return this.coraza
	}

	recibirAtaque(daño) {
		var descuento;
		if (this.coraza < daño) {
			var bajo = this.coraza - daño;
			descuento = this.potencia + bajo;
			if (this.potencia == 0) {
				console.log('Game Over');
			}
			this.coraza = 0;
			this.potencia = descuento;
			return this.coraza
			return this.potencia
		}
		else {
			bajo = this.coraza - daño;
			this.coraza = bajo;
			return this.coraza
		}
	}

	mostrar() {
		console.log('La potencia actual es: ' + this.potencia);
		console.log('La coraza actual es: ' + this.coraza);
	}

}

const enterprice = new Juego(50,5);

enterprice.pilaAtomica();
enterprice.encontrarEscudo();
enterprice.pilaAtomica();
enterprice.recibirAtaque(35);
enterprice.mostrar();
```

![I12](https://github.com/Ruisu4869/TAREA-7/blob/master/E%2012.png)

## Ejercicio #13

```javascript
class Juego {
	constructor(potencia, coraza) {
		this.potencia = potencia;
		this.coraza = coraza;
	}

	potencia() {
		if (this.potencia < 0 && this.potencia > 100) {
			console.log('La potencia no es un valor accesible');
		}
	}

	coraza() {
		if (this.coraza < 0 && this.coraza > 20) {
			console.log('La coraza no es un valor accesible');
		}
	}

	pilaAtomica() {
		var aumento = this.potencia + 25;
		if (aumento > 100) {
			aumento = 100;
		}
		this.potencia = aumento;
		return this.potencia
	}

	encontrarEscudo() {
		var corazaAumento = this.coraza + 10;
		if (corazaAumento > 20) {
			corazaAumento = 20;
		}
		this.coraza = corazaAumento;
		return this.coraza
	}

	recibirAtaque(daño) {
		var descuento;
		if (this.coraza < daño) {
			var bajo = this.coraza - daño;
			descuento = this.potencia + bajo;
			if (this.potencia == 0) {
				console.log('Game Over');
			}
			this.coraza = 0;
			this.potencia = descuento;
			return this.coraza
			return this.potencia
		}
		else {
			bajo = this.coraza - daño;
			this.coraza = bajo;
			return this.coraza
		}
	}

	mostrar() {
		console.log('La potencia actual es: ' + this.potencia);
		console.log('La coraza actual es: ' + this.coraza);
	}

	fortalezaDefensiva() {
		var maximo = this.potencia + this.coraza;
		console.log('La fortaleza defensiva maxima es ' + maximo);
	}

	necesitaFortalecerse() {
		if (this.potencia < 20 && this.coraza == 0) {
			console.log(true);
		}
		else {
			console.log(false);
		}
	}

	fortalezaOfensiva() {
		if (this.potencia < 20) {
			console.log('Su fortaleza ofensiva es 0');
		}
		else {
			var fuerza = (this.potencia-20)/2;
			console.log('Su fortaleza ofensiva es '+ fuerza);
		}
	}

}

const enterprice = new Juego(50,5);

enterprice.pilaAtomica();
enterprice.encontrarEscudo();
enterprice.pilaAtomica();
enterprice.recibirAtaque(35);
enterprice.mostrar();
enterprice.fortalezaDefensiva();
enterprice.necesitaFortalecerse();
enterprice.fortalezaOfensiva();

```

![I13](https://github.com/Ruisu4869/TAREA-7/blob/master/E%2013.png)


## Ejercicio #14

```javascript

class Taller {
	constructor(cambios, revoluciones) {
		this.cambios = cambios;
		this.revoluciones = revoluciones;
	}

	arrancar() {
		var marchas = 1;
		var rev = 500;
		this.cambios = marchas;
		this.revoluciones = rev;
		console.log('El coche esta en '+ marchas + ' cambio');
		console.log('El coche esta a '+ rev +' RPM');
		return this.cambios
		return this.revoluciones
	}

	subirCambio() {
		var subirMarcha = this.cambios + 1;
		if (this.cambios > 5) {
			this.cambios = 5;
			console.log('No hay mas cambios');
		}
		else {
			this.cambios = subirMarcha;
		}
		this.revoluciones = 2000;
		return this.cambios
		return this.revoluciones
	}

	bajarCambio() {
		var bajarMarcha = this.cambios - 1;
		if (this.cambios < 0) {
			this.cambios = 0;
			console.log('No hay mas cambios');
		}
		else {
			this.cambios = bajarMarcha;
		}
		this.revoluciones = 3500;
		return this.cambios
		return this.revoluciones
	}

	subirRPM(rpmS) {
		var subirRpm = this.revoluciones + (100*rpmS);
		if(this.revoluciones > 5000) {
			this.revoluciones = 5000;
			console.log('No puede subir mas las revoluciones');
		}
		else {
			this.revoluciones = subirRpm;
		}
		return this.revoluciones
	}

	bajarRPM(rpmB) {
		var bajarRpm = this.revoluciones - (100*rpmB);
		if (this.revoluciones < 0) {
			this.revoluciones = 500;
			console.log('El coche se mantiene encendido');
		}
		else {
			this.revoluciones = bajarRpm;
		}
		return this.revoluciones
	}

	velocidad() {
		var vel = (this.revoluciones/100)*(0.5 +(this.cambios/2));
		console.log('La velocidad es '+ vel +' Km/h');
	}

	consumoActualPorKm() {
		var consumo = 0.05;
		var consumoActual;
		if (this.revoluciones >= 3000) {
			consumoActual = consumo*((this.revoluciones - 2500)/500);
			if (this.revoluciones < 4000) {
				consumoActual = consumoActual*2;
			}
			else {
				consumoActual = consumoActual*3;
			}
			console.log('El consumo actual es de '+ consumoActual +' L/Km');
		}
		else {
			console.log('El consumo actual es de '+ consumo +' L/Km');
		}
		console.log('El coche esta en '+ this.cambios);
		console.log('El coche esta a '+ this.revoluciones);
		return consumoActual
	}
}

const coche = new Taller(0,0);

coche.arrancar();
coche.subirRPM(30);
coche.subirCambio();
coche.subirRPM(30);
coche.subirCambio();
coche.subirRPM(30);
coche.subirCambio();

coche.bajarRPM(20);
coche.bajarCambio();

coche.velocidad();
coche.consumoActualPorKm();

```

![I14](https://github.com/Ruisu4869/TAREA-7/blob/master/E%2014.png)