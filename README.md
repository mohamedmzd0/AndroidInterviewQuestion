# Android Interview Questions & Answers

## Jr. JWE (Senior Software Engineer)

### Kotlin / Java

**Q: Do objects get passed by reference or value in Java?**
A: In Java, objects are passed by reference, but primitive types are passed by value. More precisely, Java passes the value of the reference for objects - you get a copy of the reference pointing to the same object in memory.

**Q: What is init block in Kotlin?**
A: The `init` block is executed immediately after the primary constructor. It's used for initialization logic that can't be placed in the primary constructor parameter list. Multiple init blocks can exist and are executed in order.

```kotlin
class Person(name: String) {
    val name: String
    
    init {
        this.name = name.uppercase()
        println("Person initialized with name: $name")
    }
}
```

**Q: What are the types of constructors in Kotlin?**
A: Kotlin has two types of constructors:
1. **Primary Constructor**: Declared as part of the class header, can have parameters and visibility modifiers
2. **Secondary Constructor**: Declared inside the class body using the `constructor` keyword, must delegate to the primary constructor

**Q: Is there any relationship between primary and secondary constructors?**
A: Yes, secondary constructors must delegate to the primary constructor either directly or indirectly through another secondary constructor using `this()`.

**Q: Difference between var and val?**
A: 
- `var` - mutable variable (can be reassigned)
- `val` - immutable variable (cannot be reassigned after initialization, similar to `final` in Java)

**Q: What are visibility modifiers in Kotlin & Java?**
A: 
**Kotlin**: `public` (default), `private`, `protected`, `internal`
**Java**: `public`, `private`, `protected`, `package-private` (default)

**Q: Switch expression replacement in Kotlin? || When Expression?**
A: Kotlin uses `when` expression instead of `switch`. It's more powerful and can be used as both statement and expression.

```kotlin
when (x) {
    1 -> "One"
    2, 3 -> "Two or Three"
    in 4..10 -> "Between 4 and 10"
    else -> "Other"
}
```

**Q: List vs MutableList?**
A: 
- `List` - read-only interface, cannot add/remove elements
- `MutableList` - extends List, allows adding/removing elements

**Q: How to define a nullable variable in kotlin?**
A: Use the `?` operator after the type:
```kotlin
var name: String? = null
```

**Q: Lateinit var in kotlin?**
A: `lateinit var` is used for variables that will be initialized later but before first use. It can only be used with mutable properties and non-null types.

```kotlin
class MyClass {
    lateinit var name: String
    
    fun initialize() {
        name = "John"
    }
}
```

**Q: Difference between lateinit var and var?**
A: 
- `lateinit var` - promises initialization before use, throws exception if accessed before initialization
- `var` - regular mutable variable, can be null if nullable type

**Q: What is String Interpolation in Kotlin?**
A: String interpolation allows embedding expressions inside string literals using `$` for variables and `${}` for expressions.

```kotlin
val name = "John"
val age = 25
val message = "Hello $name, you are ${age + 1} years old next year"
```

**Q: What are companion objects in Kotlin?**
A: Companion objects are singleton objects tied to a class, similar to static members in Java. They're initialized when the class is loaded.

```kotlin
class MyClass {
    companion object {
        fun create(): MyClass = MyClass()
    }
}
```

**Q: What is the open keyword in Kotlin used for?**
A: The `open` keyword makes a class, method, or property inheritable/overridable. By default, classes and methods are final in Kotlin.

**Q: What are lambda expressions?**
A: Lambda expressions are anonymous functions that can be treated as values. They're defined with curly braces and can be passed as parameters.

```kotlin
val sum = { x: Int, y: Int -> x + y }
listOf(1, 2, 3).map { it * 2 }
```

### Algorithms & Data Structures

**Q: What is data-structure? And examples of it.**
A: A data structure is a way of organizing and storing data to perform operations efficiently. Examples: Array, LinkedList, Stack, Queue, HashMap, Tree, Graph.

**Q: Common Ops that can be executed on DS?**
A: Common operations include: Insert, Delete, Search, Update, Traverse, Sort, and Access.

**Q: What is linear data structure?**
A: A linear data structure has elements arranged in a sequential manner where each element is connected to its previous and next element. Examples: Arrays, LinkedList, Stack, Queue.

**Q: What is a linked-list?**
A: A linked list is a linear data structure where elements (nodes) are stored in sequence, and each node contains data and a reference to the next node.

**Q: What is a stack?**
A: A stack is a LIFO (Last In, First Out) data structure with two main operations: push (add element) and pop (remove top element).

**Q: Example of stack Implementation in Android?**
A: Activity lifecycle management, Fragment backstack, Navigation component's back stack, and Undo/Redo functionality.

**Q: List vs Array**
A: 
- **Array**: Fixed size, elements stored in contiguous memory, direct access by index
- **List**: Dynamic size, may not be contiguous, implements Collection interface

**Q: What's Linear Search?**
A: Linear search checks each element sequentially until the target is found or the end is reached. Time complexity: O(n).

**Q: What's Binary Search?**
A: Binary search works on sorted arrays by repeatedly dividing the search interval in half. Time complexity: O(log n).

