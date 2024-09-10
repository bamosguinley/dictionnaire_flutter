## **Cours Complet sur Dart**

### **1. Introduction à Dart**

Dart est un langage de programmation développé par Google, principalement utilisé pour le développement d'applications web et mobiles avec le framework Flutter. Dart est orienté objet et dispose d'une syntaxe moderne, inspirée de langages comme JavaScript, Java et C#.

### **2. Syntaxe de Base**

#### **2.1 Variables et Types**

- **Déclaration des Variables**
  ```dart
  var name = 'Alice'; // Variable modifiable
  final age = 30;     // Variable non modifiable après l'initialisation
  const pi = 3.14;    // Constante de compilation
  ```

- **Types de Données**
  ```dart
  int count = 5;
  double price = 19.99;
  String message = 'Hello, Dart!';
  bool isValid = true;
  List<int> numbers = [1, 2, 3];
  Map<String, int> scores = {'Alice': 90, 'Bob': 80};
  ```

#### **2.2 Structures de Contrôle**

- **Conditionnelles**
  ```dart
  if (count > 10) {
    print('Count is greater than 10');
  } else {
    print('Count is 10 or less');
  }
  ```

- **Boucles**
  ```dart
  for (var i = 0; i < 5; i++) {
    print(i);
  }
  
  numbers.forEach((num) => print(num));
  ```

### **3. Fonctions et Méthodes**

#### **3.1 Déclaration de Fonction**
```dart
int add(int a, int b) {
  return a + b;
}
```

#### **3.2 Fonctions Anonymes (Lambda)**
```dart
var multiply = (int a, int b) => a * b;
```

### **4. Programmation Orientée Objet**

#### **4.1 Classes et Objets**
```dart
class Person {
  String name;
  int age;

  Person(this.name, this.age);

  void greet() {
    print('Hello, my name is $name');
  }
}

var person = Person('Alice', 30);
person.greet();  // Output: Hello, my name is Alice
```

#### **4.2 Héritage**
```dart
class Animal {
  void speak() {
    print('Animal sound');
  }
}

class Dog extends Animal {
  @override
  void speak() {
    print('Woof');
  }
}

var dog = Dog();
dog.speak();  // Output: Woof
```

### **5. Asynchronisme**

#### **5.1 Futures et Async/Await**

- **Future** : Représente une opération qui sera complétée dans le futur.
  ```dart
  Future<String> fetchData() async {
    return Future.delayed(Duration(seconds: 2), () => 'Data received');
  }
  ```

- **Async/Await**
  ```dart
  void fetchAndPrint() async {
    String data = await fetchData();
    print(data);
  }
  ```

### **6. Collections**

Les collections en Dart incluent les listes (`List`), les ensembles (`Set`), et les cartes (`Map`). Voici un aperçu complet de chaque type.

#### **6.1 List**

Les listes sont des collections ordonnées d'objets, accessibles par un index.

- **Création d'une Liste**
  ```dart
  List<int> numbers = [1, 2, 3];
  List<String> fruits = ['apple', 'banana', 'cherry'];
  ```

- **Accès aux Éléments**
  ```dart
  var firstFruit = fruits[0]; // 'apple'
  var count = fruits.length; // 3
  ```

- **Méthodes de Base**
  - **Ajout d'Éléments**
    ```dart
    fruits.add('date');
    fruits.addAll(['elderberry', 'fig']);
    ```
  - **Insertion d'Éléments**
    ```dart
    fruits.insert(1, 'blueberry');
    fruits.insertAll(2, ['grape', 'honeydew']);
    ```
  - **Suppression d'Éléments**
    ```dart
    fruits.remove('banana');
    fruits.removeAt(2);
    fruits.removeLast();
    ```
  - **Modification d'Éléments**
    ```dart
    fruits[0] = 'pear';
    ```
  - **Recherche d'Éléments**
    ```dart
    bool hasApple = fruits.contains('apple');
    int index = fruits.indexOf('cherry');
    ```
  - **Itération**
    ```dart
    fruits.forEach((fruit) => print(fruit));
    for (var fruit in fruits) {
      print(fruit);
    }
    ```

