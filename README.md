<!-- # readcross

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.


# 1. Introduction

Flutter is Google's UI toolkit for building applications for mobile, web, and desktop from a single codebase. In this codelab, you will build the following Flutter application:

The application generates cool-sounding names, such as "newstay", "lightstream", "mainbrake", or "graypine". The user can ask for the next name, favorite the current one, and review the list of favorited names on a separate page. The app is responsive to different screen sizes.

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/1d26af443561f39c.gif)


## What you'll learn

    The basics of how Flutter works
    Creating layouts in Flutter
    Connecting user interactions (like button presses) to app behavior
    Keeping your Flutter code organized
    Making your app responsive (for different screens)
    Achieving a consistent look & feel of your app

    [-] flutter pub add english_words
    [-] english_words: ^4.0.0
    [-] provider: ^6.0.0


You'll start with a basic scaffold so that you can jump straight to the interesting parts.

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/d6e3d5f736411f13_856.png)

# 2. Set up your Flutter environment

# Editor

To make this codelab as straightforward as possible, we assume you'll use Visual Studio Code (VS Code) as your development environment. It's free and works on all major platforms.



Of course it's fine to use any editor you like: Android Studio, other IntelliJ IDEs, Emacs, Vim, or Notepad++. They all work with Flutter.

We recommend using VS Code for this codelab because the instructions default to VS Code-specific shortcuts. It's easier to say things like "click here" or "press this key" instead of something like "do the appropriate action in your editor to do X".
![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/15961a28a4500ac1_856.png)

# Choose a development target

## Flutter is a multi-platform toolkit. Your app can run on any of the following operating systems:

    iOS
    Android
    Windows
    macOS
    Linux
    web

However, it's common practice to choose a single operating system for which you will primarily develop. This is your "development target"—the operating system that your app runs on during development.

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/d105428cb3aae7d5_856.png)

For example, say you're using a Windows laptop to develop a Flutter app. If you choose Android as your development target, you typically attach an Android device to your Windows laptop with a USB cable, and your app-in-development runs on that attached Android device. But you could also choose Windows as the development target, which means your app-in-development runs as a Windows app alongside your editor.

**Tip: We strongly recommend choosing your development device's Operating System as your development target. So, for example, if your computer runs Windows, choose Windows as the development target.**

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/6bfd4ef44ca74791_856.png)


It might be tempting to select the web as your development target. The downside of this choice is that you lose one of Flutter's most useful development features: Stateful Hot Reload. Flutter can't hot-reload web applications.

Make your choice now. Remember: You can always run your app on other operating systems later. It's just that having a clear development target in mind makes the next step smoother.

Install Flutter

The most up-to-date instructions on how to install the Flutter SDK are always at ![Alt Text](docs.flutter.dev)

<button>google.com</button>

The instructions on the Flutter website cover not only the installation of the SDK itself, but also the development target-related tools and the editor plugins. Remember that, for this codelab, you only need to install the following:

    Flutter SDK
    Visual Studio Code with the Flutter plugin
    The software required by your chosen development target (for example: Visual Studio to target Windows, or Xcode to target macOS)

In the next section, you'll create your first Flutter project.

If you've had problems so far, you might find some of these questions and answers (from StackOverflow) helpful for troubleshooting.

# Create a project

## Create your first Flutter project

Launch Visual Studio Code and open the command palette (with F1 or Ctrl+Shift+P or Shift+Cmd+P). Start typing "flutter new". Select the Flutter: New Project command.

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/58e8487afebfc1dd.gif)


Next, select Application and then a folder in which to create your project. This could be your home directory, or something like C:\src\.

Finally, name your project. Something like namer_app or my_awesome_namer.
![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/260a7d97f9678005_856.png)

Flutter now creates your project folder and VS Code opens it.

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/756a9586aacb2bda_856.png)

**Select Yes. The other option disables substantial Flutter functionality.**

