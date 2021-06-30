# Dart vs Kotlin vs Swift Comparison

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
