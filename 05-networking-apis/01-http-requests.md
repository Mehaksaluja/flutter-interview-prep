# HTTP Requests in Flutter

## Question
How do you make HTTP requests in Flutter? Explain the http package and best practices.

## Answer
Flutter uses the `http` package (or `dio` package) to make HTTP requests. The `http` package provides a simple way to perform GET, POST, PUT, DELETE, and other HTTP methods.

### Key Concepts:

1. **http package**: Official package for HTTP requests
2. **Future-based**: Returns Future objects for async operations
3. **JSON parsing**: Use `dart:convert` for JSON encoding/decoding
4. **Error handling**: Always handle network errors and exceptions
5. **State management**: Update UI based on loading/success/error states

### Code Example
```dart
import 'package:http/http.dart' as http;
import 'dart:convert';

// GET Request
Future<Map<String, dynamic>> fetchUser(int userId) async {
  try {
    final response = await http.get(
      Uri.parse('https://api.example.com/users/$userId'),
      headers: {'Content-Type': 'application/json'},
    );
    
    if (response.statusCode == 200) {
      return json.decode(response.body);
    } else {
      throw Exception('Failed to load user');
    }
  } catch (e) {
    throw Exception('Network error: $e');
  }
}

// POST Request
Future<Map<String, dynamic>> createUser(String name, String email) async {
  try {
    final response = await http.post(
      Uri.parse('https://api.example.com/users'),
      headers: {'Content-Type': 'application/json'},
      body: json.encode({
        'name': name,
        'email': email,
      }),
    );
    
    if (response.statusCode == 201) {
      return json.decode(response.body);
    } else {
      throw Exception('Failed to create user');
    }
  } catch (e) {
    throw Exception('Network error: $e');
  }
}
```

## Key Points
- Always use try-catch for error handling
- Check statusCode before processing response
- Use async/await for asynchronous operations
- Consider using dio package for advanced features (interceptors, timeouts)
- Handle loading, success, and error states in UI

## Related Topics
- [REST API Integration](./02-rest-api-integration.md)
- [Error Handling](./03-error-handling.md)

## Difficulty Level
- [x] Beginner
- [ ] Intermediate
- [ ] Advanced

## Status
- [ ] Reviewed
- [ ] Understood
- [ ] Needs Practice
