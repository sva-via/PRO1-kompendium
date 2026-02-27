# Bilag B – IntelliJ quick guide

Dette bilag giver en kort introduktion til IntelliJ IDEA som udviklingsværktøj i PRO1. Fokus er på de funktioner, der understøtter design, struktur og test.

## 1. Opret nyt projekt

1) File → New → Project
2) Vælg Java
3) Vælg korrekt JDK
4) Angiv projektets navn og placering

## 2. Opret klasse

1) Højreklik på src-mappen
2) New → Java Class
3) Angiv klassenavn (fx MyDate)

```
public class MyDate {

}
```
## 3. Kør program

Højreklik på klassen med main-metoden og vælg Run.

Alternativt: Klik på den grønne pil i venstre margen.

```
public static void main(String[] args) {
    System.out.println("Test");
}
```
## 4. Refactoring

IntelliJ understøtter sikker refactoring.

- Rename: Højreklik → Refactor → Rename
- Extract Method: Markér kode → Refactor → Extract → Method

Brug disse værktøjer til at forbedre cohesion og reducere duplication.

## 5. Navigation

Vigtige genveje:
- Ctrl + B: Gå til definition
- Ctrl + Alt + L: Formatér kode
- Ctrl + Shift + F: Søg i hele projektet

## 6. Fejl og debugging

Røde markeringer indikerer kompilationsfejl.

Debugging:
1) Sæt breakpoint i venstre margen
2) Vælg Debug i stedet for Run
3) Gennemse variabler og kontrolflow

## 7. Simple tests

Opret en separat klasse til test.

Struktur:
- Opret objekt
- Udfør handling
- Brug assert

```
public void testExample() {
    MyDate d = new MyDate(2024, 1, 1);
    assert d.isBefore(new MyDate(2024, 1, 2));
}
```
IntelliJ understøtter også JUnit, men i PRO1 er fokus først på test som tænkning.

## 8. Projektstruktur

Hold projektet enkelt:
- Én klasse pr. fil
- Klasser i src-mappen
- Testklasser adskilt fra domæneklasser

Brug IDE’en som værktøj – men lad designbeslutninger styre strukturen.
