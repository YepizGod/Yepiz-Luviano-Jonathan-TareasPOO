# Yepiz Luviano Jonathan
# Unidad 3 (Polimorfismo)


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




