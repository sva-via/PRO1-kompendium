# Translation Guide

Denne vejledning beskriver principperne for oversættelse af **PRO1-Compendium** til **PRO1-kompendium**.

Målet er at skabe et kompendium, der er naturligt at læse for danske studerende, samtidig med at de bevarer forbindelsen til den engelske terminologi, de møder i Java, dokumentation og litteratur.

---

## Grundprincipper

Oversættelsen følger disse overordnede principper:

- skriv naturligt dansk
- bevar den objektorienterede tankegang
- bevar Java-kode uændret
- bevar eksempler og øvelser
- oversæt fagtermer konsekvent
- undgå direkte ord-for-ord oversættelser

Der oversættes for **førsteårsstuderende i software engineering**.

---

## Objektorienteret terminologi

Brug altid de danske betegnelser, når de er almindeligt anvendt.

| Engelsk | Dansk |
|----------|--------|
| object | objekt |
| objects | objekter |
| class | klasse |
| classes | klasser |
| reference | reference |
| references | referencer |
| method | metode |
| methods | metoder |
| constructor | konstruktør |
| field | felt |
| instance variable | instansvariabel |
| parameter | parameter |
| variable | variabel |
| value | værdi |
| array | array |
| loop | løkke |
| interface | interface |
| inheritance | nedarvning |
| association | association |
| aggregation | aggregering |
| composition | komposition |

---

## Designbegreber

Nogle centrale designbegreber bevares på engelsk første gang de introduceres, men forklares på dansk.

Eksempel:

> responsibility (ansvar)

> encapsulation (indkapsling)

> invariant (invariant)

> collaboration (samarbejde)

> behavior (adfærd)

> state (tilstand)

Efter første introduktion kan den danske betegnelse anvendes, hvis teksten bliver mere naturlig.

---

## Java-termer

Java-specifikke navne oversættes aldrig.

Eksempel:

- String
- Object
- ArrayList
- Integer
- LocalDate
- IllegalArgumentException
- JUnit
- IntelliJ IDEA
- JavaFX

---

## Kode

Kode må aldrig ændres.

Bevar:

- formattering
- indrykning
- kommentarer
- navngivning
- klassenavne
- metodenavne
- variabelnavne

Eksempel:

```java
public class BankAccount {
    private double balance;
}
```

må ikke oversættes.

---

## UML

Alle UML-diagrammer bevares.

Klassenavne ændres kun hvis de også ændres i Java-koden.

---

## Overskrifter

Oversæt overskrifter til naturligt dansk.

Eksempel:

| Engelsk | Dansk |
|----------|--------|
| Chapter | Kapitel |
| Appendix | Bilag |
| Introduction | Introduktion |
| Summary | Opsummering |
| Learning goals | Læringsmål |

---

## Øvelser

Brug konsekvent:

| Engelsk | Dansk |
|----------|--------|
| Task | Del |
| Exercise | Øvelse |
| Inspection | Undersøg |

Eksempel:

```
### Task 1
```

bliver

```
### Del 1
```

---

## Navigation

Mapper oversættes.

| Engelsk | Dansk |
|----------|--------|
| chapter | kapitel |
| appendix | bilag |

Eksempel:

```
chapter/01.md
```

bliver

```
kapitel/01.md
```

---

## Filstruktur

Den danske udgave anvender:

```
docs/
    index.md
    kapitel/
    bilag/
```

---

## mkdocs.yml

Navigation oversættes.

Eksempel:

```yaml
nav:
  - Forside: index.md

  - Kapitler:
      - "Kapitel 1: Hvad er et objekt?": kapitel/01.md

  - Bilag:
      - "Bilag A: Hurtig reference": bilag/A.md
```

---

## Første forekomst af fagbegreber

Når et vigtigt designbegreb introduceres første gang, bruges:

```
engelsk (dansk)
```

Eksempel:

> responsibility (ansvar)

> encapsulation (indkapsling)

> collaboration (samarbejde)

Dette hjælper studerende med at koble den danske tekst til engelsksproget litteratur.

---

## Senere forekomster

Når begrebet først er introduceret, anvendes normalt den danske betegnelse.

Eksempel:

Første gang:

> responsibility (ansvar)

Senere:

> ansvar

---

## Sprogstil

Oversættelsen skal:

- være flydende dansk
- være let at læse
- undgå maskinoversættelser
- undgå unødigt formelt sprog

Målet er et kompendium – ikke en ordret oversættelse.

---

## Bevar engelske identifikatorer

Disse oversættes aldrig:

- Java-klassenavne
- metodenavne
- variabelnavne
- filnavne
- pakker
- imports
- API-navne

Eksempel:

```
deposit()
withdraw()
getBalance()
```

forbliver uændrede.

---

## Markdown

Markdown-strukturen bevares.

Oversæt kun teksten.

Bevar:

- overskriftsniveauer
- tabeller
- kodeblokke
- lister
- links
- billeder

---

## Terminologi

Anvend konsekvent følgende oversættelser.

| Engelsk | Dansk |
|----------|--------|
| object | objekt |
| class | klasse |
| reference | reference |
| references | referencer |
| object reference | objektreference |
| constructor | konstruktør |
| method | metode |
| field | felt |
| instance variable | instansvariabel |
| parameter | parameter |
| responsibility | ansvar |
| encapsulation | indkapsling |
| invariant | invariant |
| collaboration | samarbejde |
| state | tilstand |
| behavior | adfærd |
| mutable | mutérbar |
| immutable | uforanderlig |
| array | array |
| loop | løkke |
| association | association |
| aggregation | aggregering |
| composition | komposition |
| inheritance | nedarvning |
| interface | interface |

---

## Oversættelsesprincip

Når der findes en naturlig dansk fagterm, anvendes den.

Eksempel:

✔ objekt

ikke

✘ object

---

## Konsistens

Det vigtigste princip er konsekvens.

Den samme engelske term oversættes altid til den samme danske term gennem hele kompendiet.

Undgå synonymer.

Eksempel:

Brug altid:

- objekt

ikke skiftevis:

- objekt
- genstand
- ting

---

## Formål

Kompendiet skal hjælpe danske studerende med at:

- lære objektorienteret programmering
- forstå engelske Java-begreber
- læse engelsksproget dokumentation
- arbejde naturligt med Java-kode

Derfor kombineres naturligt dansk med konsekvent anvendelse af de engelske programmeringsbegreber, hvor det er fagligt relevant.
