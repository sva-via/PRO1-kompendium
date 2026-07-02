# PRO1 Kompendium

## Hurtig start

- **Start her:** [Kapitel 1 – Hvad er et objekt?](kapitel/01.md)
- **Bilag:** [Bilag A – Hurtig reference til Java-syntaks](kapitel/01.md)

## Introduktion

Velkommen til PRO1-kompendiet.

Dette kompendium understøtter kurset:

**Programmering 1 – Software Engineering**

Formålet med kurset er ikke kun at lære Java-syntaks, men også at lære at:

- tænke objektorienteret
- modellere problemdomæner
- designe klasser og objekter
- placere responsibility (ansvar) korrekt
- skrive læsbar og vedligeholdelig software
- teste objekters behavior (adfærd) systematisk

Kurset anvender Java som programmeringssprog, men det primære fokus er objektorienteret design.

---

## Anbefalet referencebog

Dette kompendium er kursets primære undervisningsmateriale.

Studerende kan også anvende følgende bog som supplerende reference:

**Tony Gaddis**  
*Starting Out with Java: Early Objects, Global Edition (5th Edition)*

Bogen er tænkt som et opslagsværk og en reference – ikke som den primære lærebog.

Den kan være nyttig til:

- alternative forklaringer af Java-begreber
- yderligere eksempler
- uddybning af Java-syntaks
- flere øvelsesopgaver

Kurset følger sin egen progression og lægger vægt på objektorienteret design, responsibility (ansvar), test og domænemodellering. Derfor kan emnerne i bogen optræde i en anden rækkefølge end i kurset.

Studerende bør primært følge kursusmaterialet og bruge bogen, når der er behov for yderligere forklaringer eller eksempler.

---

## PRO1's kursusfilosofi

Kurset følger en:

- object-first-tilgang
- design-first-tilgang
- test-first-tilgang

Det betyder, at kurset først og fremmest fokuserer på:

- objekter
- responsibility (ansvar)
- encapsulation (indkapsling)
- samarbejde
- domænemodellering

frem for:

- konsolmenuer
- procedureorienteret programmering
- store algoritmer
- avanceret syntaks

Målet er at forstå, hvordan softwaresystemer opbygges af samarbejdende objekter.

---

## Læringsmål

Kurset har til formål at give de studerende kompetencer til at:

- analysere enkle problemdomæner
- designe klasser og objekter
- implementere Java-klasser ud fra UML-diagrammer
- modellere domæner ved hjælp af UML
- arbejde med encapsulation (indkapsling) og invarianter
- oprette associationer mellem objekter
- arbejde med arrays og samlinger
- teste objekters behavior (adfærd) med JUnit
- håndtere exceptions korrekt
- designe vedligeholdelige objektorienterede systemer
- anvende nedarvning
- anvende polymorfi
- udvikle GUI-applikationer i JavaFX
- arbejde med filpersistens

---

## Kursets fokus

Kurset har et stærkt fokus på responsibility (ansvar) og design.

Studerende bør løbende spørge sig selv:

- Hvilket objekt bør have responsibility?
- Hvilken klasse bør indeholde logikken?
- Hvilke data hører til hvilket objekt?
- Hvordan bør objekter samarbejde?
- Hvordan kan invarianter beskyttes?

Godt objektorienteret design handler i høj grad om at placere responsibility korrekt.

---

# Sådan bruger du kompendiet

Hvert kapitel svarer til én undervisningsgang.

Hvert kapitel fokuserer på:

- de vigtigste begreber, der introduceres i undervisningsgangen
- designidéerne bag eksemplerne
- almindelige begynderfejl
- vigtige objektorienterede principper

Kompendiet er tænkt som støtte til:

- undervisningen
- opgaver og afleveringer
- repetition af begreber
- forberedelse til tests og eksamen

---

## Anbefalet måde at studere på

Kurset er opbygget trinvist.

Nye begreber bygger videre på tidligere undervisning.

En anbefalet studieproces er:

1. Læs kapitlet før undervisningen.
2. Deltag aktivt i undervisning og diskussioner.
3. Studér eksemplerne grundigt.
4. Implementér små eksempler selv.
5. Skriv og kør JUnit-tests.
6. Reflektér over objekters responsibility og design.
7. Genlæs kapitlet efter undervisningen.