######
You'll now overwrite the contents of 3 files with a basic scaffold of the app.
Copy & Paste the initial app

In the left pane of VS Code, make sure that Explorer is selected, and open the pubspec.yaml file.

# 4. Add a button

This step adds a Next button to generate a new word pairing.
Launch the app

First, open lib/main.dart and make sure that you have your target device selected. At the bottom right corner of VS Code, you'll find a button that shows the current target device. Click to change it.

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/6c4474b4b5e92ffb.gif)

**While lib/main.dart is open, find the "play" b0a5d0200af5985d.png button in the upper right-hand corner of VS Code's window, and click it.**

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/9b7598a38a6412e6.gif)

After about a minute, your app launches in debug mode. It doesn't look like much yet:
![Alt Text](/readcross/asset/demo1.png)

## First Hot Reload
At the bottom of lib/main.dart, add something to the string in the first Text object, and save the file (with Ctrl+S or Cmd+S). For example:

```dart
// ...

    return Scaffold(
      body: Column(
        children: [
          Text('A random AWESOME idea:'),  // ← Example change.
          Text(appState.current.asLowerCase),
        ],
      ),
    );

// ...
```

### Notice how the app changes immediately but the random word stays the same. This is Flutter's famous stateful Hot Reload at work. Hot reload is triggered when you save changes to a source file.

## Adding a button

Next, add a button at the bottom of the Column, right below the second Text instance.

* lib/main.dart

```dart
// ...

    return Scaffold(
      body: Column(
        children: [
          Text('A random AWESOME idea:'),
          Text(appState.current.asLowerCase),

          // ↓ Add this.
          ElevatedButton(
            onPressed: () {
              print('button pressed!');
            },
            child: Text('Next'),
          ),

        ],
      ),
    );

// ...
```

###### When you save the change, the app updates again: A button appears and, when you click it, the Debug Console in VS Code shows a button pressed! message.

![Alt Text](/readcross/asset/demo2.png)

## A Flutter crash course in 5 minutes

As much fun as it is to watch the Debug Console, you want the button to do something more meaningful. Before getting to that, though, take a closer look at the code in ***lib/main.dart***, to understand how it works.

***lib/main.dart***

```dart
// ...

void main() {
  runApp(MyApp());
}

// ...
```

### At the very top of the file, you'll find the main() function. In its current form, it only tells Flutter to run the app defined in MyApp.

**lib/main.dart**
```dart
// ...

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => MyAppState(),
      child: MaterialApp(
        title: 'Namer App',
        theme: ThemeData(
          useMaterial3: true,
          colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepOrange),
        ),
        home: MyHomePage(),
      ),
    );
  }
}

// ...
```

$ The MyApp class extends StatelessWidget. Widgets are the elements from which you build every Flutter app. As you can see, even the app itself is a widget.

## Note: We'll get to the explanation of StatelessWidget (versus StatefulWidget) later.

The code in MyApp sets up the whole app. It creates the app-wide state (more on this later), names the app, defines the visual theme, and sets the "home" widget—the starting point of your app.

```dart
// ...

class MyAppState extends ChangeNotifier {
  var current = WordPair.random();
}

// ...
```

Next, the MyAppState class defines the app's...well...state. This is your first foray into Flutter, so this codelab will keep it simple and focused. There are many powerful ways to manage app state in Flutter. One of the easiest to explain is ChangeNotifier, the approach taken by this app.

    MyAppState defines the data the app needs to function. Right now, it only contains a single variable with the current random word pair. You will add to this later.
    The state class extends ChangeNotifier, which means that it can notify others about its own changes. For example, if the current word pair changes, some widgets in the app need to know.
    The state is created and provided to the whole app using a ChangeNotifierProvider (see code above in MyApp). This allows any widget in the app to get hold of the state

   ![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/d9b6ecac5494a6ff_856.png)
   
   ```dart
   // ...

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {           // ← 1
    var appState = context.watch<MyAppState>();  // ← 2

    return Scaffold(   // ← 3
      body: Column(    // ← 4
        children: [
          Text('A random AWESOME idea:'),        // ← 5
          Text(appState.current.asLowerCase),    // ← 6
          ElevatedButton(
            onPressed: () {
              print('button pressed!');
            },
            child: Text('Next'),
          ),
        ],      // ← 7
      ),
    );
  }
}

// ...
```