**Q: Difference between Linear and Binary Search?**
A: 
- **Linear**: O(n) time, works on unsorted data
- **Binary**: O(log n) time, requires sorted data

### Architecture

**Q: What are Android Architecture Components?**
A: A collection of libraries that help design robust, testable, and maintainable apps: Room, ViewModel, LiveData, Navigation, WorkManager, Data Binding, Paging.

**Q: Did you work with any architecture pattern before?**
A: This is experience-based. Common patterns include MVC, MVP, MVVM, and MVI.

**Q: Describe MVP Pattern**
A: Model-View-Presenter pattern:
- **Model**: Data layer (repositories, databases)
- **View**: UI layer (Activities, Fragments)
- **Presenter**: Business logic, mediates between Model and View

**Q: Describe MVC Pattern**
A: Model-View-Controller pattern:
- **Model**: Data and business logic
- **View**: User interface
- **Controller**: Handles user input and updates Model/View

**Q: Describe MVVM Pattern**
A: Model-View-ViewModel pattern:
- **Model**: Data layer
- **View**: UI layer
- **ViewModel**: Holds UI state and business logic, survives configuration changes

### Dependency Injection

**Q: What's dependency injection?**
A: A design pattern where objects receive their dependencies from external sources rather than creating them internally. This promotes loose coupling and testability.

**Q: What's the benefit of applying it?**
A: Benefits include: Improved testability, loose coupling, easier maintenance, better code reusability, and simplified mocking.

**Q: Did you try any dependency injection framework before?**
A: Common frameworks include Dagger2, Hilt, Koin, and manual dependency injection.

### SOLID Principles

**Q: What do you know about SOLID principles?**
A: SOLID is an acronym for five design principles that make software designs more understandable, flexible, and maintainable.

**Q: Explain the Single Responsibility Principle (SRP)**
A: A class should have only one reason to change. Each class should have only one job or responsibility.

**Q: Explain the Open Close Principle (OCP)**
A: Software entities should be open for extension but closed for modification. You should be able to extend behavior without modifying existing code.

**Q: Explain Liskov Substitution Principle (LSP)**
A: Objects of a superclass should be replaceable with objects of a subclass without breaking the application.

**Q: Explain Interface Segregation Principle (ISP)**
A: Clients should not be forced to depend on interfaces they don't use. Create specific interfaces rather than one general-purpose interface.

**Q: Explain the Dependency Inversion Principle (DIP)**
A: High-level modules should not depend on low-level modules. Both should depend on abstractions.

### Automation Test

**Q: What are the different types of testing we have in android?**
A: Unit tests, Integration tests, Instrumentation tests, UI tests, and End-to-end tests.

**Q: Did you conduct a unit test before?**
A: This is experience-based. Unit tests test individual components in isolation.

**Q: What makes your code testable?**
A: Factors include: dependency injection, single responsibility, loose coupling, avoiding static methods, and using interfaces.

**Q: What are the steps to test a logic in a specific method?**
A: 1. Arrange (set up test data), 2. Act (execute the method), 3. Assert (verify the result).

### Android

**Q: Explain Activity and Fragment lifecycle**
A: 
**Activity**: onCreate() → onStart() → onResume() → onPause() → onStop() → onDestroy()
**Fragment**: onAttach() → onCreate() → onCreateView() → onViewCreated() → onStart() → onResume() → onPause() → onStop() → onDestroyView() → onDestroy() → onDetach()

**Q: What is an Implicit Intent?**
A: An implicit intent doesn't specify the target component but declares an action to perform, allowing other apps to handle it.

```kotlin
val intent = Intent(Intent.ACTION_VIEW, Uri.parse("https://www.example.com"))
startActivity(intent)
```

**Q: What is an Explicit Intent?**
A: An explicit intent specifies the exact component (class) to start.

```kotlin
val intent = Intent(this, SecondActivity::class.java)
startActivity(intent)
```

**Q: What are the android application components?**
A: Activities, Services, Broadcast Receivers, and Content Providers.

**Q: Ever used broadcast receivers?**
A: Broadcast receivers respond to system-wide broadcast announcements like battery low, connectivity changes, etc.

**Q: Did you work with Constraint Layout?**
A: ConstraintLayout allows creating complex layouts with a flat view hierarchy using constraints between views.

**Q: What's the Service, which thread it operates on?**
A: A Service runs long-running operations in the background. It runs on the main thread by default, so you need to use background threads for intensive work.

**Q: Difference between View.GONE and View.INVISIBLE?**
A: 
- **GONE**: View is invisible and doesn't take up space in layout
- **INVISIBLE**: View is invisible but still takes up space in layout

**Q: What are View and ViewGroup with examples?**
A: 
- **View**: Basic building block for UI components (TextView, Button, ImageView)
- **ViewGroup**: Container for other views (LinearLayout, RelativeLayout, ConstraintLayout)

**Q: How would you communicate between two Fragments?**
A: Methods include: Shared ViewModel, Interface with Activity, Fragment Result API, Event Bus, or Navigation Component.

