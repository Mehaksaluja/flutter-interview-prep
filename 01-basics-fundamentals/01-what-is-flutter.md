# What is Flutter?

## Question
What is Flutter and what are its key features?

## Answer
Flutter is an open-source UI software development kit (SDK) created by Google. It allows developers to build natively compiled applications for mobile, web, desktop, and embedded devices from a single codebase using the Dart programming language.

### Key Features:

1. **Cross-Platform Development**: Write once, run on multiple platforms (iOS, Android, Web, Desktop)
2. **Hot Reload**: See changes instantly without losing app state
3. **Widget-Based Architecture**: Everything is a widget, providing a consistent UI framework
4. **High Performance**: Compiles to native ARM code for mobile platforms
5. **Rich Widget Library**: Extensive collection of Material Design and Cupertino widgets
6. **Dart Language**: Modern, object-oriented language optimized for UI development

### Code Example
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      home: Scaffold(
        appBar: AppBar(title: Text('Hello Flutter')),
        body: Center(
          child: Text('Welcome to Flutter!'),
        ),
      ),
    );
  }
}
```

## Key Points
- Flutter uses Dart programming language
- Single codebase for multiple platforms
- Compiles to native code (not interpreted)
- Widget-based reactive framework
- Strong performance due to direct compilation

## Related Topics
- [Dart Language Basics](./02-dart-language-basics.md)
- [Widget Tree](./03-widget-tree.md)

## Difficulty Level
- [x] Beginner
- [ ] Intermediate
- [ ] Advanced

## Status
- [ ] Reviewed
- [ ] Understood
- [ ] Needs Practice
