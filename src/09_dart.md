# Dart

- [Print](#print)
- [Variables](#variables)
- [Data types](#data-types)
- [Control flow](#control-flow)
- [Functions](#functions)
- [Classes](#classes)
- [Interfaces](#interfaces)
- [Generics](#generics)
- [Async](#async)
- [Concurrency](#concurrency)
- [Error handling](#error-handling)

### Print

```dart
var name = "world";
print('Hello $name');
print('Hello ${name}');
```

### Variables

```dart
var x = 'Smith';
String x = 'Bob'; // typed
final x = 42; // immutable
const x = 42; // immutable at compile-time
int x = optionalValue() ?? exprIfNull; // default operator
int x ??= 4; // fallback assignment operator
var x = condition ? exprIfTrue : exprIfFalse // conditional operator
```

### Data types

```dart
// Basic types
String x;
int x:
double x;
bool x;

// List
var myList = new List(5) // fixed length
var myList = [1, 2, 3] // growable length
myList[0] = 'value' // initialize

// Map
var myMap = { 'key1': 'value1', 'key2': 'value2' };
Map<String, String> myMap = { 'key1': 'value1', 'key2': 'value2' }; // typed

// Enum
enum Color { Red, Green, Blue };
```

### Control flow

```dart
// for loop
for (var i = 0; i <= 3; i++) {
    print(i);
}

// for ... in loop
for (car in cars) {
    print(car);
}

// while loop
while (i <= 5) {
    print(i);
    i++;
}

// do ... while loop
do {
    print(i);
    i++;
}
while (i <= 5);

// if-else
if (a < b) {
    // statement
} else if (a == b) {
    // statement
} else {
    // statement
}

// switch
switch (variable_expression) {
    case constant_expr1: {
        //statement
    }
    break;

    case constant_expr2: {
        //statement
    }
    break;

    default: {
        //statement
    }
    break;
}
```

### Functions

```dart
int my_function(int param, [int optional_param], {int default_param = 42} ) {
    return param;
}

// Lambda functions
int my_lambda() => 42;
```

### Classes

```dart
class MyClass {
    static String name;
    final int myFinalVar1;
    final int myFinalVar2;
    int myVar1;
    int myVar2;
    int myPublicVariable;
    int _myPrivateVariable;

    // class constructor
    MyClass() {
        // ...
    }

    // parameterized constructor
    MyClass(String param1, String param2) {
        this.myVar1 = param1;
        this.myVar2 = param2;
    }

    // parameterized constructor (short form)
    MyClass({this.myVar1, this.myVar2});

    // initializer list
    MyClass(String param1, String param2)
    : this.myFinalVar1 = param1,
      this.myFinalVar2 = param2;

    // named constructor
    MyClass.myConstructor(String param) {
        // ...
    }

    // static method
    static void myStaticMethod() {
        // ...
    }

    // public method
    public void myPublicMethod() {
        // ...
    }

    void set name(String name) {
        this.name = name;
    }

    String get name {
        return name;
    }
}

MyClass myObject = new MyClass(); // Create instance
myObject.name; // Access attribute
myObject.myPublicMethod(); // Call method
MyClass.myStaticMethod(); // Call static method
MyClass()..myMethod(); // Cascade notation

// Inheritance and method overriding
class ParentClass {
    void my_method() {
        // ...
    }
}

class ChildClass extends ParentClass {
    @override
    void my_method() {
        // ...
    }
}
```

### Interfaces

```dart
class MyInterface {
   void my_function() {}
}

class MyClass implements MyInterface {
   void my_function() {  
      // implementation
   }
}
```

### Generics

```dart
// Generic class
class Property<T> {
    T first, second;
    Property(this.first, this.second);
}
```

### Async

```dart
Future<String> fut_str = file.readAsString();
fut_str.then((data) => print(data));

// async-await
Future<void> my_function() async {
    await my_async_function();
}
```

### Concurrency

```dart
Isolate.spawn(spawned_function1, message1);
Isolate.spawn(spawned_function2, message2);
```

### Error handling

```dart
try {
   // code that might throw an exception
}
on Exception1 {
   // code for handling exception
}
catch Exception2 {
   // code for handling exception
}
```
