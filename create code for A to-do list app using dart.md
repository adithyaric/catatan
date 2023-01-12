Sure! Here is some example code for a simple to-do list app using the Dart programming language:

```dart
import 'package:flutter/material.dart';

void main() => runApp(TodoApp());

class TodoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Todo List',
      home: TodoList(),
    );
  }
}

class TodoList extends StatefulWidget {
  @override
  _TodoListState createState() => _TodoListState();
}

class _TodoListState extends State<TodoList> {
  List<String> _todos = [];

  void _addTodo(String task) {
    setState(() {
      _todos.add(task);
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Todo List'),
      ),
      body: Column(
        children: <Widget>[
          Expanded(
            child: ListView.builder(
              itemCount: _todos.length,
              itemBuilder: (context, index) {
                return ListTile(
                  title: Text(_todos[index]),
                );
              },
            ),
          ),
          AddTodo(_addTodo),
        ],
      ),
    );
  }
}

class AddTodo extends StatefulWidget {
  final Function addTodo;

  AddTodo(this.addTodo);

  @override
  _AddTodoState createState() => _AddTodoState();
}

class _AddTodoState extends State<AddTodo> {
  final _formKey = GlobalKey<FormState>();
  String _task;

  void _submit() {
    if (_formKey.currentState.validate()) {
      _formKey.currentState.save();
      widget.addTodo(_task);
      Navigator.pop(context);
    }
  }

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      child: Column(
        children: <Widget>[
          TextFormField(
            validator: (value) {
              if (value.isEmpty) {
                return 'Please enter some text';
              }
              return null;
            },
            onSaved: (value) => _task = value,
            decoration: InputDecoration(hintText: 'Task'),
          ),
          RaisedButton(
            onPressed: _submit,
            child: Text('Add'),
          ),
        ],
      ),
    );
  }
}

```

This code defines a `TodoApp` that displays a list of to-do items and provides a form to add new items. The app has a single `Scaffold` with an `AppBar` at the top and a column containing an `Expanded` list view of to-do items and an `AddTodo` form at the bottom.

The `TodoList` widget manages a list of to-do items and displays them using a list view