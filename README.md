# Dart vs Kotlin vs Swift Comparison

Versions: Swift (5.4.2), Dart (2.13.4), Kotlin

### Basics, Variables & Constants
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>
<tr>
<td>
  
```dart
// Implicit type = int
var myVariable = 5;

// Explicit type: String
String name = "Kral";

// Dynamic type: dynamic
dynamic dinamik = "Dynamic";
dinamik = 5; // Valid

// Constant
final name = "Enes";
const name = "Enes";
// Anything that isn't known at 
// compile time 
// should be final over const.
```
[Difference between const and final](https://stackoverflow.com/questions/50431055/what-is-the-difference-between-the-const-and-final-keywords-in-dart)
  
</td>
<td>

```kotlin
// Implicit type = Int
var myVariable = 5 

// Explicit type: String
var name: String = "Kral"

// Dynamic type: dynamic
var dinamik: dynamic = "String"
dinamik = 5 // Valid

// Constant
// Fill
```

</td>
<td>
  
```swift
// Implicit type = Int
var myVariable = 5 
myVariable = "a string" // Invalid

// Explicit type: String
var name: String = "Kral"

// Dynamic type: Any
var dinamik: Any = "String"
dinamik = 5 // Valid

// Constant
let gender = "Man"
gender = "Woman" // Invalid
```
    
</td>
</tr>

<tr>
<td>
  
```dart
enum Color { red, green, blue }
var aColor = Color.blue;  
// aColor has index, hashCode & toString() parameters by default.

// Enum cases can not contain associated values like in Swift.
// Computed variables & Functions can't be added directly to the enum.
// But they can be added via an extension.
extension DarkMode on Color {
  Color get darkModeAlternative {
    switch (this) {
      case Color.blue: return Color.red;
      default: return Color.blue;
    }
  }
}
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Enum
enum MessageKind {
    case placeholder
    // Associated values allowed.
    case image(URL)
    case text(String)

    // Computed variables & Static variables allowed.
    var debugPrint: String {
        switch self {
        case .image(let url):
            return "Url: \(url)"
        case .text(let text):
            return "Text: \(text)"
        default:            
            return "Placeholder"
        }
    }

    // Functions are allowed as well.
    func debugPrintFoo() -> String {
        debugPrint
    }
}
```
    
</td>
</tr>

<tr>
<td>
  
```dart
typedef GestureTapCallback = void Function();
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Type alias
typealias TapCallback = () -> Void
```
    
</td>
</tr>


<tr>
<td>
  
```dart
// Check type
if (myVariable is String) { .. }
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Check type
if myVariable is String { .. }
```
    
</td>
</tr>

</table>

### Strings
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// Declaration
var string1 = "String";
var string2 = 'String';

// Multiline
var multilineStr = """
Here you can have your string multiline for easier readability;
Start & end with 3 quote character.
""";

// String interpolation
var name = "Enes";
print("Hello $name");
print("For objects use ${person.name}");
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Declaration
let string = "String"

// Multiline
let multilineStr = """
Here you can have your string multiline for easier readability;
Start & end with 3 quote character.
"""

// String interpolation
let name = "Enes"
print("Hello \(name)")
print("For objects use \(person.name)")
```
    
</td>
</tr>

</table>

### Functions
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// Declaration
String greet(String name) {
    return "Hey $name";
}

// Optional named parameters
void greet(String name) { }
greet("Enes");

// Named parameters
void greet({required String name}) { }
greet(name: "Enes")

// Default parameters
void greet({String name = "Enes"}) { }
greet();
greet(name: "Kral");

// Var args
// N/A
// List can be used to achieve
// similar behaviour
// or visit `VarArgs` package below.

// Closure/Lambda
var square = (int x) => x * x;
square(4);
```

[VarArgs Package](https://pub.dev/packages/varargs)
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Declaration
func greet(name: String) -> String {
    // return keyword is optional if body contains single (code) line 
    return "Hey \(name)"
}

// Optional named parameters
func greet(_ name: String) { }
greet("Enes")

// Named parameters
func greet(name: String) { }
greet(name: "Enes")

// Default parameters
func greet(name: String = "Enes") { }
greet()
greet(name: "Adam")

// Var args
func greet(_ names: String...) { }
greet("Enes", "Egemen", "Ferid", "Serkan")

// Closure/Lambda
var square: (Int) -> Int = { $0 * $0 }
var square = { (x: Int) -> Int in 
    return x * x
}
square(4)
```
    
</td>
</tr>

</table>

### Control Flow
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// if & else(if)
if (isRaining()) {
  you.bringRainCoat();
} else if (isSnowing()) {
  you.wearJacket();
} else {
  car.putTopDown();
}
  
// for loops
for (var i = 0; i < 5; i++) {
  print('Flutter ${i + 1}');
}
  
// for-in
var obj = ["Android","iOS","Flutter"]; 
for (var prop in obj) { 
  print(prop); 
} 

// for-each
var collection = ["Android", "iOS", "Flutter"];
collection.forEach(print);
// or
var callbacks = [];
for (var i = 0; i < 2; i++) {
  callbacks.add(() => print(i));
}
callbacks.forEach((c) => c()); 

// while
while (!isDone()) {
  doSomething();
}
  
// do-while
do {
  printLine();
} while (!atEndOfPage());

// break
while (true) {
  if (shutDownRequested()) break;
  processIncomingRequests();
}

// continue
for (int i = 0; i < candidates.length; i++) {
  var candidate = candidates[i];
  if (candidate.yearsExperience < 5) {
    continue;
  }
  candidate.interview();
}
// or
candidates
    .where((c) => c.yearsExperience >= 5)
    .forEach((c) => c.interview());

// switch-case
var option = 1;
switch (option) {
case 1:
  print("Android");
  break;
case 2:
  print("iOS");
  break;
default:
  print("Flutter");
  break;
}
  
// switch-continue
var option = 1;
switch (option) {
case 1:
  print("Android");
  continue testCase;
testCase:
case 2:
  print("iOS");
  break;
}

```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// if & else(if)
if isRaining() {
    you.bringRainCoat()
} else if isSnowing() {
    you.wearJacket()
} else {
    car.putTopDown()
}

// for loops
// swift does not have C like for loops
for i in 0..<5 {
    print("Swift \(i + 1)")
}

// for-in
var collection = ["Android", "iOS", "Flutter"]
for item in collection {
    print(item)
}

// for-each
collection.forEach {
    print($0)
}

// while
while !isDone() {
    doSomething()
}

// repeat-while
repeat {
    printLine()
} while !atEndOfPage()

// break
while true {
    if (shutDownRequested()) break
    processIncomingRequests()
}

// continue
for candidate in candidates {
    if candidate.yearsExperience < 5 { continue }
    candidate.interview()
}

// or
candidates
    .filter { $0.yearsExperience >= 5 }
    .forEach { $0.interview() }

// switch-case
var option = 1
switch option {
case 1:
    print("Android")
case 2:
// ranges also supported -> case 2...5: 
// ranges also supported -> case 2..<6: 
    print("iOS")
default:
    print("Flutter")
}
// Prints "Android"

// switch-continue
var option = 1
switch option {
case 1:
    print("Android");
    fallthrough
case 2:
    print("iOS")
default:
    print("Flutter");
}
// Prints "Android" & "iOS"
```
    
</td>
</tr>

</table>

### Collections
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// Fill
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Fill
```
    
</td>
</tr>

</table>

### Optionals & Nullability
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// Declaration
String str = null;  // Invalid

String? str = null; // Valid
str?.toUpperCase(); // Safe call

String? str = "enes";
str?.toUpperCase(); // "ENES"

// Null aware operator
int? id = null;
var userId = id ?? -1; // -1

int? id = 53;
var userId = id ?? -1; // 53
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Declaration
var str: String = nil  // Invalid

var str: String? = nil // Valid
str?.uppercased()      // Safe call

var str: String? = "enes";
str?.uppercased() // Optional("ENES")

// Nil Coalescing operator
var id: Int? = nil
var userId = id ?? -1 // -1

var id: Int? = 53;
var userId = id ?? -1; // 53

```
    
</td>
</tr>

</table>

### Extensions
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// Fill
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Fill
```
    
</td>
</tr>

</table>

### Class, Struct, Protocol..
<table>
<tr>
<th> Dart </th>
<th> Kotlin </th>
<th> Swift </th>
</tr>

<tr>
<td>
  
```dart
// Fill
```
  
</td>
<td>

```kotlin
// Fill
```

</td>
<td>
  
```swift
// Fill
```
    
</td>
</tr>

</table>
