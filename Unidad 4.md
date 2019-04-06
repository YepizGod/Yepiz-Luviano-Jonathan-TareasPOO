# Yepiz Luviano Jonathan
# Unidad 4 (Polimorfismo)


### 1. Considera el siguiente fragmento de programa:
```c#
using System;
class A
    {
    public int a;
    public A()
        {
        a = 10;
        }
    public _______ string Display()
      {
      return a.ToString();
      }
    }
class B:A
   {
   public int b;
   public B():base()
   {
    b = 15;
   }
   }
 class Program
  {
   public static void Main()
   {
  A objA = new A();
  B objB = new B();
  Console.WriteLine(objA.Display()); ////  (1 )
  Console. WriteLine(objB.Display()); ////  (2)
  }
  }
   ```
### 1. ¿Qué valores imprimen las lineas (1) y (2)? 
Antes de redefinir se imprimen los valores de 10, 10.

### 1.2.  Redefine el método Display en el espacio indicado, una vez redefinido el método, ¿qué valores imprimen las lineas (1) y (2) ?
10 y 15

### 1.3. ¿Que palabra debes agregar en la linea (public _______ string Display()) al definir A.Display()?
virtual

### 2. Considera el siguiente fragmento de programa:
```c#
using System;
using System.Collections.Generic;
 public class Musico
    {
    public string nombre;
    public Musico (string n)
        {
         nombre = n;
        }
   public abstract void Afina(); 
   public virtual string Display()
      { 
       return nombre;
      }
   }
class Bajista; Musico
  {
    public string instrumento;
    public Bajista (string n, string i ) ......
    .........
    public _________ Afina()
      {
      ________________
      }
 }
class Guitarrista ____________
     {
     public instrumento;
     }
class Program
 {
  public static Main()
   {
  Musico musico = new Musico("Django"); (D)
  Bajista b = new Bajista("Flea");
  Guitarrista g = new Guitarrista("Santana");
  List<Musico> musicos = ____________________
  musicos.Add( b);
  musicos.Add(g);
  foreach ( _____in musicos______)___________
 // (m as IAfina).Afina()
 Console.ReadKey();
 }
}
```
#### 2.1 Completa el codigo
```c#
using System;
using System.Collections.Generic;
abstract class Musico
{
    public string nombre;
    public Musico(string n)
    {
        nombre = n;
    }
    public abstract void Afina();
    public string Display()
    {
        return nombre;
    }
}
class Bajista : Musico
{
    public string instrumento;
    public Bajista(string n, string i) : base(n)
    {
        this.instrumento = i;
    }
    public override void Afina()
    {
        Console.WriteLine("{0} afina el {1}", nombre, instrumento);
    }
}
class Guitarrista : Musico
{
    public string instrumento;
    public Guitarrista(string n, string i) : base(n)
    {
        this.instrumento = i;
    }
    public override void Afina()
    {
        Console.WriteLine("{0} afina el {1}", nombre, instrumento);
    }
}
class Program
{
    public static void Main()
    {
        //No se puede instanciar una objeto de una clase virtual
        //Musico m = new Musico("Django"); 
        Bajista b = new Bajista("Flea", "bajo acústico");
        Guitarrista g = new Guitarrista("Santana", "guitarra Yamaha");
        List<Musico> musicos = new List<Musico>();
        musicos.Add(b);
        musicos.Add(g);
        foreach (Musico musico in musicos)
        {
            Console.WriteLine(musico.Afina());
            musico.Afina();
        }
        Console.ReadKey();
    }
}
```

#### 2.2. Hay un error en uno de los puntos (A)(B)(C)(D). ¿Cuál es y por qué? 
El D, porque no se pueden crear objetos o instancias en esa clase

#### 2.3. ¿Qué método se debe implementar obligatoriamente en ambas clases y por qué?
El metodo afina, ya que por ser abstracto si no lo incluimos nos marcara siempre un error

#### 2.4. ¿Por qué no se ponen las llaves en (B)?, ¿Cuando si se pondrían?
Porque al ser un metodo abstracto este no necesita poseer un cuerpo, las llaves son utilizadas en otros metodos que nos retornen valor o en los void, pero en los abstractos no se deben de incluir.

#### 2.5. ¿Qué pasa si el método Afina() lo hacemos virtual en lugar de abstract?
Para empezar debemos de añadirle un cuerpo a nuestro metodo ya que en uno abstracto no los tenemos, despues tendriamos que utilizar el override para que este pudiera funcionar en las otras clases.

#### 3. Implementa el programa utilizando interfaces en lugar de herencia.
```c#
using System;
using System.Collections.Generic;

interface IAfinable
{
    void Afina();
}
abstract class Musico
{
    public string nombre;

    public Musico(string name)
    {
        nombre = name;
    }
    public string Display()
    {
        return nombre;
    }
}
class Bajista : Musico, IAfinable
{
    public string instrumento;
    public Bajista(string n, string i) : base(n)
    {
        this.instrumento = i;
    }
    public void Afina()
    {
        Console.WriteLine("{0} afina el {1}", nombre, instrumento);
    }
}
class Guitarrista : Musico, IAfinable
{
    public string instrumento;
    public Guitarrista(string n, string i) : base(n)
    {
        this.instrumento = i;
    }
    public void Afina()
    {
        Console.WriteLine("{0} afina la {1}", nombre, instrumento);
    }
}
class Program
{
    public static void Main()
    {
        Bajista b = new Bajista("Flea", "bajo acústico");
        Guitarrista g = new Guitarrista("Santana", "guitarra Yamaha");
        List<Musico> musicos = new List<Musico>();
        musicos.Add(b);
        musicos.Add(g);
        foreach (Musico musico in musicos)
        {
            Console.WriteLine(musico.Display());
            (musico as IAfinable).Afina();
        }
        Console.ReadKey();
    }
}
```