**Q: When should you use a Fragment rather than an Activity?**
A: Use Fragments for: modular UI components, tablet layouts, navigation within single Activity, reusable UI components.

### Feature / System Design

**Q: How to support two different implementation approaches and dynamically use one of them with ease based on device type using design patterns?**
A: Use Strategy Pattern or Factory Pattern:

```kotlin
interface LocationService {
    fun getLocation(): Location
}

class HMSLocationService : LocationService {
    override fun getLocation(): Location { /* HMS implementation */ }
}

class GMSLocationService : LocationService {
    override fun getLocation(): Location { /* GMS implementation */ }
}

class LocationServiceFactory {
    fun createLocationService(): LocationService {
        return if (isHuaweiDevice()) {
            HMSLocationService()
        } else {
            GMSLocationService()
        }
    }
}
```

---

## SWE II (Mid-level Software Engineer)

### Kotlin / Java (Additional Questions)

**Q: What does it mean to say that a String is immutable?**
A: Once a String object is created, its value cannot be changed. Any operation that appears to modify a String actually creates a new String object.

**Q: What are the scope functions? And What is the difference between them?**
A: Kotlin has five scope functions: `let`, `run`, `with`, `apply`, `also`
- **let**: Returns lambda result, uses `it` for context
- **run**: Returns lambda result, uses `this` for context
- **with**: Non-extension function, returns lambda result
- **apply**: Returns context object, uses `this` for context
- **also**: Returns context object, uses `it` for context

**Q: What's the difference between declaring a nullable Var and a lateinit Var?**
A: 
- **Nullable var**: Can be null, requires null checks
- **lateinit var**: Cannot be null, must be initialized before use, throws exception if accessed before initialization

**Q: Val vs const**
A: 
- **val**: Runtime constant, can be initialized at runtime
- **const**: Compile-time constant, must be initialized with constant value

**Q: How to handle nullable variables in kotlin?**
A: Methods include: Safe call operator (`?.`), Elvis operator (`?:`), Not-null assertion (`!!`), and null checks.

**Q: What's the elvis operator?**
A: The Elvis operator (`?:`) provides a default value when the left side is null.

```kotlin
val name = person?.name ?: "Unknown"
```

**Q: What are @JvmStatic, @JvmOverloads, and @JvmFiled annotations?**
A: 
- **@JvmStatic**: Makes companion object functions static for Java interop
- **@JvmOverloads**: Generates overloaded methods for default parameters
- **@JvmField**: Exposes property as a field instead of getter/setter

**Q: Type of classes in Kotlin?**
A: Regular classes, Data classes, Sealed classes, Enum classes, Inner classes, Nested classes, Abstract classes, Interface.

**Q: What is the equivalent of Java static methods in Kotlin?**
A: Use companion objects, top-level functions, or object declarations.

**Q: What is the suspend function in Kotlin Coroutines?**
A: A suspend function can be paused and resumed without blocking the thread. It can only be called from within a coroutine or another suspend function.

**Q: What is the difference between Launch and Async in Kotlin Coroutines?**
A: 
- **launch**: Fire-and-forget coroutine, returns Job
- **async**: Returns Deferred<T>, allows getting result with await()

**Q: What are extension functions in Kotlin?**
A: Extension functions allow adding new functionality to existing classes without modifying their source code.

```kotlin
fun String.isValidEmail(): Boolean {
    return android.util.Patterns.EMAIL_ADDRESS.matcher(this).matches()
}
```

**Q: What are the benefits of using a Sealed Class over Enum?**
A: Sealed classes can hold data and have different types for each subclass, while enums are limited to constants.

**Q: What are pair and triple in Kotlin?**
A: Data classes for holding two or three values: `Pair<A, B>` and `Triple<A, B, C>`

**Q: Synchronized vs Volatile keyword**
A: 
- **synchronized**: Ensures thread-safe access to a block of code
- **volatile**: Ensures variable visibility across threads

**Q: StringBuffer and StringBuilder**
A: 
- **StringBuffer**: Thread-safe, synchronized
- **StringBuilder**: Not thread-safe, faster

### Algorithms & DS (Additional Questions)

**Q: hashmap vs set**
A: 
- **HashMap**: Key-value pairs, allows duplicate values
- **Set**: Unique elements only, no duplicates

**Q: What is the worst case time complexity of linear search algorithm?**
A: O(n) - when the element is at the end or not found.

**Q: What is the selection sort?**
A: Selection sort finds the minimum element and places it at the beginning, then repeats for the remaining array. Time complexity: O(n²).

**Q: How does quicksort work?**
A: Quicksort picks a pivot element, partitions the array around it, and recursively sorts the sub-arrays. Average time complexity: O(n log n).

**Q: How does Bubble Sort work?**
A: Bubble sort repeatedly steps through the list, compares adjacent elements, and swaps them if they're in the wrong order. Time complexity: O(n²).

**Q: SparseArray vs HashMap?**
A: 
- **SparseArray**: Memory efficient for integer keys, slower for large datasets
- **HashMap**: Faster lookups, more memory overhead

### Architecture (Additional Questions)

