# C# Uniqueness

## Written By- Zuhair Ahmed

### Instance Details:

An instance of a class in C# is an object that is created from a class and contains its own data and behavior. Here's a simple example in C# to create an instance of a class:

```csharp
class Dog
{
    public string Name { get; set; }
    public int Age { get; set; }
    
    public void Bark()
    {
        Console.WriteLine("Woof! Woof!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Creating an instance of the Dog class
        Dog myDog = new Dog();
        
        // Assigning values to the properties of the dog
        myDog.Name = "Buddy";
        myDog.Age = 5;
        
        // Calling a method on the dog instance
        myDog.Bark();
        
        Console.ReadLine();
    }
}
```

When the program is executed, it will create an instance of the `Dog` class and assign values to its properties. Then it will call the `Bark` method, which will display "Woof! Woof!" on the console.

### Static Details:

In C#, "static" is a keyword that is used to declare a member of a type as static. A static member is shared by all objects of the same type, rather than being unique to each instance of the type. This means that you can access a static member without having to create an instance of the type first. Here's an example:

```csharp
class MathHelper
{
    public static int Square(int number)
    {
        return number * number;
    }
}

class Program
{
    static void Main(string[] args)
    {
        int result = MathHelper.Square(5);
        Console.WriteLine(result); // Output: 25
    }
}
```

In this example, the method **`Square`** is declared as **`static`**, so it can be called directly from the **`MathHelper`** class without having to create an instance of the class. In the **`Main`** method, we call **`MathHelper.Square(5)`** to get the square of 5, which is 25.

### Dynamic Details:

The **`dynamic`** keyword in C# is used to specify that a variable or an object is dynamic, meaning that its type is not known at compile-time. Instead, the type is determined at runtime. The **`dynamic`** keyword allows you to write code that is more flexible and that can be easier to maintain since it can adapt to changes in the types of objects you are working with.

Here's an example that demonstrates how you can use the **`dynamic`** keyword in C#:

```csharp
class Program
{
    static void Main(string[] args)
    {
        dynamic x = 10;
        Console.WriteLine(x * 2); // Output: 20

        x = "Hello, World!";
        Console.WriteLine(x.Length); // Output: 13
    }
}
```

In this example, the variable **`x`** is declared as **`dynamic`**. On the first line, **`x`** is assigned the value 10, which is an **`int`**. On the second line, we perform a multiplication on **`x`** and the result is 20, which is the expected result for an **`int`**.

Later, **`x`** is assigned a value of type **`string`**. On the fourth line, we access the **`Length`** property of **`x`**, which is valid for strings, and the result is 13, which is the length of the string "Hello, World!".

Note that, while **`dynamic`** variables can make your code more flexible and easier to maintain, they can also make your code more difficult to debug and less performant, since the type checking is done at runtime instead of at compile-time. It's generally a good idea to use the **`dynamic`** keyword only when you have a specific use case for it and to avoid overusing it in your code.

### Overloading and Overriding Concept:

In C#, "overloading" and "overriding" are two different concepts that are used to create methods with the same name.

### Overloading

Method overloading allows you to have multiple methods with the same name, but with different parameters. The number of parameters, the data types of the parameters, or the order of the parameters can be different between the methods. The compiler will determine which method to call based on the number, types, and order of the arguments passed in.

Here's an example of method overloading in C#:

```csharp
class Calculator
{
    public int Add(int x, int y)
    {
        return x + y;
    }

    public double Add(double x, double y)
    {
        return x + y;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Calculator calculator = new Calculator();
        int resultInt = calculator.Add(1, 2);
        Console.WriteLine(resultInt); // Output: 3

        double resultDouble = calculator.Add(1.1, 2.2);
        Console.WriteLine(resultDouble); // Output: 3.3
    }
}
```

In this example, the **`Calculator`**class has two methods with the same name, **`Add`**, but with different parameters. The first method takes two **`int`**parameters and returns the sum of them, and the second method takes two **`double`**parameters and returns the sum of them.

