# Bilag C – Scanner og console I/O

Dette bilag giver en kort introduktion til input og output via konsollen i Java. I PRO1 bruges console I/O primært til små testprogrammer – ikke som del af domænelogikken.

## 1. Output til konsol

```
System.out.println("Hello World");
System.out.print("Value: ");
System.out.println(42);
```
System.out.println skriver en linje og laver linjeskift.
System.out.print skriver uden linjeskift.

## 2. Brug af Scanner

For at læse input fra tastaturet bruges klassen Scanner.

```
import java.util.Scanner;
Scanner scanner = new Scanner(System.in);
```
Scanner oprettes typisk i main-metoden i små testprogrammer.

## 3. Læsning af input

```
System.out.print("Enter a number: ");
int number = scanner.nextInt();

System.out.print("Enter a word: ");
String word = scanner.next();
```
Typiske metoder:
- nextInt()
- nextDouble()
- next()
- nextLine()

Bemærk forskellen mellem next() (læser ét ord) og nextLine() (læser en hel linje).

## 4. Simpelt eksempelprogram

```
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter year: ");
        int year = scanner.nextInt();

        MyDate date = new MyDate(year, 1, 1);

        System.out.println("Created date: " + year);

        scanner.close();
    }
}
```
Bemærk at Scanner lukkes med scanner.close().

## 5. Designprincip i PRO1

I PRO1 skal console I/O holdes adskilt fra domæneklasser.

Forkert design:

```
public class MyDate {

    public void readFromConsole() {
        Scanner s = new Scanner(System.in);
        year = s.nextInt();
    }
}
```
Her blandes inputlogik og domænelogik. Det reducerer cohesion.

Korrekt design:
- Læs input i main eller i en separat UI-klasse
- Opret derefter domæneobjekter

## 6. Typiske fejl og misforståelser

1) At glemme import java.util.Scanner.
2) At blande nextInt() og nextLine() uden at håndtere linjeskift.
3) At placere Scanner direkte i domæneklasser.
4) At bruge console I/O som erstatning for test.

Console I/O er et hjælpemiddel – ikke en del af kernearkitekturen.