**Q: Difference between MVC, MVP and MVVM?**
A: 
- **MVC**: Controller handles input, Model manages data, View displays UI
- **MVP**: Presenter handles logic, Model manages data, View is passive
- **MVVM**: ViewModel handles logic with data binding, Model manages data, View observes ViewModel

**Q: Do you know the MVI pattern?**
A: Model-View-Intent pattern treats UI as a function of state, with unidirectional data flow: Intent → Model → View.

**Q: What's the repository pattern and when to use it?**
A: Repository pattern centralizes data access logic, abstracting data sources. Use it to provide a clean API for data access and enable easy testing.

**Q: What's clean architecture? And what's the benefit of it?**
A: Clean architecture separates concerns into layers (presentation, domain, data) with dependency inversion. Benefits: testability, maintainability, independence of frameworks.

**Q: What's the difference between Single module vs Multi module architecture?**
A: 
- **Single module**: Everything in one module, simpler but can become unwieldy
- **Multi module**: Separated by features/layers, better build times, enforces boundaries

### Dependency Injection (Additional Questions)

**Q: Heard about manual dependency injection?**
A: Manual DI involves manually creating and passing dependencies without using a framework. It's simpler but requires more boilerplate code.

**Q: What's Service locator?**
A: Service locator is a design pattern where objects obtain their dependencies by asking a central locator service.

**Q: Difference between Service locator and Dependency injection?**
A: 
- **Service Locator**: Objects pull dependencies from a central location
- **Dependency Injection**: Dependencies are pushed to objects from external sources

**Q: Koin vs Dagger2?**
A: 
- **Koin**: Lightweight, runtime resolution, easier to learn
- **Dagger2**: Compile-time resolution, better performance, more complex

**Q: Dagger2 vs Hilt?**
A: Hilt is built on top of Dagger2, providing a simpler API with predefined components for Android.

**Q: Dependency Injection vs Dependency Inversion?**
A: 
- **Dependency Injection**: A technique for achieving IoC
- **Dependency Inversion**: A principle stating high-level modules shouldn't depend on low-level modules

### Design Principles (Additional Questions)

**Q: What is Inversion of Control (IoC)?**
A: IoC is a principle where the control of object creation and lifecycle is transferred from the object itself to an external container or framework.

**Q: What is the 'Don't repeat yourself (DRY)' Principle?**
A: DRY principle states that every piece of knowledge should have a single, unambiguous representation within a system.

### Automation Test (Additional Questions)

**Q: What's a unit test?**
A: A unit test tests a single component or method in isolation, typically using mocks for dependencies.

**Q: What's an instrumental test?**
A: An instrumentation test runs on an Android device or emulator, testing the app in a real Android environment.

**Q: Differentiate between test and androidTest directory in android studio**
A: 
- **test**: Unit tests, run on JVM
- **androidTest**: Instrumentation tests, run on Android device/emulator

**Q: When to use the real object and when to mock it?**
A: Use real objects for simple, fast operations. Mock external dependencies, slow operations, or when testing edge cases.

**Q: What's the test double?**
A: Test doubles are objects that replace real dependencies in tests: Mock, Stub, Fake, Spy, Dummy.

**Q: Have you used Mockito before?**
A: Mockito is a popular mocking framework for creating test doubles in Java/Kotlin.

**Q: What's the testing pyramid in android?**
A: The testing pyramid shows the ideal distribution of tests: Many unit tests (base), some integration tests (middle), few UI tests (top).

**Q: What is Code Coverage?**
A: Code coverage measures the percentage of code executed during testing, helping identify untested areas.

### Android (Additional Questions)

**Q: What are the different types of Broadcasts?**
A: Ordered broadcasts (delivered to receivers in priority order) and Normal broadcasts (delivered to all receivers simultaneously).

**Q: What is the thread that the onReceive method of a BroadcastReceiver operates on?**
A: The main/UI thread.

**Q: ConstraintLayout vs RelativeLayout**
A: 
- **ConstraintLayout**: Flat hierarchy, better performance, more flexible
- **RelativeLayout**: Can create deep hierarchies, less performant

**Q: What is a PendingIntent?**
A: A PendingIntent is a wrapper around an Intent that can be passed to another application, allowing it to execute the Intent with your app's permissions.

**Q: While using the location service how to reduce battery usage in an android application?**
A: Use appropriate location accuracy, increase update intervals, use geofencing, stop updates when not needed, and use passive location provider.

**Q: What's the difference between Service and IntentService?**
A: 
- **Service**: Runs on main thread, must handle threading manually
- **IntentService**: Runs on background thread, handles one request at a time, stops automatically

**Q: How to support different screen sizes in android?**
A: Use flexible layouts, provide different resources for different screen sizes, use density-independent pixels (dp), and test on various screen sizes.

**Q: What is Android Data Binding?**
A: Data Binding allows binding UI components to data sources declaratively, reducing boilerplate code and improving performance.

**Q: What is Android View Binding?**
A: View Binding generates binding classes for each XML layout file, providing type-safe access to views without findViewById.

**Q: List Adapter vs RecyclerView.Adapter**
A: 
- **ListAdapter**: Built-in DiffUtil support, easier to use with lists
- **RecyclerView.Adapter**: More flexible, requires manual DiffUtil implementation