### Overriding

Method overriding allows you to provide a new implementation for a method that is already defined in a base class. The new implementation must have the same name, return type, and parameters as the method in the base class. The **`override`** keyword is used to indicate that a method is intended to override a method in a base class.

Here's an example of method overriding in C#:

```csharp
class Shape
{
    public virtual void Draw()
    {
        Console.WriteLine("Drawing a Shape");
    }
}

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a Circle");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Shape shape = new Shape();
        shape.Draw(); // Output: Drawing a Shape

        Circle circle = new Circle();
        circle.Draw(); // Output: Drawing a Circle
    }
}
```

In this example, the **`Shape`** class has a method **`Draw`** with the **`virtual`** keyword, indicating that it can be overridden in a derived class. The **`Circle`** class inherits from **`Shape`** and provides its own implementation for the **`Draw`** method using the **`override`** keyword.

When we call the **`Draw`** method on an instance of **`Shape`**, it outputs "Drawing a Shape". When we call the **`Draw`** method on an instance of **`Circle`**, it outputs "Drawing a Circle", because the implementation in the **`Circle`** class overrides the implementation in the **`Shape`** class.

### Var and Dynamic

In C#, **`var`** and **`dynamic`** are two different concepts that are used to declare variables.

### **`var`**

The **`var`** keyword is used to declare implicitly typed variables in C#. This means that the compiler infers the type of the variable based on the value assigned to it. You can assign any value to a **`var`** variable, including values of different types, but the type of the variable will be determined based on the type of the value assigned to it, and it cannot be changed later.

Here's an example of using the **`var`** keyword in C#:

```csharp
var x = 10;
Console.WriteLine(x.GetType().Name); // Output: Int32

var y = "Hello, World!";
Console.WriteLine(y.GetType().Name); // Output: String
```

In this example, the variable **`x`** is declared using the **`var`** keyword and is assigned the value 10, which is of type **`int`**. The type of **`x`** is determined by the compiler as **`int`**.

The variable **`y`** is declared using the **`var`** keyword and is assigned the value "Hello, World!", which is of type **`string`**. The type of **`y`** is determined by the compiler as **`string`**.

### **`dynamic`**

The **`dynamic`** keyword in C# is used to specify that a variable or an object is dynamic, meaning that its type is not known at compile-time. Instead, the type is determined at runtime. The **`dynamic`** keyword allows you to write code that is more flexible and that can be easier to maintain, since it can adapt to changes in the types of objects you are working with.

Here's an example that demonstrates how you can use the **`dynamic`** keyword in C#:

```csharp
dynamic x = 10;
Console.WriteLine(x * 2); // Output: 20

x = "Hello, World!";
Console.WriteLine(x.Length); // Output: 13
```

In this example, the variable **`x`** is declared as **`dynamic`**. On the first line, **`x`** is assigned the value 10, which is an **`int`**. On the second line, we perform a multiplication on **`x`** and the result is 20, which is the expected result for an **`int`**.

Later, **`x`** is assigned a value of type **`string`**. On the fourth line, we access the **`Length`** property of **`x`**, which is valid for strings, and the result is 13, which is the length of the string "Hello, World!".

Note that, while **`dynamic`** variables can make your code more flexible and easier to maintain, they can also make your code more difficult to debug and less performant, since the type checking is done at runtime instead of at compile-time. It's generally a good idea to use the **`dynamic`** keyword only when you have a specific use case for it and to avoid overusing it in your code.

### Differences

- The **`var`** keyword is used to declare implicitly typed variables.
- The type of a **`var`** variable is determined by the compiler at compile-time based on the type of the expression used to initialize the variable.
- The type of a **`var`** variable cannot be changed once it has been determined.
- **`var`** variables can be assigned values of any type, but the type of the variable is determined based on the type of the value assigned to it.
- Using the **`var`** keyword can make your code more concise and readable, since the type of the variable is inferred by the compiler and does not need to be explicitly specified.

