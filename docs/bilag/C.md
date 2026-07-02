# Bilag C – Scanner og konsol-I/O

## Introduktion

Dette bilag introducerer grundlæggende konsol-input og -output i Java.

Bilaget forklarer:

- konsol-output
- konsol-input ved hjælp af `Scanner`
- indlæsning af primitive værdier og Strings
- almindelige problemer ved input

---

## Vigtig bemærkning om PRO1

PRO1-kurset er primært:

- objektorienteret
- designorienteret
- testorienteret

Kurset fokuserer **ikke** i høj grad på konsolprogrammer.

De fleste eksempler i kurset undgår derfor:

- `main`
- konsolmenuer
- store konsolapplikationer
- omfattende brug af `System.out.println`

Det er dog stadig nyttigt at forstå simpel konsol-I/O til:

- små eksperimenter
- fejlfinding
- enkle demonstrationer
- forståelse af grundlæggende programinteraktion

---

## 1. Konsol-output

Java kan skrive tekst til konsollen.

Eksempel:

```java
System.out.println("Hello world");
```

`println` betyder:

```text
print line
```

Der tilføjes automatisk et linjeskift.

---

### Udskrivning af variabler

Eksempel:

```java
int age = 20;

System.out.println(age);
```

Eksempel:

```java
String name = "Ada";

System.out.println(name);
```

---

### Sammenkædning af output

Strings kan sammenkædes med `+`.

Eksempel:

```java
String name = "Bob";
int age = 20;

System.out.println(name + " is " + age + " years old");
```

---

## 2. main-metoden

Konsolprogrammer begynder normalt med en `main`-metode.

Eksempel:

```java
public class Main
{
  public static void main(String[] args)
  {
    System.out.println("Hello world");
  }
}
```

`main`-metoden er programmets startpunkt.

---

### Vigtig bemærkning om kurset

PRO1-kurset undgår generelt at bruge `main` i opgaver.

Kurset fokuserer i stedet på:

- objekter
- klasser
- metoder
- test

Du bør derfor betragte konsol-eksempler som supplerende materiale.

---

## 3. Scanner

`Scanner` læser input fra konsollen.

Klassen skal først importeres.

Eksempel:

```java
import java.util.Scanner;
```

---

## 4. Oprettelse af en Scanner

Eksempel:

```java
Scanner input = new Scanner(System.in);
```

Forklaring:

| Del | Betydning |
|---|---|
| `Scanner` | klassetype |
| `input` | variabelnavn |
| `new Scanner(...)` | opretter et Scanner-objekt |
| `System.in` | konsollens inputstrøm |

---

## 5. Indlæsning af Strings

Eksempel:

```java
Scanner input = new Scanner(System.in);

System.out.print("Name: ");
String name = input.nextLine();
```

`nextLine()` læser en hel tekstlinje.

---

## 6. Indlæsning af int-værdier

Eksempel:

```java
Scanner input = new Scanner(System.in);

System.out.print("Age: ");
int age = input.nextInt();
```

`nextInt()` læser et heltal.

---

## 7. Indlæsning af double-værdier

Eksempel:

```java
Scanner input = new Scanner(System.in);

System.out.print("Temperature: ");
double temp = input.nextDouble();
```

`nextDouble()` læser decimaltal.

---

## 8. Indlæsning af boolean-værdier

Eksempel:

```java
Scanner input = new Scanner(System.in);

System.out.print("Adult? ");
boolean adult = input.nextBoolean();
```

Gyldige værdier er normalt:

```text
true
false
```

---

## 9. Almindeligt Scanner-problem

Et almindeligt begynderproblem opstår, når man blander:

- `nextInt()`
- `nextDouble()`
- `nextLine()`

Eksempel:

```java
int age = input.nextInt();
String name = input.nextLine();
```

Linjeskiftet efter heltallet bliver liggende i inputbufferen.

Resultatet er, at:

```java
name
```

kan blive en tom String.

---

## 10. Løsning på nextLine-problemet

En almindelig løsning:

```java
int age = input.nextInt();
input.nextLine();

String name = input.nextLine();
```

Den ekstra `nextLine()` læser det resterende linjeskift.

---

## 11. Eksempel på et konsolprogram

Eksempel:

```java
import java.util.Scanner;

public class Main
{
  public static void main(String[] args)
  {
    Scanner input = new Scanner(System.in);

    System.out.print("Name: ");
    String name = input.nextLine();

    System.out.print("Age: ");
    int age = input.nextInt();

    System.out.println(name + " is " + age + " years old");
  }
}
```

---

## 12. Scanner og exceptions

Ugyldigt input kan medføre exceptions.

Eksempel:

```text
InputMismatchException
```

Eksempel:

```java
int age = input.nextInt();
```

Hvis brugeren indtaster:

```text
hello
```

opstår der en exception.

---

## 13. Simpelt try-catch-eksempel

Eksempel:

```java
try
{
  int age = input.nextInt();
}
catch (InputMismatchException e)
{
  System.out.println("Illegal number");
}
```

Dette emne bliver vigtigere senere i kurset.

---

## 14. Lukning af Scanner

En `Scanner` kan lukkes.

Eksempel:

```java
input.close();
```

I enkle begynderprogrammer lægges der ofte ikke stor vægt på dette.

---

## 15. Konsolprogrammer kontra objektorienteret design

Konsol-I/O bør normalt holdes adskilt fra domænelogik.

Mindre god løsning:

```java
public class Person
{
  public void readAgeFromConsole()
  {
    // scanner logic
  }
}
```

Bedre løsning:

- hold konsolkode adskilt
- lad domæneklasser fokusere på deres responsibility

Domæneklasser bør primært repræsentere:

- state (tilstand)
- behavior (adfærd)
- invarianter

og ikke logik til brugergrænsefladen.

---

## 16. Konsol-I/O og test

Konsolprogrammer er vanskelige at teste automatisk.

Det er en af grundene til, at kurset lægger vægt på:

- objektmetoder
- returværdier
- JUnit-test

frem for interaktive konsolprogrammer.

Eksempel:

God løsning:

```java
person.isAdult()
```

Mindre god løsning:

```java
System.out.println("Adult")
```

Den første løsning er lettere at teste.

---

## 17. Anbefalet anvendelse i PRO1

Brug primært konsol-I/O til:

- eksperimenter
- fejlfinding
- små demonstrationer

Kursets primære fokus er fortsat:

- objektorienteret tankegang
- klassedesign
- test
- encapsulation
- responsibility

---

## 18. Typiske begynderfejl

Almindelige fejl:

1. At glemme at importere `Scanner`.
2. At glemme `new Scanner(System.in)`.
3. At blande `nextInt()` og `nextLine()` forkert.
4. At glemme semikoloner.
5. At skrive al logik inde i `main`.
6. At placere domænelogik i konsolkode.
7. At bruge konsol-output i stedet for returværdier.

---

## 19. Refleksionsspørgsmål

- Hvad er formålet med `Scanner`?
- Hvorfor returnerer `nextLine()` nogle gange en tom String?
- Hvorfor er konsolprogrammer vanskeligere at teste?
- Hvorfor undgår PRO1 normalt brug af `main`?
- Hvorfor bør konsolkode holdes adskilt fra domænelogik?
- Hvornår er det passende at bruge konsol-I/O?

---

## Opsummering

Dette bilag introducerer grundlæggende konsol-I/O i Java.

Vigtige idéer omfatter:

- `Scanner` læser input fra konsollen
- `System.out.println()` skriver output til konsollen
- `nextLine()` kan give problemer efter `nextInt()`
- `try-catch` kan håndtere ugyldigt input
- konsolkode bør holdes adskilt fra domænelogik
- PRO1 fokuserer primært på objekter, design og test frem for konsolprogrammer

Konsol-I/O er nyttigt til små eksperimenter og demonstrationer, men er ikke den centrale måde at udvikle applikationer på i PRO1.
