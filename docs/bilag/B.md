# Bilag B – Hurtig guide til IntelliJ IDEA

## Introduktion

Dette bilag giver en praktisk introduktion til IntelliJ IDEA til brug i PRO1.

Formålet er ikke at gennemgå alle funktioner i IntelliJ, men at forklare de værktøjer og arbejdsgange, der anvendes mest i kurset.

Guiden fokuserer på:

- oprettelse af Java-projekter
- organisering af opgaver
- oprettelse af klasser
- oprettelse af JUnit-tests
- kørsel af tests
- effektiv navigation i kode

---

## 1. Hvad er IntelliJ IDEA?

IntelliJ IDEA er et integreret udviklingsmiljø (IDE).

Et IDE hjælper programmører med at:

- skrive kode
- organisere projekter
- køre programmer
- køre tests
- finde fejl
- navigere i kode

Kurset anvender primært IntelliJ IDEA Community Edition.

---

## 2. Anbefalet PRO1-struktur

I PRO1 anbefales det at organisere arbejdet ved hjælp af:

- ét IntelliJ-projekt
- ét modul pr. opgave

Dette giver en overskuelig og enkel struktur.

Eksempel:

```text
PRO1
├── Person_v1
├── Person_v2
├── Person_v3
├── Rectangle_v1
└── Temperature_v1
```

Hver opgave bliver et selvstændigt modul.

Fordele:

- opgaver holdes adskilt
- test bliver enklere
- fejl isoleres
- navigation bliver lettere

---

## 3. Strukturen af et opgavemodul

En typisk modulstruktur:

```text
Person_v1
├── src
│   └── Person.java
└── Test
    └── PersonTest.java
```

---

### src-mappen

Mappen `src` indeholder Java-klasserne.

Eksempel:

```text
Person.java
Rectangle.java
Temperature.java
```

Disse klasser indeholder:

- state (tilstand)
- behavior (adfærd)
- invarianter
- objektorienteret design

---

### Test-mappen

Mappen `Test` indeholder JUnit-testklasser.

Eksempel:

```text
PersonTest.java
RectangleTest.java
```

Testene verificerer:

- objekters behavior
- beregninger
- invarianter
- exceptions

Adskillelse af tests og kildekode forbedrer læsbarhed og struktur.

---

## 4. Oprettelse af et nyt IntelliJ-projekt

### Trin 1

Åbn IntelliJ IDEA.

Vælg:

```text
New Project
```

---

### Trin 2

Vælg:

```text
Java
```

---

### Trin 3

Vælg den korrekte JDK.

Eksempel:

```text
JDK 25
```

Hvis ingen JDK er installeret, kan IntelliJ normalt hente en automatisk.

---

### Trin 4

Vælg et projektnavn.

Eksempel:

```text
PRO1
```

---

### Trin 5

Tryk på:

```text
Create
```

---

## 5. Oprettelse af et modul til en opgave

Hver opgave bør normalt oprettes som sit eget modul.

---

### Trin 1

Højreklik på projektnavnet.

---

### Trin 2

Vælg:

```text
New → Module
```

---

### Trin 3

Vælg:

```text
Java
```

---

### Trin 4

Vælg et modulnavn.

Eksempel:

```text
Person_v1
```

---

### Trin 5

Tryk på:

```text
Create
```

---

## 6. Oprettelse af Test-mappen

### Trin 1

Højreklik på modulnavnet.

---

### Trin 2

Vælg:

```text
New → Directory
```

---

### Trin 3

Opret:

```text
Test
```

---

### Trin 4

Højreklik på mappen `Test`.

Vælg:

```text
Mark Directory As → Test Sources Root
```

---

## 7. Oprettelse af en klasse

### Trin 1

Højreklik på:

```text
src
```

---

### Trin 2

Vælg:

```text
New → Java Class
```

---

### Trin 3

Indtast klassens navn.

Eksempel:

```text
Person
```

---

### Trin 4

Tryk:

```text
Enter
```

IntelliJ opretter automatisk klassen.

---

## 8. Oprettelse af en testklasse

Den nemmeste måde at oprette en JUnit-testklasse i IntelliJ er direkte fra den klasse, der skal testes.

---

### Trin 1

Åbn klassen.

Eksempel:

```text
Person.java
```

---

### Trin 2

Placér markøren på klassenavnet.

Eksempel:

```java
public class Person
```

---

### Trin 3

Tryk:

```text
Alt + Enter
```

---

### Trin 4

Vælg:

```text
Create Test
```

---

### Trin 5

Vælg:

```text
JUnit 5
```

Hvis JUnit endnu ikke er konfigureret, viser IntelliJ normalt en advarsel eller et forslag.

Klik på:

```text
Fix
```

IntelliJ vil derefter:

- hente JUnit om nødvendigt
- konfigurere modulet
- automatisk tilføje de nødvendige biblioteker

---

### Trin 6

Tryk på:

```text
OK
```

IntelliJ:

- opretter automatisk `PersonTest`
- placerer den i mappen `Test`
- tilføjer JUnit-importer
- opretter skeletter til testmetoder

---

## 9. Kørsel af tests

JUnit-tests kan køres direkte i IntelliJ.

---

## Kør en enkelt test

Klik på den grønne trekant ud for testmetoden.

---

## Kør en hel testklasse

Klik på den grønne trekant ud for klassenavnet.

---

## Testresultater

### Grøn

```text
Tests passed
```

### Rød

```text
Tests failed
```

IntelliJ viser:

- hvilke tests der fejlede
- forventede værdier
- faktiske værdier
- stack traces

---

## 10. Nyttige tastaturgenveje

### Søg overalt

```text
Double Shift
```

---

### Generér kode

```text
Alt + Insert
```

Nyttig til at generere:

- konstruktører
- getters
- setters
- `toString()`
- `equals()`

---

### Hurtig rettelse

```text
Alt + Enter
```

---

### Formater kode

```text
Ctrl + Alt + L
```

---

### Omdøb

```text
Shift + F6
```

---

### Gå til deklaration

```text
Ctrl + Click
```

---

## 11. Typiske begynderfejl

Almindelige fejl:

1. At oprette klasser i det forkerte modul.
2. At glemme at markere `Test` som Test Sources Root.
3. At blande tests og kildekode.
4. At glemme importer.
5. At ignorere IntelliJ-advarsler.
6. At skrive al kode i én klasse.
7. At bruge genereret kode uden at forstå den.

---

## 12. Anbefalet arbejdsgang

En anbefalet arbejdsgang i PRO1:

1. Opret modulet.
2. Opret mappen `Test`.
3. Opret klassen i mappen `src`.
4. Opret testklassen.
5. Skriv en lille test.
6. Implementér den enkleste kode.
7. Kør testen.
8. Forbedr designet.
9. Gentag.

Dette understøtter:

- test-first-tilgangen
- design-first-tilgangen
- object-first-tilgangen

som anvendes gennem hele kurset.

---

## Afsluttende bemærkninger

Det kræver øvelse at lære IntelliJ.

Studerende opfordres til at:

- udforske IDE'et
- bruge tastaturgenveje
- læse fejlmeddelelser omhyggeligt
- køre tests ofte
- organisere opgaver tydeligt
- tænke i objekter og responsibility

Effektiv brug af IntelliJ hjælper studerende med at fokusere mere på:

- design
- test
- responsibility
- objektorienteret tankegang

frem for syntaksdetaljer.