- The **`dynamic`** keyword is used to declare variables that are dynamically typed.
- The type of a **`dynamic`** variable is determined at runtime.
- The type of a **`dynamic`** variable can change during its lifetime.
- **`dynamic`** variables can be assigned values of any type, and the type of the variable will be determined at runtime based on the type of the value assigned to it.
- Using the **`dynamic`** keyword can make your code more flexible and easier to maintain since it allows you to work with values of different types at runtime.

### Params

The **`params`** keyword in C# is used to declare a method parameter that allows you to pass a variable number of arguments to the method. When a method parameter is declared with the **`params`** keyword, it creates an array that can hold any number of arguments of the specified type.

Here is an example of how you might use the **`params`** keyword to declare a method that calculates the sum of a variable number of integers:

```csharp
public static int Sum(params int[] numbers)
{
    int result = 0;
    foreach (int number in numbers)
    {
        result += number;
    }
    return result;
}
```

In this example, the **`Sum`** method takes a single parameter, **`numbers`**, which is declared with the **`params`** keyword. The type of the parameter is an array of integers, **`int[]`**. This means that you can pass any number of integer arguments to the **`Sum`** method when you call it.

You can call the **`Sum`** method in a number of different ways, depending on the number of arguments you want to pass:

```csharp
int result1 = Sum(1, 2, 3, 4, 5); // result1 is 15
int result2 = Sum(10, 20, 30); // result2 is 60
int result3 = Sum(); // result3 is 0
```

In the first example, the **`Sum`** method is called with five integer arguments, so the **`numbers`** parameter will be an array with five elements. In the second example, the **`Sum`** method is called with three integer arguments, so the **`numbers`** parameter will be an array with three elements. In the third example, the **`Sum`** method is called with no arguments, so the **`numbers`** parameter will be an empty array.

### Foreach Loop:

The **`foreach`** loop in C# is used to iterate over a collection of elements, such as an array or a list. The **`foreach`** loop is used to read the elements of a collection one by one and perform some action on each element.

Here is an example of how you might use a **`foreach`** loop to iterate over an array of integers and print each element to the console:

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
foreach (int number in numbers)
{
    Console.WriteLine(number);
}
```

In this example, the **`foreach`** loop iterates over the **`numbers`** array and assigns each element in turn to the **`number`** variable. The body of the loop, which is enclosed in curly braces, is then executed for each iteration of the loop, printing the value of **`number`** to the console.

The output of this code will be:

```csharp
1
2
3
4
5
```

The **`foreach`** loop is very useful when you want to iterate over a collection of elements and perform some action on each element, without having to worry about the index of the element in the collection. You can use the **`foreach`** loop with any collection that implements the **`IEnumerable`** or **`IEnumerable<T>`** interface, such as arrays, lists, and dictionaries.

### IEnumerable:

**`IEnumerable<T>`** is an interface in C# that defines a standard way of iterating over a collection of elements. The **`IEnumerable<T>`** interface defines a single method, **`GetEnumerator`**, which returns an object that implements the **`IEnumerator<T>`** interface. The **`IEnumerator<T>`** interface defines methods that allow you to iterate over the elements of a collection, such as **`MoveNext`** and **`Current`**.

Here is an example of a simple class that implements the **`IEnumerable<T>`** interface:

```csharp
public class MyList<T> : IEnumerable<T>
{
    private T[] _items = new T[10];
    private int _count;

    public void Add(T item)
    {
        if (_count == _items.Length)
        {
            Array.Resize(ref _items, _count * 2);
        }
        _items[_count++] = item;
    }

