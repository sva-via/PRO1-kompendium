# Bilag D – Mini-guide til JUnit

## Introduktion

Dette bilag giver en kompakt introduktion til JUnit-test i PRO1.

JUnit bruges gennem hele kurset til at:

- teste objekters behavior (adfærd)
- verificere invarianter
- teste beregninger
- teste exceptions
- understøtte objektorienteret design

Test er en vigtig del af kursets filosofi.

Kurset følger en stærk:

- test-first-tilgang
- design-first-tilgang
- object-first-tilgang

---

## 1. Hvad er JUnit?

JUnit er et testframework til Java.

JUnit gør det muligt for programmører at:

- skrive automatiserede tests
- verificere forventet behavior
- finde fejl tidligt
- dokumentere forventet behavior

JUnit-tests skrives som almindelige Java-metoder.

---

## 2. Hvorfor er test vigtigt?

Test hjælper med at verificere, at objekter opfører sig korrekt.

Eksempler på spørgsmål:

- Initialiserer konstruktøren korrekt?
- Returnerer en metode den korrekte værdi?
- Beskyttes invarianterne?
- Kastes exceptions korrekt?

Test understøtter:

- korrekthed
- læsbarhed
- vedligeholdelse
- tillid til koden under udvikling

---

## 3. Strukturen af en JUnit-test

Eksempel:

```java
@Test void getAge()
{
  Person person = new Person("Bob", 20);

  assertEquals(20, person.getAge());
}
```

En test består normalt af:

1. Klargøring (Setup)
2. Handling (Action)
3. Kontrol (Verification)

---

## 4. Import af JUnit

Typiske importer:

```java
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.*;
```

Disse importer stiller følgende til rådighed:

- `@Test`
- assertions-metoder

---

## 5. Annotationen @Test

JUnit identificerer testmetoder ved hjælp af `@Test`.

Eksempel:

```java
@Test void isAdult()
{
  // testkode
}
```

Uden `@Test` bliver metoden ikke udført som en test.

---

## 6. Navngivning af testmetoder

Testnavne bør beskrive behavior tydeligt.

Gode eksempler:

```java
@Test void incrementOnceReturns1()
```

```java
@Test void constructorRejectsNegativeAge()
```

Mindre gode eksempler:

```java
@Test void test1()
```

Læsbare testnavne gør det lettere at forstå systemets behavior.

---

## 7. assertEquals

`assertEquals` kontrollerer forventede værdier.

Eksempel:

```java
assertEquals(20, person.getAge());
```

Struktur:

```java
assertEquals(expected, actual)
```

---

## 8. Test af double-værdier

Flydende kommatal er tilnærmede værdier.

Derfor bruger test en epsilon-værdi.

Eksempel:

```java
private static final double EPSILON = 0.00001;
```

Eksempel:

```java
assertEquals(3.14, circle.getArea(), EPSILON);
```

---

## 9. assertTrue og assertFalse

Bruges til booleske metoder.

Eksempel:

```java
assertTrue(person.isAdult());
```

Eksempel:

```java
assertFalse(person.isAdult());
```

Booleske metoder er almindelige i objektorienteret design.

---

## 10. assertNull og assertNotNull

Bruges til referencer.

Eksempel:

```java
assertNull(person.getEmail());
```

Eksempel:

```java
assertNotNull(person.getEmail());
```

---

## 11. Test af exceptions

JUnit kan verificere, at exceptions bliver kastet.

Eksempel:

```java
@Test void negativeAgeThrowsException()
{
  assertThrows(IllegalArgumentException.class,
      () -> new Person("Bob", -1));
}
```

Dette er vigtigt ved test af invarianter og validering.

---

## 12. Forstå lambda-udtryk i tests

Eksempel:

```java
() -> new Person("Bob", -1)
```

Dette repræsenterer kode, som forventes at kaste en exception.

På dette tidspunkt i kurset er det tilstrækkeligt at forstå:

- JUnit udfører koden
- JUnit kontrollerer, om exceptionen opstår

Den detaljerede syntaks for lambda-udtryk introduceres senere i kurset.

---

## 13. Test af konstruktører

Konstruktører bør testes grundigt.

Eksempel:

```java
@Test void constructorInitializesName()
{
  Person person = new Person("Bob", 20);

  assertEquals("Bob", person.getName());
}
```

Konstruktører har responsibility for at etablere en gyldig state.

---

