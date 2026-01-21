# Navigation Basics

## Question
How does navigation work in Flutter? Explain Navigator and routes.

## Answer
Navigation in Flutter is handled by the `Navigator` widget, which manages a stack of routes (screens). You can navigate forward to new routes or backward to previous routes.

### Key Concepts:

1. **Navigator**: Manages a stack of Route objects
2. **Route**: Represents a screen or page in the app
3. **MaterialPageRoute**: Default route that transitions with platform-appropriate animations
4. **Named Routes**: Routes identified by string names
5. **Route Arguments**: Passing data between screens

### Code Example
```dart
// Basic Navigation
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => SecondScreen(),
  ),
);

// Navigation with Arguments
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => DetailScreen(data: 'Hello'),
  ),
);

// Named Routes (in MaterialApp)
MaterialApp(
  initialRoute: '/',
  routes: {
    '/': (context) => HomeScreen(),
    '/details': (context) => DetailScreen(),
  },
);

// Using Named Routes
Navigator.pushNamed(context, '/details');

// Going Back
Navigator.pop(context);

// Returning Data
Navigator.pop(context, 'Returned Data');
```

## Key Points
- Navigator manages a stack of routes
- push() adds a new route to the stack
- pop() removes the current route
- Named routes make navigation more maintainable
- You can pass data when navigating and when returning

## Related Topics
- [Named Routes](./02-named-routes.md)
- [Deep Linking](./03-deep-linking.md)

## Difficulty Level
- [x] Beginner
- [ ] Intermediate
- [ ] Advanced

## Status
- [ ] Reviewed
- [ ] Understood
- [ ] Needs Practice