**Q: What is the difference between Serializable and Parcelable?**
A: 
- **Serializable**: Java interface, uses reflection, slower
- **Parcelable**: Android interface, faster, more efficient for Android

**Q: commit() vs apply() in SharedPreferences?**
A: 
- **commit()**: Synchronous, returns boolean, blocks UI thread
- **apply()**: Asynchronous, void return, doesn't block UI thread

**Q: Why is it recommended to use only the default constructor to create a fragment?**
A: Android recreates fragments during configuration changes using the default constructor. Use arguments Bundle for passing data.

**Q: What is ANR? How can the ANR be prevented?**
A: ANR (Application Not Responding) occurs when the main thread is blocked for more than 5 seconds. Prevent by using background threads for heavy operations.

**Q: What is adb?**
A: Android Debug Bridge is a command-line tool for communicating with Android devices for debugging and development.

**Q: Describe a scenario where onPause() and onStop() would not be invoked**
A: When the app is killed by the system due to low memory or when the device is powered off suddenly.

**Q: How is LiveData different from ObservableField?**
A: 
- **LiveData**: Lifecycle-aware, automatically manages subscriptions
- **ObservableField**: Part of Data Binding, not lifecycle-aware

**Q: Cold vs Hot Observables?**
A: 
- **Cold**: Emits values only when subscribed to
- **Hot**: Emits values regardless of subscriptions

**Q: Observable vs flowable**
A: 
- **Observable**: No backpressure handling
- **Flowable**: Handles backpressure for high-emission scenarios

**Q: How to create parallel Network calls with Rxjava?**
A: Use `zip`, `merge`, or `flatMap` operators to combine multiple observable streams.

**Q: What's the difference between map and flatMap() in Rxjava?**
A: 
- **map**: Transforms each emission 1:1
- **flatMap**: Transforms each emission into an Observable and flattens the result

**Q: Concat vs Merge operators in Rxjava**
A: 
- **concat**: Emits from observables sequentially
- **merge**: Emits from observables simultaneously

**Q: Schedulers.io() vs Schedulers.computation()**
A: 
- **io()**: For I/O operations (network, database)
- **computation()**: For CPU-intensive operations

**Q: One example of a memory leak and two ways to detect it**
A: Example: Activity holding static reference. Detection: LeakCanary, Android Studio Memory Profiler.

**Q: What is proguard used for?**
A: ProGuard is used for code obfuscation, shrinking, and optimization to reduce APK size and improve security.

**Q: What are coroutines in Kotlin?**
A: Coroutines are lightweight threads that allow writing asynchronous code in a sequential manner.

**Q: Did you work with CI/CD in your previous projects?**
A: This is experience-based. CI/CD involves automated building, testing, and deployment processes.

**Q: How to handle screen rotations properly**
A: Use ViewModel to retain data, save state in onSaveInstanceState, use configuration qualifiers, or lock orientation if needed.

**Q: What is the difference between Dialog & DialogFragment?**
A: 
- **Dialog**: Can cause memory leaks, doesn't handle configuration changes well
- **DialogFragment**: Lifecycle-aware, handles configuration changes properly

---

## Sr. SWE (Senior Software Engineer)

### Kotlin / Java (Additional Questions)

**Q: OOP vs Functional Programming**
A: 
- **OOP**: Encapsulation, inheritance, polymorphism, objects
- **FP**: Immutability, higher-order functions, pure functions, no side effects

**Q: What's the "!! double bang" operator? Is it safe to use it?**
A: The not-null assertion operator converts nullable types to non-null types. It's not safe as it throws KotlinNullPointerException if the value is null.

**Q: How to define Singleton in Kotlin?**
A: Multiple ways: `object` declaration, class with companion object, enum singleton, or thread-safe lazy initialization.

**Q: What's destructuring in Kotlin?**
A: Destructuring allows extracting multiple values from objects:
```kotlin
val (name, age) = person
val (first, second) = pair
```

**Q: lateinit vs lazy**
A: 
- **lateinit**: Mutable, must be initialized before use
- **lazy**: Immutable, computed on first access

**Q: == vs === operator**
A: 
- **==**: Structural equality (calls equals())
- **===**: Referential equality (same object reference)

**Q: What are Higher-Order functions in Kotlin?**
A: Functions that take other functions as parameters or return functions.

**Q: What is an infix function in Kotlin?**
A: Infix functions can be called using infix notation (without dot and parentheses):
```kotlin
infix fun Int.multiply(x: Int): Int = this * x
val result = 2 multiply 3
```

**Q: What is an inline function in Kotlin?**
A: Inline functions have their code copied to the call site, avoiding function call overhead.

**Q: What is noinline in Kotlin?**
A: `noinline` prevents specific lambda parameters from being inlined in an inline function.

**Q: What are Reified types in Kotlin?**
A: Reified type parameters allow accessing type information at runtime in inline functions:
```kotlin
inline fun <reified T> isA(value: Any): Boolean = value is T
```

### Algorithms & DS (Additional Questions)

