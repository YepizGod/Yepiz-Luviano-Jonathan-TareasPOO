
# Unidad 2. Clases y Objetos

## Declaración de clases: atributos, métodos, encapsulamiento.
Una clase o estructura es donde se encapsulan los datos y comportamientos de los miembros, ya sea de la clase o de la estructura.
Estas nos ayudan para crear instancias u objetos y poder asignarles atributos a nuestra conveniencia. Tambien hay que recordar que una clase es una referencia y que las estructuras son un valor.
Una clase se utiliza cuando sabemos que modificaremos datos de los objetos, mientras que con las estructuras no.

La encapsulacion nos ayuda para restringir el acceso de los miembros que quieran modificar algo fuera de la clase o estructura.

El concepto de accesibilidad es muy importante ya que es lo que nos indica hasta donde tenemos acceso fuera de la clase, puede haber tres tipos de accesos uno es el private que es el mas comun y viene predeterminado, el public el cual da acceso total fuera de la clase y el protect.

Herencia, consiste en transmitir todos los miembros de la clase hacia otra exceptuando los constructores y finalizadores. Se utiliza la herencia para poder crear una clase base, la cual heredara sus miembros a otras.
Finalmente las clases pueden ser de distintos tipos los cuales serian los siguientes, los gericos, estaticos, anidados, parciales y anonimos.

Link : https://docs.microsoft.com/es-es/dotnet/csharp/programming-guide/classes-and-structs/index

## Instanciación de una clase.
El operador new sirve para poder crear objetos o invocar instancias. Este operador puede tener multiples usos como en algun constructor por default pero principalmente se utiliza para la creacion de objetos, la sintaxis para crear un objeto seria la siguiente:

(El nombre de la clase)(el nombre que se le quiera dar al objeto) = new (El nombre de la clase)(variables que se le hayan asignado);

Persona a = new Persona("Pedro");

Link> https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/new-operator

## Referencia al objeto actual. 

### Escribe un programa donde utilices this para obtener acceso a miembros con el fin de evitar ambigüedades con nombres similares.

    class Persona
    
    {
        public string nombre
        
        public int edad;
        
        public Persona(string n, int edad)
        {
            this.nombre = n;
            
            this.edad = edad;
            
        }
        public void Imprime()
        
        {
        Console.WriteLine("Mi nombre es " + nombre)
        
        }
  ### Escribe un programa donde se utilice this como parámetro.
  
