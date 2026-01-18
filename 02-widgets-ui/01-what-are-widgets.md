# What are Widgets?

## Question
What are widgets in Flutter? Explain the difference between StatelessWidget and StatefulWidget.

## Answer
In Flutter, **everything is a widget**. Widgets are the basic building blocks of a Flutter application's user interface. They describe what their view should look like given their current configuration and state.

### Types of Widgets:

1. **StatelessWidget**: A widget that does not require mutable state
   - Immutable once built
   - Cannot change over time
   - More efficient (no state management overhead)

2. **StatefulWidget**: A widget that has mutable state
   - Can change dynamically
   - Maintains state that might change during the widget's lifetime
   - Uses a separate State object to hold mutable state

### Code Example
```dart
// StatelessWidget Example
class MyStatelessWidget extends StatelessWidget {
  final String title;
  
  const MyStatelessWidget({Key? key, required this.title}) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return Text(title);
  }
}

// StatefulWidget Example
class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Counter: $_counter'),
        ElevatedButton(
          onPressed: _incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

## Key Points
- Widgets are immutable (except StatefulWidget's State)
- StatelessWidget is for static content
- StatefulWidget is for dynamic content that changes
- Always use StatelessWidget when possible for better performance
- setState() triggers a rebuild of the widget tree

## Related Topics
- [Widget Lifecycle](./02-widget-lifecycle.md)
- [State Management](./../03-state-management/01-introduction-to-state.md)

## Difficulty Level
- [x] Beginner
- [ ] Intermediate
- [ ] Advanced

## Status
- [ ] Reviewed
- [ ] Understood
- [ ] Needs Practice