**Q: What is the Complexity of Algorithms?**
A: Algorithm complexity measures resource usage (time/space) as input size grows, expressed in Big O notation.

**Q: What is hashing?**
A: Hashing converts data into a fixed-size string using a hash function, commonly used in hash tables for fast lookups.

**Q: What are asymptotic notations?**
A: Mathematical notations to describe algorithm performance: Big O (upper bound), Omega (lower bound), Theta (tight bound).

**Q: What is a Binary Search Tree?**
A: A binary tree where left child is smaller than parent, and right child is larger. Enables efficient search, insertion, and deletion.

**Q: Briefly explain the approaches to develop algorithms**
A: Approaches include: Divide and Conquer, Dynamic Programming, Greedy, Brute Force, Backtracking, and Branch and Bound.

**Q: What is a priority queue?**
A: A data structure where elements are served based on priority rather than insertion order. Often implemented using heaps.

**Q: What is the worst case run-time complexity of binary search algorithms?**
A: O(log n) - when the element is not found or at the last position checked.

### Architecture (Additional Questions)

**Q: Describe Android platform Architecture?**
A: Android architecture consists of: Linux Kernel, Hardware Abstraction Layer (HAL), Android Runtime (ART), Native C/C++ Libraries, Java API Framework, and System Apps.

**Q: What is the UseCase and when to use it?**
A: UseCase encapsulates business logic for a specific user action. Use it in clean architecture to separate business logic from UI and data layers.

**Q: What's the repository pattern?**
A: Repository pattern abstracts data access logic, providing a clean API for data operations regardless of data sources.

### Dependency Injection (Additional Questions)

**Q: Explain how to apply manual dependency injection?**
A: Create dependencies manually and pass them through constructors or setters. Use factories or service locators for complex scenarios.

**Q: Property injection vs Constructor injection?**
A: 
- **Constructor injection**: Dependencies passed through constructor (preferred)
- **Property injection**: Dependencies set after object creation

**Q: What are the hidden dependencies?**
A: Dependencies that aren't explicitly declared in the constructor or interface, making code harder to test and maintain.

**Q: What's the main difference between dagger2 and dagger1?**
A: Dagger2 uses compile-time code generation instead of runtime reflection, providing better performance and compile-time error checking.

**Q: What's the dependency flow in clean architecture?**
A: Dependencies flow inward: Presentation → Domain ← Data, with domain layer being independent of outer layers.

**Q: What's the difference between Dependency Injection, Dependency Inversion and Inversion of Control?**
A: 
- **DI**: Technique for providing dependencies
- **Dependency Inversion**: Principle about depending on abstractions
- **IoC**: General principle of inverting control flow

### Design Principles (Additional Questions)

**Q: How are Design Principles different from Design Patterns?**
A: 
- **Design Principles**: Guidelines for good design (SOLID, DRY)
- **Design Patterns**: Reusable solutions to common problems (Observer, Factory)

**Q: Explain the Separation of Concerns (SoC) design principle**
A: SoC separates a program into distinct sections, each addressing a separate concern or responsibility.

**Q: Explain KISS design principle**
A: KISS (Keep It Simple, Stupid) emphasizes simplicity in design, avoiding unnecessary complexity.

**Q: How Encapsulation Works as a Design Principle?**
A: Encapsulation bundles data and methods together while hiding internal implementation details, providing controlled access through interfaces.

