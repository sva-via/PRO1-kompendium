# Bilag A – Java-syntaks quick reference

Dette bilag er en kort syntaksoversigt. Det erstatter ikke forståelse af design, men fungerer som opslagsværk.

## 1. Klasse

```
public class MyClass {

    private int value;

    public MyClass(int value) {
        this.value = value;
    }

    public int getValue() {
        return value;
    }
}
```
## 2. Primitive typer

```
int x = 5;
double y = 3.14;
boolean b = true;
char c = 'A';
```
## 3. if / else

```
if (x > 0) {
    System.out.println("Positive");
} else {
    System.out.println("Not positive");
}
```
## 4. Loops

```
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}

while (x > 0) {
    x--;
}
```
## 5. Metoder

```
public int add(int a, int b) {
    return a + b;
}
```
## 6. Exceptions

```
if (value < 0) {
    throw new IllegalArgumentException("Must be positive");
}

try {
    method();
} catch (IllegalArgumentException e) {
    System.out.println("Error");
}
```
## 7. Arrays

```
int[] numbers = new int[5];
numbers[0] = 10;

for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```
## 8. Relation mellem klasser

```
public class Person {

    private Name name;

    public Person(Name name) {
        this.name = name;
    }
}
```
## 9. Synlighed

```
public    // synlig overalt
private   // kun i klassen
protected // i pakken og subklasser
```
## 10. main-metode

```
public static void main(String[] args) {
    System.out.println("Hello World");
}
```
Brug dette bilag som reference. Fokus i PRO1 er stadig design, ansvar og invariants – ikke syntaks alene.
