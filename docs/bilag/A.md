# Bilag A – Hurtig reference til Java-syntaks

## Introduktion

Dette bilag giver et kompakt overblik over den Java-syntaks, der anvendes gennem hele PRO1.

Formålet er ikke at erstatte forklaringerne i kapitlerne, men at fungere som en hurtig reference under arbejdet med:

- opgaver
- afleveringer
- tests
- eksempler

Bilaget fokuserer kun på den syntaks, der introduceres i kurset.

---

## 1. Klassestruktur

```java
public class Person
{
  private String name;

  public Person(String name)
  {
    this.name = name;
  }

  public String getName()
  {
    return name;
  }
}
```

Hoveddele:

- klassedeklaration
- felter
- konstruktør
- metoder

---

## 2. Variabler

### Primitive variabler

```java
int age = 20;
double temperature = 21.5;
boolean valid = true;
char grade = 'A';
```

---

### Referencevariabler

```java
String name = "Bob";
Person person = new Person("Ada");
```

Referencevariabler gemmer referencer til objekter.

---

## 3. Primitive datatyper

| Type | Eksempel |
|---|---|
| `int` | `int x = 5;` |
| `double` | `double y = 3.14;` |
| `boolean` | `boolean ok = true;` |
| `char` | `char c = 'A';` |

---

## 4. Strings

```java
String name = "Ada";
```

Nyttige metoder:

```java
name.length()
name.toUpperCase()
name.toLowerCase()
name.trim()
name.contains("Ada")
name.substring(0, 2)
```

---

## 5. Oprettelse af objekter

```java
Person person = new Person("Bob");
```

Generel form:

```java
ClassName variable = new ClassName(arguments);
```

---

## 6. Felter (instansvariabler)

```java
private String name;
private int age;
```

Felter gemmer et objekts state (tilstand).

---

## 7. Konstruktører

```java
public Person(String name)
{
  this.name = name;
}
```

Konstruktører:

- har samme navn som klassen
- har ingen returtype
- initialiserer objekter

---

## 8. Metoder

### Metode, der returnerer en værdi

```java
public int getAge()
{
  return age;
}
```

---

### Void-metode

```java
public void birthday()
{
  age++;
}
```

---

### Boolesk metode

```java
public boolean isAdult()
{
  return age >= 18;
}
```

---

## 9. this

`this` refererer til det aktuelle objekt.

Eksempel:

```java
this.name = name;
```

Bruges til at skelne mellem felter og parametre.

---

## 10. Konstruktørdelegering

```java
public Person(String name)
{
  this(name, 18);
}
```

En konstruktør kan kalde en anden konstruktør ved hjælp af `this(...)`.

---

## 11. if-sætninger

```java
if (age >= 18)
{
  return true;
}
```

---

### if-else

```java
if (age >= 18)
{
  return "Adult";
}
else
{
  return "Child";
}
```

---

### else-if

```java
if (age < 13)
{
  return "Child";
}
else if (age < 20)
{
  return "Teenager";
}
else
{
  return "Adult";
}
```

---

## 12. switch

```java
switch(day)
{
  case 1:
    return "Monday";

  case 2:
    return "Tuesday";

  default:
    return "Unknown";
}
```

---

## 13. Relationelle operatorer

| Operator | Betydning |
|---|---|
| `==` | lig med |
| `!=` | ikke lig med |
| `>` | større end |
| `<` | mindre end |
| `>=` | større end eller lig med |
| `<=` | mindre end eller lig med |

---

## 14. Logiske operatorer

| Operator | Betydning |
|---|---|
| `&&` | OG |
| `||` | ELLER |
| `!` | IKKE |

Eksempel:

```java
if (age >= 18 && age < 65)
{
  // ...
}
```

---

## 15. Sammenligning af Strings

Korrekt:

```java
name.equals("Bob")
```

Undgå:

```java
name == "Bob"
```

`equals()` sammenligner indhold.

`==` sammenligner referencer.

---

## 16. null

```java
Person person = null;
```

Kontrol af `null`:

```java
if (person != null)
{
  // ...
}
```

---