    public IEnumerator<T> GetEnumerator()
    {
        for (int i = 0; i < _count; i++)
        {
            yield return _items[i];
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }
}
```

In this example, the **`MyList<T>`** class implements the **`IEnumerable<T>`** interface by providing an implementation of the **`GetEnumerator`** method. The implementation of the **`GetEnumerator`** method uses the **`yield`** keyword to return each element of the **`_items`** array one by one.

You can use the **`MyList<T>`** class in a **`foreach`** loop, just like any other collection that implements the **`IEnumerable<T>`** interface:

```csharp
MyList<int> numbers = new MyList<int>();
numbers.Add(1);
numbers.Add(2);
numbers.Add(3);

foreach (int number in numbers)
{
    Console.WriteLine(number);
}
```

The output of this code will be: 1 2 3 . The **`IEnumerable<T>`**interface is a powerful tool in C#, allowing you to create your own collections and use them with the standard **`foreach`**loop, as well as with LINQ and other features of the .NET framework.

### List

A **`List<T>`** in C# is a collection that stores a list of elements of a specific type **`T`**. The **`List<T>`** class is part of the System.Collections.Generic namespace, and it provides a range of useful methods and properties for adding, removing, and accessing elements in the list.

Here is an example of how you might use a **`List<T>`** to store a list of integers:

```csharp
List<int> numbers = new List<int>();
numbers.Add(1);
numbers.Add(2);
numbers.Add(3);

foreach (int number in numbers)
{
    Console.WriteLine(number);
}
```

In this example, we create a new **`List<int>`** named **`numbers`** and add three elements to it using the **`Add`** method. We then use a **`foreach`** loop to iterate over the elements of the list and print each element to the console.

The output of this code will be:

```csharp
1
2
3
```

The **`List<T>`** class provides many other useful methods, such as **`Remove`**, **`RemoveAt`**, **`Insert`**, and **`Clear`**, that allow you to manipulate the elements in the list. You can also use the **`Count`** property to get the number of elements in the list, and the **`IndexOf`** method to find the index of a specific element in the list.

In addition to its convenient methods, the **`List<T>`** class is also very fast, since it is implemented as an array that automatically grows as elements are added. This makes it a great choice for many applications that require a dynamic collection of elements.

### Properties:

Properties in C# are a way of exposing member variables of a class in a controlled and encapsulated manner. Properties in C# allow you to set and retrieve the value of a member variable, while hiding the underlying implementation details.

Here is an example of a class with a property:

```csharp
public class Person
{
    private string _name;

    public string Name
    {
        get
        {
            return _name;
        }
        set
        {
            _name = value;
        }
    }
}
```

In this example, the **`Person`** class has a private member variable named **`_name`**, and a public property named **`Name`**. The property **`Name`** has a **`get`** accessor that returns the value of **`_name`**, and a **`set`** accessor that sets the value of **`_name`**. You can use the **`Person`** class as follows:

```csharp
Person person = new Person();
person.Name = "John Doe";
Console.WriteLine(person.Name);
```

The output of this code will be: John Doe . In this example, we create a new instance of the **`Person`** class and set the value of its **`Name`** property to "John Doe". We then retrieve the value of the **`Name`** property and print it to the console.

Properties in C# are a convenient way to expose member variables in a controlled and encapsulated manner, making it easier to maintain and modify your code. By using properties instead of public member variables, you can ensure that the implementation details of your class are hidden, making it easier to change the implementation without affecting client code.

### Auto-Properties:

Auto-properties in C# are a shorthand way of declaring a property that has a simple getter and setter. With auto-properties, you don't have to write the **`get`** and **`set`** accessors yourself. Instead, the C# compiler generates the getter and setter for you.

Here is an example of an auto-property:

```csharp
public class Person
{
    public string Name { get; set; }
}
```

In this example, the **`Person`** class has a property named **`Name`**, which is an auto-property. The **`Name`** property has a getter and setter, but you don't have to write them yourself. Instead, the C# compiler generates them for you.

You can use the **`Person`** class as follows:

```csharp
Person person = new Person();
person.Name = "John Doe";
Console.WriteLine(person.Name);
```

The output of this code will be: John Doe . In this example, we create a new instance of the **`Person`** class and set the value of its **`Name`** property to "John Doe". We then retrieve the value of the **`Name`** property and print it to the console.

Auto-properties are a convenient and concise way of declaring properties in C#. They are especially useful when you have simple properties that don't require any additional logic in their getter or setter. However, if you need to perform additional logic when the property value is retrieved or set, you'll need to use a regular property and write the getter and setter yourself.

### ReadOnly:

The **`readonly`** modifier in C# is used to declare a member of a class that can only be set once, either in the declaration or in the class constructor. A **`readonly`** member cannot be changed after it has been set, making it a way to ensure that the value of the member remains constant throughout the lifetime of the object.

Here is an example of a **`readonly`** field:

```csharp
public class Person
{
    public readonly string Name;

