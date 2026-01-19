# Dart Language Basics

## Question
What are the key features of the Dart programming language used in Flutter?

## Answer
Dart is a client-optimized language for fast apps on any platform. It's the language Flutter uses and has several important features:

### Key Features:

1. **Object-Oriented**: Everything is an object, including numbers and functions
2. **Type Safety**: Supports both static and dynamic typing
3. **Null Safety**: Prevents null reference errors (introduced in Dart 2.12)
4. **Async/Await**: Built-in support for asynchronous programming
5. **Mixins**: Support for multiple inheritance through mixins
6. **Generics**: Type-safe collections and functions
7. **Isolates**: Concurrency model for parallel execution

### Code Example
```dart
// Null Safety
String? nullableString; // Can be null
String nonNullableString = 'Hello'; // Cannot be null

// Async/Await
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 1));
  return 'Data loaded';
}

// Generics
List<String> names = ['Alice', 'Bob'];
Map<String, int> ages = {'Alice': 30, 'Bob': 25};

// Mixins
mixin Flyable {
  void fly() => print('Flying');
}

class Bird with Flyable {
  // Bird can now use fly() method
}
```

## Key Points
- Dart is strongly typed but supports type inference
- Null safety prevents common null reference errors
- Async/await makes asynchronous code readable
- Everything in Dart is an object
- Dart supports both JIT (Just-In-Time) and AOT (Ahead-Of-Time) compilation

## Related Topics
- [What is Flutter](./01-what-is-flutter.md)
- [Async Programming](./04-async-programming.md)

## Difficulty Level
- [x] Beginner
- [ ] Intermediate
- [ ] Advanced

## Status
- [ ] Reviewed
- [ ] Understood
- [ ] Needs Practice