Det er vigtigere at forstå idéerne bag koden end at kunne huske syntaks udenad.

---

## Vigtige designprincipper

Gennem hele kurset går en række centrale principper igen.

### Encapsulation (indkapsling)

Objekter bør beskytte deres egen state (tilstand).

Interne data bør som udgangspunkt være private.

---

### Responsibility (ansvar)

Logik bør placeres i det objekt, der har responsibility.

Godt design:

```java
person.isAdult()
```

Mindre godt:

```java
person.getAge() >= 18
```

---

### Invarianter

Objekter bør altid være i en gyldig state.

Konstruktører etablerer en gyldig state.

Metoder bevarer en gyldig state.

---

### Samarbejde

Objekter løser problemer ved at samarbejde med andre objekter.

Associationer og samlinger bliver stadig vigtigere senere i kurset.

---

### Læsbarhed

Læsbar kode er vigtig.

Kode bør:

- kommunikere sin hensigt tydeligt
- bruge sigende metodenavne
- undgå duplikering
- udtrykke responsibility klart

---

## Test

Test introduceres tidligt i kurset.

JUnit-tests bruges til at:

- verificere behavior
- kontrollere objektets state
- teste grænsetilfælde
- teste exceptions

Kurset lægger vægt på:

- test af objekters behavior
- test af invarianter
- test af både gyldige og ugyldige tilfælde

Test betragtes som en naturlig del af softwareudvikling.

---

## UML og design

UML-diagrammer anvendes gennem hele kurset.

Studerende skal lære at:

- læse UML-klassediagrammer
- forstå relationer mellem klasser
- omsætte UML til Java-kode
- modellere enkle domæner ved hjælp af UML

Fokus er ikke avanceret UML-notation, men forståelsen af sammenhængen mellem design og implementering.

---

## Kursets progression

Kurset introducerer gradvist mere avancerede objektorienterede begreber.

### De første undervisningsgange

Fokus på:

- klasser
- objekter
- metoder
- konstruktører
- state og behavior
- test

### De mellemste undervisningsgange

Fokus på:

- invarianter
- encapsulation
- responsibility
- arrays
- løkker
- samlinger
- samarbejde mellem objekter

### De sidste undervisningsgange

Fokus på:

- nedarvning
- polymorfi
- filpersistens
- GUI-applikationer i JavaFX

Hvert emne bygger videre på tidligere forståelse.

---

## Almindelige begynderudfordringer

Mange studerende har i starten svært ved:

- at forstå referencer
- at skelne mellem objekter og variabler
- at placere responsibility korrekt
- at forstå encapsulation
- at designe meningsfulde klasser
- at forstå samlinger og objektrelationer

Det er helt normalt.

Objektorienteret tankegang udvikles gradvist gennem øvelse.

---

## Om eksemplerne

Eksemplerne i dette kompendium er bevidst små.

Formålet er at:

- fokusere tydeligt på begreberne
- undgå unødig kompleksitet
- fremhæve designidéer
- understøtte trinvis læring

Eksemplerne er valgt for at illustrere:

- objekters responsibility
- invarianter
- samarbejde
- læsbarhed
- test

---

## Forberedelse til eksamen

Den mundtlige eksamen fokuserer på:

- forståelse af UML-diagrammer
- design af klasser
- implementering af objektorienterede løsninger
- forklaring af designbeslutninger
- skrivning af korrekt Java-kode

Succes i kurset kræver:

- aktiv træning
- regelmæssig programmering
- dyb forståelse af begreberne
- at tænke i objekter og responsibility

---

## Afsluttende bemærkninger

Objektorienteret programmering handler ikke kun om at skrive kode.

Det handler om:

- at modellere domæner
- at designe samarbejdende objekter
- at beskytte objekters gyldige state
- at placere responsibility tydeligt
- at udvikle forståelige softwaresystemer

Målet med kurset er at hjælpe studerende med at udvikle både:

- praktiske programmeringsfærdigheder
- objektorienteret designtænkning

Kompendiet bør bruges som en guide gennem hele kurset og som støtte ved arbejde med opgaver, afleveringer og eksamensforberedelse.