- **Opérations Avancées**
  - **Transformation avec `map`**
    ```dart
    var fruitLengths = fruits.map((fruit) => fruit.length).toList();
    ```
  - **Filtrage avec `where`**
    ```dart
    var longFruits = fruits.where((fruit) => fruit.length > 5).toList();
    ```
  - **Réduction avec `reduce`**
    ```dart
    var totalLength = fruits.map((fruit) => fruit.length).reduce((a, b) => a + b);
    ```
  - **Accumulateur avec `fold`**
    ```dart
    var totalLength = fruits.fold(0, (prev, fruit) => prev + fruit.length);
    ```
  - **Tri avec `sort`**
    ```dart
    fruits.sort();
    ```
  - **Inversion avec `reversed`**
    ```dart
    var reversedFruits = fruits.reversed.toList();
    ```

#### **6.2 Set**

Les ensembles (`Set`) sont des collections non ordonnées d'éléments uniques.

- **Création d'un Ensemble**
  ```dart
  Set<int> numbers = {1, 2, 3};
  Set<String> names = {'Alice', 'Bob', 'Charlie'};
  ```

- **Accès et Modification**
  ```dart
  bool containsAlice = names.contains('Alice');
  numbers.add(4);
  numbers.remove(2);
  ```

- **Opérations avec Ensembles**
  - **Union**
    ```dart
    Set<int> moreNumbers = {3, 4, 5};
    Set<int> allNumbers = numbers.union(moreNumbers);
    ```
  - **Intersection**
    ```dart
    Set<int> commonNumbers = numbers.intersection(moreNumbers);
    ```
  - **Différence**
    ```dart
    Set<int> uniqueNumbers = numbers.difference(moreNumbers);
    ```

- **Itération**
  ```dart
  names.forEach((name) => print(name));
  for (var name in names) {
    print(name);
  }
  ```

#### **6.3 Map**

Les cartes (`Map`) sont des collections de paires clé-valeur.

- **Création d'une Carte**
  ```dart
  Map<String, int> ages = {'Alice': 30, 'Bob': 25};
  ```

- **Accès et Modification**
  ```dart
  int aliceAge = ages['Alice'];
  ages['Charlie'] = 35;
  ```

- **Méthodes Utiles**
  - **Ajouter des Paires**
    ```dart
    ages.addAll({'Dave': 40});
    ```
  - **Vérifier Existence de Clé/ Valeur**
    ```dart
    bool hasAlice = ages.containsKey('Alice');
    bool has30 = ages.containsValue(30);
    ```
  - **Itération**
    ```dart
    ages.forEach((key, value) => print('$key: $value'));
    ```
  - **Transformation avec `map`**
    ```dart
    var transformedAges = ages.map((key, value) => MapEntry(key, value + 1));
    ```

### **7. Comparaison des Collections**

- **List vs Set**
  - **List** : Ordonnée, permet les doublons, accès par index.
  - **Set** : Non ordonné, unique, pas d'accès par index.

- **Set vs Map**
  - **Set** : Collection d'éléments uniques.
  - **Map** : Collection de paires clé-valeur, chaque clé unique.

- **List vs Map**
  - **List** : Accès basé sur l'index, liste ordonnée.
  - **Map** : Accès basé sur la clé, collection de paires.

### **8. Utilisation avec Flutter**

Flutter est un framework de développement d'applications mobiles utilisant Dart. Voici un aperçu rapide de la création d'une application Flutter simple :

- **Installation de Flutter**
  Assurez-vous que Flutter est installé sur votre machine.

- **Création d'un Projet**
  ```bash
  flutter create my_app
  cd my_app
  ```

- **Structure d'une Application Flutter**
  ```dart
  import 'package:flutter/material.dart';

  void main() {
    runApp(MyApp());
  }

  class MyApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return MaterialApp(
        home:

 Scaffold(
          appBar: AppBar(title: Text('Hello, Flutter')),
          body: Center(child: Text('Hello, world!')),
        ),
      );
    }
  }
  ```

### **9. Conclusion**

Dart est un langage puissant pour le développement moderne, offrant une syntaxe claire et des fonctionnalités robustes pour la manipulation des données avec des collections. La maîtrise des concepts fondamentaux et des structures de données vous permettra d'écrire un code plus efficace et de développer des applications performantes.

Pour approfondir vos connaissances, consultez les ressources officielles et la [documentation de Dart](https://dart.dev/guides/libraries/library-tour), ainsi que des tutoriels et guides pratiques pour des projets spécifiques.

---

Ce cours couvre les bases du langage Dart et les opérations essentielles sur les collections. N'hésitez pas à consulter des exemples supplémentaires et à pratiquer pour mieux comprendre chaque concept.