    public Person(string name)
    {
        Name = name;
    }
}
```

In this example, the **`Person`** class has a **`readonly`** field named **`Name`**. The **`Name`** field can be set only once, either in the declaration or in the class constructor. In this example, the **`Name`** field is set in the class constructor.

You can use the **`Person`** class as follows:

```csharp
Person person = new Person("John Doe");
Console.WriteLine(person.Name);
```

The output of this code will be: John Doe . In this example, we create a new instance of the **`Person`** class and pass in a value for the **`Name`** field in the constructor. We then retrieve the value of the **`Name`** field and print it to the console.

The **`readonly`** modifier is a convenient way to declare members of a class that should only be set once and remain constant throughout the lifetime of the object. By using **`readonly`** fields, you can ensure that the values of the fields remain unchanged, even if the object is modified elsewhere in your code.

### Constant:

A constant in C# is a value that can be assigned to a variable at compile-time and cannot be changed afterwards. The **`const`** keyword is used to declare a constant in C#.

Here is an example of a constant:

```csharp
public class Person
{
    public const string NAME = "John Doe";
}

```

In this example, the **`Person`** class has a constant named **`NAME`** with a value of "John Doe". The value of a constant must be a value that can be determined at compile-time, such as a string literal or a numeric constant.

You can use the **`Person`** class as follows:

```csharp
Console.WriteLine(Person.NAME);
```

The output of this code will be:

```csharp
John Doe
```

In this example, we retrieve the value of the **`NAME`** constant from the **`Person`** class and print it to the console.

Constants are a useful way to declare values that never change in your code. By using constants, you can ensure that the value of a variable remains the same throughout your application, even if it's used in multiple places. Constants can also help make your code more readable and maintainable, by allowing you to use meaningful names for values that are used throughout your code.

### Association

Association in C# is a term used to describe the relationship between classes, where one class uses another class. In other words, an instance of one class is associated with an instance of another class.

There are several types of associations in C#, including aggregation, composition, and inheritance.

Aggregation: This type of association occurs when one class has a reference to another class, but the referenced class can exist independently of the referencing class. An example of this type of relationship is a **`Student`** class that has a reference to a **`Subject`** class. A **`Student`** can have multiple **`Subject`**s, but a **`Subject`** can be assigned to multiple students.

Composition: This type of association occurs when one class contains the instance of another class. An example of this type of relationship is a **`Car`** class that contains an instance of an **`Engine`** class. When a **`Car`** instance is destroyed, the instance of the **`Engine`** is also destroyed.

Inheritance: This type of association occurs when a new class is derived from an existing class. An example of this type of relationship is a **`Manager`** class that is derived from an **`Employee`** class. The **`Manager`** class inherits the properties and methods of the **`Employee`** class.

Here's an example of aggregation in C#:

```csharp
class Student
{
    private string name;
    private List<Subject> subjects;

    public Student(string name)
    {
        this.name = name;
        subjects = new List<Subject>();
    }

    public void AddSubject(Subject subject)
    {
        subjects.Add(subject);
    }
}

class Subject
{
    private string name;

    public Subject(string name)
    {
        this.name = name;
    }
}
```

In this example, the **`Student`** class has a list of **`Subject`** objects, which represent the subjects that the student is taking. The **`AddSubject`** method is used to add a **`Subject`** object to the list of subjects. This is an example of an aggregation relationship because the **`Student`** class has reference to the **`Subject`** class, but a **`Subject`** can exist independently of a **`Student`**.
