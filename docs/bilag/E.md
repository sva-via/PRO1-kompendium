# Bilag E – Spec2JUnit: AI som sparringspartner til test

## 1. Formål

Dette bilag viser, hvordan AI (f.eks. ChatGPT) kan bruges som **støtteværktøj** til at generere JUnit-tests ud fra en specifikation.

Vigtigt:

> AI erstatter ikke din forståelse, den understøtter den.

---

## 2. Hvad er Spec2JUnit?

Spec2JUnit betyder:

- Vi giver en specifikation og får forslag til JUnit-tests.

Eksempel:

**Specifikation:**

- `Name` har fornavn og efternavn
- Ingen af dem må være `null` eller tomme
- `getFullName()` returnerer `"fornavn efternavn"`

**AI kan generere:**

- tests af normale tilfælde
- tests af grænsetilfælde
- tests af exceptions

---

## 3. Arbejdsproces (meget vigtig)

Brug altid denne rækkefølge:

1. Læs specifikationen.
2. Find reglerne.
3. Udarbejd testidéer.
4. Brug AI.
5. Vurdér og ret output.

- AI er trin 4 – ikke trin 1.

---

## 4. Eksempel

### Dine testidéer

- `("Ada", "Lovelace")` → `"Ada Lovelace"`
- `("A", "L")` → `"A L"`
- `("", "Lovelace")` → exception
- `(null, "Lovelace")` → exception

### Prompt

```text
Generér JUnit-tests for en Name-klasse.

Krav:
- Test normale tilfælde
- Test grænsetilfælde
- Test ugyldige input (exception)
```

---

## 5. Vurdering af AI-output

Når du får tests fra AI, skal du kontrollere:

- Dækker testene alle regler?
- Mangler der grænsetilfælde?
- Er exceptions testet?
- Er testene lette at forstå?

AI tester ofte kun "happy path".

---

## 6. Typiske fejl fra AI

AI glemmer ofte:

- ugyldige input
- grænsetilfælde
- flere variationer
- præcise assertions

---

## 7. God praksis

- Udarbejd altid dine egne testidéer først.
- Brug AI til at spare tid.
- Ret og forbedr output.
- Tænk kritisk.

---

## 8. Dårlig praksis

- Kopiér AI-output uden at forstå det.
- Spring arbejdet med testidéer over.
- Stol blindt på resultatet.

---

## 9. Designprincip

> Du er ansvarlig for testen – ikke AI.

AI er et værktøj, ikke en løsning.

---

## 10. Øvelse

1. Udarbejd testidéer for en klasse.
2. Brug AI til at generere tests.
3. Sammenlign resultatet.
4. Ret AI-output.

---

## Afslutning

Spec2JUnit gør det muligt at:

- arbejde hurtigere
- få inspiration
- strukturere tests

Men kun hvis du:

- forstår problemet først
- og vurderer output bagefter