## 14. Test af setters

Setter-metoder skal bevare invarianter.

Eksempel:

```java
@Test void setAgeChangesAge()
{
  Person person = new Person("Bob", 20);

  person.setAge(25);

  assertEquals(25, person.getAge());
}
```

---

## 15. Test af ugyldig state

Ugyldigt input bør også testes.

Eksempel:

```java
@Test void setNegativeAgeThrowsException()
{
  Person person = new Person("Bob", 20);

  assertThrows(IllegalArgumentException.class,
      () -> person.setAge(-1));
}
```

Test af ugyldig behavior er lige så vigtig som test af gyldig behavior.

---

## 16. Grænseværditest

Grænseværdier er særligt vigtige.

Eksempel:

```text
age = 0
age = 1
age = 17
age = 18
```

Eksempel:

```java
@Test void age18IsAdult()
{
  Person person = new Person("Bob", 18);

  assertTrue(person.isAdult());
}
```

---

## 17. Test af arrays og samlinger

Samlinger bør også testes.

Eksempel:

```java
@Test void addGradeIncreasesSize()
{
  GradeList list = new GradeList();

  list.addGrade(12);

  assertEquals(1, list.size());
}
```

Vigtige testtilfælde omfatter:

- tomme samlinger
- tilføjelse af elementer
- fjernelse af elementer
- søgning
- grænseindekser

---

## 18. Test af objektsamarbejde

Associationer bør også testes.

Eksempel:

```java
@Test void addStudent()
{
  SchoolClass c = new SchoolClass();
  Student s = new Student("Ada");

  c.addStudent(s);

  assertEquals(1, c.numberOfStudents());
}
```

Relationer mellem objekter bliver stadig vigtigere senere i kurset.

---

## 19. Arrange – Act – Assert

En almindelig struktur for tests:

### Arrange

Opret objekter og testdata.

### Act

Kald den metode, der skal testes.

### Assert

Kontrollér resultatet.

Eksempel:

```java
@Test void birthdayIncreasesAge()
{
  // Arrange
  Person person = new Person("Bob", 20);

  // Act
  person.birthday();

  // Assert
  assertEquals(21, person.getAge());
}
```

Denne struktur forbedrer læsbarheden.

---

## 20. Gode principper for test

Gode tests bør:

- være små
- fokusere på én type behavior
- have læsbare navne
- være uafhængige
- teste observerbar behavior

Tests bør ikke afhænge af:

- konsol-output
- udførelsesrækkefølge
- skjulte interne detaljer

---

## 21. Hvad bør testes?

Vigtige områder:

### Konstruktører

- korrekt initialisering
- ugyldigt input

### Metoder

- beregninger
- ændringer af state
- boolesk behavior

### Invarianter

- gyldig state
- ugyldig state

### Samlinger

- indsættelse
- fjernelse
- søgning

### Associationer

- tilføjelse af objekter
- fjernelse af objekter
- samarbejde mellem objekter

---

## 22. Typiske begynderfejl

Almindelige fejl:

1. At glemme `@Test`.
2. At teste flere typer behavior i samme test.
3. At bruge uklare testnavne.
4. At glemme grænsetilfælde.
5. Kun at teste gyldigt input.
6. At bruge konsol-output i stedet for assertions.
7. At glemme epsilon ved `double`.
8. At skrive tests, der afhænger af andre tests.

---

## 23. JUnit og kursets filosofi

Test er ikke et valgfrit ekstra element.

I PRO1 er test en del af:

- forståelse af objekters behavior
- forståelse af responsibility
- beskyttelse af invarianter
- design af vedligeholdelige systemer

JUnit understøtter objektorienteret tankegang.

---

# 24. Anbefalet arbejdsgang

En anbefalet arbejdsgang:

1. Design klassen.
2. Skriv en lille test.
3. Implementér den minimale kode.
4. Kør testen.
5. Forbedr designet.
6. Tilføj flere tests.

Dette understøtter:

- test-first-tankegang
- inkrementel udvikling
- bedre designbeslutninger

---

# Afsluttende bemærkninger

JUnit er et uundværligt værktøj i moderne softwareudvikling.

Målet er ikke blot at få testene til at bestå.

Det egentlige mål er at:

- forstå behavior
- beskytte invarianter
- understøtte design
- udvikle pålidelig software

Gode tests hjælper programmører med at tænke klart om objekters responsibility og forventede behavior.