**Q: What is the YAGNI Principle?**
A: YAGNI (You Ain't Gonna Need It) principle states that you shouldn't add functionality until it's actually needed, avoiding over-engineering.

### Automation Tests (Additional Questions)

**Q: Integration test vs unit test?**
A: 
- **Unit test**: Tests individual components in isolation
- **Integration test**: Tests interaction between multiple components

**Q: How to run an instrumental test without the emulator?**
A: Use Robolectric framework to run Android tests on JVM without emulator/device, though it doesn't work for all instrumentation test cases.

**Q: How to design a good unit test case?**
A: Follow AAA pattern (Arrange, Act, Assert), test one thing at a time, use descriptive names, test edge cases, make tests independent, and keep them fast.

**Q: Have you heard about Robolectric?**
A: Robolectric is a testing framework that allows running Android unit tests on JVM without emulator, providing faster test execution.

**Q: How to test private methods?**
A: Generally, don't test private methods directly. Test them through public methods. If needed, use reflection or make methods package-private.

**Q: Do you know TDD? Did you apply it before?**
A: TDD (Test-Driven Development) follows Red-Green-Refactor cycle: Write failing test, make it pass, refactor. Benefits include better design and higher test coverage.

**Q: What makes it tough achieving higher code coverage?**
A: Challenges include: legacy code, complex dependencies, UI testing difficulty, third-party libraries, and balancing coverage with meaningful tests.

### Android (Additional Questions)

**Q: What are the launch modes?**
A: Four launch modes:
- **standard**: Default, creates new instance each time
- **singleTop**: Reuses if on top of stack
- **singleTask**: Only one instance in task
- **singleInstance**: Only one instance system-wide

**Q: How can two distinct Android apps interact?**
A: Through Intents, Content Providers, Broadcast Receivers, AIDL (Android Interface Definition Language), and shared files.

**Q: Why Bundle class is used for data passing and why cannot we use simple Map data structure?**
A: Bundle is optimized for inter-process communication, handles serialization automatically, and is designed for Android's lifecycle management.

**Q: Can you create a custom view? How?**
A: Yes, by extending View or ViewGroup, overriding onDraw(), onMeasure(), onLayout(), handling touch events, and defining custom attributes.

**Q: Custom View Vs Fragments**
A: 
- **Custom View**: UI component, lightweight, no lifecycle
- **Fragment**: UI controller with lifecycle, can contain multiple views

**Q: What's the views Hierarchy and how it can affect app performance?**
A: View hierarchy is a tree structure of views. Deep hierarchies slow down layout passes and drawing, affecting performance. Use flat hierarchies when possible.

**Q: How do you debug views in your daily work?**
A: Use Layout Inspector, Hierarchy Viewer, GPU Overdraw visualization, systrace, and logging in custom views.

**Q: View Binding vs Data Binding?**
A: 
- **View Binding**: Type-safe view references, compile-time safety
- **Data Binding**: Binds data to layouts, supports expressions, two-way binding

**Q: Kotlin flows vs Channels**
A: 
- **Flows**: Cold streams, declarative, composable
- **Channels**: Hot streams, imperative, for communication between coroutines

**Q: What are Job States in coroutine?**
A: Job states: New, Active, Completing, Completed, Cancelling, Cancelled.

**Q: What's coroutine scope?**
A: Coroutine scope defines the lifecycle of coroutines, ensuring they're cancelled when no longer needed.

**Q: What's the suspend function?**
A: A function that can be paused and resumed without blocking the thread, enabling asynchronous programming.

**Q: What is the coroutines context consists of?**
A: Coroutine context contains: Job, Dispatcher, CoroutineName, and CoroutineExceptionHandler.

**Q: When do you use observeOn() and subscribeOn()?**
A: 
- **subscribeOn()**: Specifies thread for subscription/emission
- **observeOn()**: Specifies thread for observation/consumption

**Q: What is reflection?**
A: Reflection allows examining and modifying code at runtime, inspecting classes, methods, and fields dynamically.

**Q: Any experience with JetPack Compose?**
A: Compose is Android's modern declarative UI toolkit, using composable functions to build reactive UIs.

**Q: Linting in Android?**
A: Android Lint analyzes code for potential bugs, performance issues, and improvements, providing static code analysis.

**Q: Explain the build process in Android**
A: Build process: Compile → DEX → Package → Align → Sign → APK/AAB. Involves compiling resources, Java/Kotlin code, and packaging.

**Q: What is the zygote process?**
A: Zygote is the parent process for all Android app processes, pre-loading common classes and resources for faster app startup.

### Feature / System Design (Additional Questions)

**Q: Design an android application which shares its location with a server**
A: Components needed:
- Location permission handling
- FusedLocationProviderClient for location updates
- Background service for continuous tracking
- Network layer for server communication
- Battery optimization considerations
- Privacy and security measures

```kotlin
class LocationSharingService {
    private val fusedLocationClient: FusedLocationProviderClient
    private val locationCallback: LocationCallback
    private val apiService: LocationApiService
    
    fun startLocationSharing() {
        // Request location updates
        // Send location to server
        // Handle errors and retries
    }
}
```

---

## Additional Advanced Questions

### Performance & Optimization

**Q: What is method tracing and how do you use it?**
A: Method tracing tracks method calls and execution times. Use Android Studio's CPU Profiler or systrace to identify performance bottlenecks.

**Q: How do you detect and fix memory leaks?**
A: Use LeakCanary, Memory Profiler, analyze heap dumps, avoid static references to context, use weak references, and properly manage lifecycle.

**Q: What is R8 and how does it differ from ProGuard?**
A: R8 is Android's code shrinker and obfuscator, replacing ProGuard. It's faster, more efficient, and integrated with Android build system.

**Q: How do you optimize RecyclerView performance?**
A: Use ViewHolder pattern, implement DiffUtil, avoid nested RecyclerViews, use appropriate layout managers, and implement view recycling properly.

**Q: What are Android App Bundles and their benefits?**
A: App Bundle is a publishing format that defers APK generation to Google Play, enabling dynamic delivery and smaller download sizes.

### Security

**Q: How do you implement certificate pinning in Android?**
A: Use OkHttp's CertificatePinner or Network Security Configuration to pin certificates, preventing man-in-the-middle attacks.

**Q: What is Android Keystore and when to use it?**
A: Android Keystore is a secure container for cryptographic keys, used for storing sensitive data like passwords and API keys.

**Q: How do you obfuscate code in Android?**
A: Use R8/ProGuard for code shrinking and obfuscation, enable minification, and configure keep rules for reflection-used code.

**Q: What are the best practices for storing sensitive data?**
A: Use Android Keystore, encrypt data, avoid SharedPreferences for sensitive data, use BiometricPrompt for authentication.

### Networking

**Q: How do you handle network security in Android?**
A: Implement HTTPS, certificate pinning, network security configuration, input validation, and secure authentication tokens.

**Q: What is OkHttp and its advantages?**
A: OkHttp is an HTTP client with features like connection pooling, GZIP compression, response caching, and request/response interceptors.

**Q: How do you implement caching in Android networking?**
A: Use HTTP cache headers, implement custom caching with Room/SQLite, use OkHttp's cache, or implement in-memory caching.

**Q: What are interceptors in OkHttp?**
A: Interceptors allow monitoring, rewriting, and retrying requests. Types: Application interceptors and Network interceptors.

### Database

**Q: What is Room and its benefits?**
A: Room is an abstraction layer over SQLite, providing compile-time SQL validation, convenient annotations, and LiveData integration.

**Q: How do you handle database migrations in Room?**
A: Define Migration objects with SQL scripts, add them to Room database builder, and test migrations thoroughly.

**Q: What is the difference between Room and SQLite?**
A: Room provides compile-time verification, easier database access, and better integration with Architecture Components.

**Q: How do you implement database relationships in Room?**
A: Use @Relation, @Embedded, foreign keys, and junction tables for many-to-many relationships.

### Modern Android Development

**Q: What is Jetpack Compose and its benefits?**
A: Compose is a declarative UI toolkit that simplifies UI development with less code, powerful tooling, and intuitive Kotlin APIs.

**Q: How does state management work in Compose?**
A: Use remember, mutableStateOf, State hoisting, and ViewModel for state management in Compose.

**Q: What are Compose modifiers?**
A: Modifiers are used to decorate or add behavior to Compose UI elements, like padding, click handling, and layout constraints.

**Q: How do you handle side effects in Compose?**
A: Use LaunchedEffect, DisposableEffect, rememberCoroutineScope, and other effect APIs for side effects.

### Testing Advanced

**Q: What is Espresso and how do you use it?**
A: Espresso is a UI testing framework for Android that provides APIs for writing concise and reliable UI tests.

**Q: How do you test asynchronous code?**
A: Use CountDownLatch, TestObserver, runBlockingTest, and mock frameworks with proper synchronization.

**Q: What is the difference between Fake and Mock?**
A: 
- **Fake**: Working implementation with shortcuts (in-memory database)
- **Mock**: Dummy implementation that returns predefined responses

**Q: How do you test ViewModels?**
A: Use JUnit, MockK/Mockito for dependencies, LiveData testing utilities, and InstantTaskExecutorRule for testing.

### Architecture Advanced

**Q: What is MVI (Model-View-Intent) pattern?**
A: MVI is a unidirectional data flow pattern where user intents trigger actions that update the model, which then updates the view.

**Q: How do you implement offline-first architecture?**
A: Use Room for local storage, implement sync mechanisms, handle conflicts, and provide seamless offline experience.

**Q: What is modularization and its benefits?**
A: Modularization splits app into feature modules, improving build times, enabling dynamic features, and better code organization.

**Q: How do you implement feature flags in Android?**
A: Use remote config services (Firebase Remote Config), implement local flag management, and A/B testing frameworks.

### DevOps & CI/CD

**Q: How do you implement automated testing in CI/CD?**
A: Set up unit tests, UI tests, use cloud testing services, implement test reports, and fail builds on test failures.

**Q: What is Gradle and how do you optimize build times?**
A: Gradle is Android's build system. Optimize with: parallel builds, build cache, avoid unnecessary dependencies, and use build variants.

**Q: How do you implement code quality checks?**
A: Use static analysis tools (detekt, ktlint), SonarQube, implement git hooks, and code review processes.

**Q: What are build flavors and build types?**
A: 
- **Build types**: Debug/Release configurations
- **Build flavors**: Different versions of app (free/paid, different environments)

### Kotlin Advanced

**Q: What are coroutines channels and when to use them?**
A: Channels are communication primitives for coroutines, used for producer-consumer scenarios and hot data streams.

**Q: What is the difference between runBlocking and coroutineScope?**
A: 
- **runBlocking**: Blocks current thread until completion
- **coroutineScope**: Suspends without blocking thread

**Q: How do you handle exceptions in coroutines?**
A: Use try-catch blocks, CoroutineExceptionHandler, SupervisorJob, and proper structured concurrency.

**Q: What are sealed interfaces in Kotlin?**
A: Sealed interfaces (Kotlin 1.5+) provide sealed functionality for interfaces, allowing restricted inheritance hierarchies.

### Android Framework Deep Dive

**Q: What is the Android Application class and when to use it?**
A: Application class is the base class for maintaining global application state, used for app-wide initialization and shared resources.

**Q: How does the Android memory management work?**
A: Android uses automatic memory management with garbage collection, low memory killer, and process importance hierarchy.

**Q: What is the difference between Context, Activity Context, and Application Context?**
A: 
- **Context**: Abstract base class for accessing app resources
- **Activity Context**: Tied to activity lifecycle
- **Application Context**: Tied to application lifecycle

**Q: How do you handle configuration changes properly?**
A: Use ViewModel, save state in onSaveInstanceState, handle orientation changes, and use retained fragments when needed.

This comprehensive guide covers questions from junior to senior level Android development, providing a solid foundation for interview preparation and knowledge assessment.
