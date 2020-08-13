# Dart

### Print

```dart
var name = "world";
print('Hello $name');
```

### Variables

```dart
var x = 'Smith';
String x = 'Bob'; // typed
const bar = 42;
```

### Data types

```dart
// Basic types
String x;
int x:
double x;
bool x;

// List
var lst = new List(5) // fixed length
var lst = [1, 2, 3] // growable length
lst[0] = 'value' // initialize

// Map
var mp = { 'key1': 'value1', 'key2': 'value2' };
Map<String, String> m = { 'key1': 'value1', 'key2': 'value2' }; // typed

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
class User {
    static String name;

    // // class constructor
    User() {
        // ...
    }

    // named constructor
    Car.myConstructor(String param) {
        // ...
    }

    void set user_name(String name) {
        this.name = name;
    }

    String get user_name {
        return name;
    }
}

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