Lastly, there's MyHomePage, the widget you've already modified. Each numbered line below maps to a line-number comment in the code above:

    Every widget defines a build() method that's automatically called every time the widget's circumstances change so that the widget is always up to date.
    MyHomePage tracks changes to the app's current state using the watch method.
    Every build method must return a widget or (more typically) a nested tree of widgets. In this case, the top-level widget is Scaffold. You aren't going to work with Scaffold in this codelab, but it's a helpful widget and is found in the vast majority of real-world Flutter apps.
    Column is one of the most basic layout widgets in Flutter. It takes any number of children and puts them in a column from top to bottom. By default, the column visually places its children at the top. You'll soon change this so that the column is centered.
    You changed this Text widget in the first step.
    This second Text widget takes appState, and accesses the only member of that class, current (which is a WordPair). WordPair provides several helpful getters, such as asPascalCase or asSnakeCase. Here, we use asLowerCase but you can change this now if you prefer one of the alternatives.
    Notice how Flutter code makes heavy use of trailing commas. This particular comma doesn't need to be here, because children is the last (and also only) member of this particular Column parameter list. Yet it is generally a good idea to use trailing commas: they make adding more members trivial, and they also serve as a hint for Dart's auto-formatter to put a newline there. For more information, see Code formatting.

## Next, you'll connect the button to the state.

# Your first behavior

Scroll to MyAppState and add a getNext method.

<mark>lib/main.dart</mark>
```dart
// ...

class MyAppState extends ChangeNotifier {
  var current = WordPair.random();

  // ↓ Add this.
  void getNext() {
    current = WordPair.random();
    notifyListeners();
  }
}

// ...
```


The new <mark>getNext()</mark> method reassigns current with a new random WordPair. It also calls <mark>notifyListeners()</mark>(a method of ChangeNotifier)that ensures that anyone watching MyAppState is notified.

All that remains is to call the getNext method from the button's callback

<mark>lib/main.dart</mark>
```dart
// ...

    ElevatedButton(
      onPressed: () {
        appState.getNext();  // ← This instead of print().
      },
      child: Text('Next'),
    ),

// ...
```


Save and try the app now. It should generate a new random word pair every time you press the Next button.

In the next section, you'll make the user interface prettier.sssss


# 5. Make the app prettier

This is how the app looks at the moment.
![Alt Text](/readcross/asset/demo3.png)


<mark>Not great</mark>. The centerpiece of the app—the randomly generated pair of words—should be more visible. It is, after all, the main reason our users are using this app! Also, the app contents are weirdly off-center, and the whole app is boringly black & white.

This section addresses these issues by working on the app's design. The end goal for this section is something like the following:

