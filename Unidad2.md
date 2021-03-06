# Yepiz Luviano Jonathan

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

Link: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/new-operator

## Referencia al objeto actual. 

### Escribe un programa donde utilices this para obtener acceso a miembros con el fin de evitar ambigüedades con nombres similares.

``` c#
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
       '''
       
  ### Escribe un programa donde se utilice this como parámetro.
  
   ```c#
    class Persona{
    
        public string name;
        
        public int edad;
        
        public void Imprime()
        
        {
            Console.WriteLine("Mi nombre es" + this.name ,"y tengo" +this.edad);
        }
    }
    ```
    
   ## Métodos: declaración, mensajes, paso de parámetros, retorno de valores.
   
   ### Parámetros de métodos.
   
   Para declarar una parametro de metodo se utilizan las siguientes palabras:
   params: Especifica que este parámetro puede tomar un número variable de argumentos.
   in : Se puede leer mediante el método llamado.
   ref: Puede ser leído o escrito por el método llamado.
   out: Se escribe mediante el método llamado.
  
  Link: https://docs.microsoft.com/es-es/dotnet/csharp/language-reference/keywords/method-parameters
  
  ### Params.
  
  Es una palabra clave para declarar un metodo que ya observamos anteriormente, este declaracion solo puede soportar matrices unidimensionales,   ademas que no permite parametros adicionales una vez declarado.
  Para utilizarlo se debe declarar de la siguiente forma dentro del metodo Main.
  
  UseParams();

  Link: https://docs.microsoft.com/es-es/dotnet/csharp/language-reference/keywords/params
  
  ### Out.
  
 Es un declarador de metodos que nos ayuda a transferir una referencia en lugar de otorgar un valor y en las declaraciones con    parametros de tipo generico este sera covariante.
 
 Link: https://docs.microsoft.com/es-es/dotnet/csharp/language-reference/keywords/out
 
 ### Ref.
 
 Nos indica que un valor fue pasado por medio de referencia. Para hacer este cambio necesitamos escribir ref para que nos indique que fue intercambiado por referencia, estoy como consecuencia nos da que cualquier cambio que hagamos se vera reflejado en nuestro metodo de llamada. Los valores que el metodo ref trae devuelta son en referencia al autor de la llamada.
 
 Link : https://docs.microsoft.com/es-es/dotnet/csharp/language-reference/keywords/ref
 
 ## Constructores y destructores: declaración, uso y aplicaciones.
 
 Los constructores tienen el mismo nombre que el de la clase y su principal funcion es inicializar datos. Cuando un constructor no tiene ningun parametro establecido se le conoce como constructor predeterminado. Si una clase no es estatica y no creo un constructor se le asigna uno publico automaticamente.
 
 Ejemplo de un constructor:
 
 public Employee(int annualSalary)
    {
        salary = annualSalary;
    }
    En cuestion a los tipos struct, quedaria de la siguiente manera:
    
    int i = new int();
Console.WriteLine(i);

    Los constructores pueden llamar a la clase base. Finalmente los constructores pueden ser publicos, privados ,protegidos y estaticos  dependiendo de su uso.
 
 
## Sobrecarga de operadores: Concepto y utilidad, operadores unarios y binarios.

using System;
using System.Collections.Generic;

class Dado
{
    private string color;
    private int valor;
    

    public Dado(string color, int valor)
       
    {
        this.color = color;
        this.valor = valor;
        
    }
    public void imprime()
    {
        Console.WriteLine("{0}-:{1}", color,
           valor);
    }
    public static bool operator <(Dado a, int valor)
    {
        return a.valor < valor;
    }
    public static bool operator> (Dado a, int valor)
    {
        return a.valor > valor;
    }

    public static bool operator ==(Dado a, int valor)
    {
        return a.valor == valor;

    }
    public static bool operator !=(Dado a, int valor)
    {
        return a.valor != valor;
    }
}

class Program
{
    static void Main()
    {
        List<Dado> dados = new List<Dado>();

        dados.Add(new Dado("Verde", 5));
        dados.Add(new Dado("Azul", 5));
        dados.Add(new Dado("Rojo", 2));

        foreach (var d in dados)
        {
            if (d == 2)
                d.imprime();
        }
        Console.ReadKey();
        }
    }
    
