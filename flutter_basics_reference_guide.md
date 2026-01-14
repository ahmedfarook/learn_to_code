# Flutter Basics – Quick Reference Guide

## 1. Flutter ka Core Concept
Flutter me **sab kuch Widget hota hai**. Screen, button, text, padding – sab widget.

Flutter ka kaam:
- Widget Tree banana
- Jab data change ho to UI ko redraw karna

---

## 2. Flutter App ka Common Flow

```text
main()
 ↓
runApp()
 ↓
MaterialApp
 ↓
Scaffold
 ↓
AppBar + Body
 ↓
Widgets (Text, Button, List, Image)
```

---

## 3. main() aur runApp()

```dart
void main() {
  runApp(const MyApp());
}
```

- `main()` = entry point
- `runApp()` = root widget attach karta hai

---

## 4. MaterialApp (App ka Base)

Use for:
- Theme
- Navigation
- Title
- Debug banner

```dart
MaterialApp(
  title: 'My App',
  home: HomePage(),
)
```

---

## 5. Scaffold (Screen ka Structure)

```dart
Scaffold(
  appBar: AppBar(),
  body: Center(),
)
```

Scaffold deta hai:
- AppBar
- Body
- FloatingActionButton
- Drawer
- BottomNavigationBar

---

## 6. AppBar

```dart
AppBar(
  title: Text('Home'),
)
```

- Screen ke top pe hota hai
- Title, actions, backgroundColor

---

## 7. Body

Body me actual UI hota hai:

```dart
body: Center(
  child: Text('Hello Flutter'),
)
```

---

## 8. Commonly Used Widgets

| Widget | Kaam |
|------|------|
| Text | Text dikhana |
| Container | Box (color, size) |
| Row | Horizontal layout |
| Column | Vertical layout |
| Center | Center align |
| Padding | Inner space |
| SizedBox | Space dena |
| Image | Image dikhana |
| ListView | Scrollable list |

---

## 9. StatelessWidget

Use jab **data change nahi hota**

```dart
class MyText extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('Fixed Text');
  }
}
```

Examples:
- Static text
- Icons
- UI jo kabhi update nahi hota

---

## 10. StatefulWidget

Use jab **data change hota hai**

```dart
class Counter extends StatefulWidget {
  @override
  State<Counter> createState() => _CounterState();
}

class _CounterState extends State<Counter> {
  int count = 0;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('$count'),
        ElevatedButton(
          onPressed: () {
            setState(() {
              count++;
            });
          },
          child: Text('Add'),
        )
      ],
    );
  }
}
```

---

## 11. setState() – Golden Rule

> Jab bhi UI update chahiye → `setState()`

- `setState()` build method dobara call karta hai
- UI refresh hota hai

---

## 12. Stateful Widget Lifecycle (Simple)

```text
createState()
 ↓
initState()  (one time)
 ↓
build()      (multiple times)
 ↓
setState()
 ↓
build() again
 ↓
dispose()
```

---

## 13. Flutter Me Confusion Ho To Ye Pucho

1. Kya data change hoga?
   - Yes → StatefulWidget
   - No → StatelessWidget

2. Layout issue?
   - Row / Column / Expanded

3. Click handle karna?
   - Button / GestureDetector

---

## 14. Short Cheat Sheet

```text
MaterialApp → App config
Scaffold    → Screen structure
AppBar      → Top bar
Body        → Screen content
setState()  → UI refresh
```

---

## 15. Next Topics to Add Later
- Navigation (Navigator.push)
- Forms & TextField
- API calling
- State management (Provider / Riverpod)
- Firebase integration

---

**Use this document as your personal Flutter notebook.**
Slow but solid progress = long-term success 💪