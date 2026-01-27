# Local Storage Options

## Question
What are the different options for local data storage in Flutter?

## Answer
Flutter provides several options for storing data locally on the device, each suited for different use cases.

### Storage Options:

1. **SharedPreferences**: Simple key-value storage for small data
2. **SQLite**: Relational database for complex data structures
3. **Hive**: Fast, lightweight NoSQL database
4. **sqflite**: SQLite plugin for Flutter
5. **path_provider**: Access to device file system paths
6. **File Storage**: Direct file read/write operations

### Code Example
```dart
// SharedPreferences
import 'package:shared_preferences/shared_preferences.dart';

// Save data
Future<void> saveData() async {
  final prefs = await SharedPreferences.getInstance();
  await prefs.setString('username', 'john_doe');
  await prefs.setInt('age', 25);
  await prefs.setBool('isLoggedIn', true);
}

// Read data
Future<void> readData() async {
  final prefs = await SharedPreferences.getInstance();
  final username = prefs.getString('username');
  final age = prefs.getInt('age');
  final isLoggedIn = prefs.getBool('isLoggedIn');
}

// SQLite (sqflite)
import 'package:sqflite/sqflite.dart';

Future<Database> initDatabase() async {
  return await openDatabase(
    'my_database.db',
    version: 1,
    onCreate: (db, version) {
      db.execute('''
        CREATE TABLE users(
          id INTEGER PRIMARY KEY,
          name TEXT,
          email TEXT
        )
      ''');
    },
  );
}
```

## Key Points
- SharedPreferences: Best for simple key-value pairs (settings, user preferences)
- SQLite: Best for structured, relational data
- Hive: Fast and efficient for NoSQL data
- Choose based on data complexity and performance needs
- Always handle async operations properly

## Related Topics
- [SQLite Database](./02-sqlite-database.md)
- [SharedPreferences](./03-shared-preferences.md)

## Difficulty Level
- [x] Beginner
- [ ] Intermediate
- [ ] Advanced

## Status
- [ ] Reviewed
- [ ] Understood
- [ ] Needs Practice