## 17. Arrays

### Oprettelse af arrays

```java
int[] numbers = new int[10];
```

---

### Adgang til elementer

```java
numbers[0]
numbers[1]
```

---

### Arrayets længde

```java
numbers.length
```

---

## 18. for-løkker

```java
for (int i = 0; i < size; i++)
{
  // ...
}
```

Bruges ofte til arrays.

---

## 19. Enhanced for-løkker

```java
for (int number : numbers)
{
  // ...
}
```

Bruges, når indekset ikke er nødvendigt.

---

## 20. while-løkker

```java
while (x > 0)
{
  x--;
}
```

---

## 21. do-while-løkker

```java
do
{
  x--;
}
while (x > 0);
```

Udføres mindst én gang.

---

## 22. ArrayList

### Import

```java
import java.util.ArrayList;
```

---

### Oprettelse af en ArrayList

```java
ArrayList<String> names;
names = new ArrayList<String>();
```

---

### Tilføjelse af elementer

```java
names.add("Ada");
```

---

### Adgang til elementer

```java
names.get(0)
```

---

### Udskiftning af elementer

```java
names.set(0, "Bob")
```

---

### Fjernelse af elementer

```java
names.remove(0)
```

---

### Samlingens størrelse

```java
names.size()
```

---

## 23. Exceptions

### Kaste exceptions

```java
throw new IllegalArgumentException(
    "Illegal age");
```

---

### try-catch

```java
try
{
  // risikofyldt kode
}
catch (Exception e)
{
  // håndter exception
}
```

---

## 24. Grundlæggende JUnit

### Simpel test

```java
@Test void getAge()
{
  Person person = new Person("Bob", 20);

  assertEquals(20, person.getAge());
}
```

---

### Test af exceptions

```java
@Test void illegalAge()
{
  assertThrows(IllegalArgumentException.class,
      () -> new Person("Bob", -1));
}
```

---

## 25. toString()

```java
public String toString()
{
  return name + ", age=" + age;
}
```

Leverer en tekstlig repræsentation af objektet.

---

## 26. equals()

```java
public boolean equals(Object obj)
{
  // sammenlign objektets indhold
}
```

Bruges til at sammenligne et objekts betydning eller indhold.

---

## 27. LocalDate

### Import

```java
import java.time.LocalDate;
```

---

### Oprettelse af datoer

```java
LocalDate birthday = LocalDate.of(2000, 10, 25);
```

---

### Nyttige metoder

```java
LocalDate.now()
birthday.isAfter(LocalDate.now())
```

---

## 28. UML-synlighedssymboler

| Symbol | Betydning |
|---|---|
| `+` | public |
| `-` | private |

Eksempel:

```text
+ getName() : String
- age : int
```

---

## 29. Almindelige Java-nøgleord

| Nøgleord | Formål |
|---|---|
| `class` | definerer en klasse |
| `public` | tilgængelig overalt |
| `private` | kun tilgængelig inde i klassen |
| `new` | opretter et objekt |
| `return` | returnerer en værdi |
| `void` | ingen returværdi |
| `this` | aktuelt objekt |
| `if` | selektion |
| `else` | alternativ gren |
| `for` | gentagelse |
| `while` | gentagelse |
| `switch` | flere alternativer |
| `null` | ingen objektreference |

---

## 30. Typiske begynderfejl

Almindelige fejl omfatter:

- at glemme `new`
- at forveksle objekter og referencer
- at bruge `==` til Strings
- at glemme krøllede parenteser `{}`
- at glemme semikolon `;`
- at bruge `length()` i stedet for `length`
- at forveksle `size()` og `length`
- at tilgå ugyldige indekser
- at glemme at initialisere samlinger

---

## Afsluttende bemærkninger

Dette bilag er tænkt som en hurtig syntaksreference under kurset.

Det vigtigste mål er fortsat:

- at forstå objektorienteret tankegang
- at placere responsibility korrekt
- at designe meningsfulde klasser
- at beskytte invarianter
- at skrive læsbar kode

Syntaks er vigtig, men design og responsibility er fortsat det primære fokus i PRO1.