![Alt Text](https://codelabs.developers.google.com/static/codelabs/flutter-codelab-first/img/2bbee054d81a3127_856.png)

# Extract a widget -->
<!-- 
The line responsible for showing the current word pair looks like this now: <mark>Text(appState.current.asLowerCase)</mark>. To change it into something more complex, it's a good idea to extract this line into a separate widget. Having separate widgets for separate logical parts of your UI is an important way of managing complexity in Flutter.

Flutter provides a refactoring helper for extracting widgets but before you use it, make sure that the line being extracted only accesses what it needs. Right now, the line accesses <mark> appState</mark>, but really only needs to know what the current word pair is.

For that reason, rewrite the MyHomePage widget as follows: -->

# Flutter app that covers some of the essential concepts:

This app displays a counter that increments every time the user taps a button. Here's an overview of some of the essential Flutter concepts that this app covers:

* <mark style="background-color: #caafed">MaterialApp </mark>: This widget creates a new Material Design app with a title and a home page.
* <mark style="background-color: #caafed">Scaffold </mark>: This widget provides a basic app structure, including an app bar, a body, and a floating action button.
* <mark style="background-color: #caafed">AppBar </mark>: This widget displays a top app bar with a title.
* <mark style="background-color: #caafed">Center </mark>:  This widget centers its child horizontally and vertically.
* <mark style="background-color: #caafed">Column </mark>: This widget displays its children in a vertical column.
* <mark style="background-color: #caafed">Text </mark>: This widget displays text.
* <mark style="background-color: #caafed">StatefulWidget and State </mark> :  These classes allow you to create widgets with mutable state that can be updated and rebuilt.
* <mark style="background-color: #caafed">setState</mark>: This method is called when the state of a StatefulWidget changes. It tells Flutter to rebuild the widget tree with the updated state.
* <mark style="background-color: #caafed"> FloatingActionButton </mark>: This widget displays a button that hovers above the app and provides quick access to a primary action.

**NB:** This is just a simple example, but it covers many of the essential concepts you'll need to know to build more complex Flutter apps.

# let's talk about `StatefulWidget`  and   `StatelessWidget` in Flutter.

Both `StatefulWidget` and `StatelessWidget` are classes in Flutter that are used to create `UI components`. However, they differ in how they `handle state`



* `StatelessWidget` is a widget that doesn't have mutable state. This means that once a `StatelessWidget` is built, its contents cannot be updated. 
* A  `StatelessWidget`  is typically used for displaying static content that doesn't change, such as text, images, or icons.

Here's an example of a  `StatelessWidget ` that displays a simple message:

```dart
class MyMessage extends StatelessWidget {
  final String message;

  MyMessage({required this.message});

  @override
  Widget build(BuildContext context) {
    return Text(message);
  }
}
```

In the example above, the <mark style="background-color:#ccc"> MyMessage</mark> class extends <mark style="background-color:#ccc"> StatelessWidget</mark> and takes a message <mark style="background-color:#ccc">parameter</mark> in its constructor. When the widget is built, it simply displays the message `string` using a `Text` `widget`.

* `StatefulWidget`, on the other hand, is a widget that has mutable state. This means that the contents of a `StatefulWidget` can change over time. 
* A `StatefulWidget` is typically used for displaying dynamic content that can change based on user input or other factors.


Here's an example of a <mark>StatefulWidget</mark> that displays a counter:

```dart
class MyCounter extends StatefulWidget {
  @override
  _MyCounterState createState() => _MyCounterState();
}

class _MyCounterState extends State<MyCounter> {
  int _count = 0;

  void _incrementCounter() {
    setState(() {
      _count++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Count: $_count'),
        ElevatedButton(
          onPressed: _incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

In the example above, the `MyCounter` class extends `StatefulWidget` and creates a `_MyCounterState` object to manage its `mutable state`. The` _MyCounterState` class has a private` _count `variable that tracks the current count, and an _incrementCounter() method that updates the count and calls setState() to rebuild the widget tree. The build() method displays the current count and a button that calls `_incrementCounter() `when `pressed.`


**NB:** These are just some examples of how StatefulWidget and StatelessWidget can be used in Flutter. Choosing between them depends on the specific needs of your app and the components you're building. If you need to display dynamic content that can change over time, use a StatefulWidget. If you're displaying static content that doesn't change, use a StatelessWidget.

``THANK FOR YOUR TIME AND KIND`` for any `support` you can reach out to `me`

* [Contact me](mailto:josephlearnwith@gmail.com)
* [Twitter](https://twitter.com/@josehub121)
* [YouTube](https://www.youtube.com/@learnwithjoseph)
* [Github](https://github.com/fhub-1)

