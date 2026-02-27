# Bilag D – JUnit mini-guide

Dette bilag giver en kort introduktion til JUnit. I PRO1 er fokus stadig test som tænkning, men JUnit kan bruges som struktureret værktøj.

## 1. Opret testklasse

I IntelliJ kan du højreklikke på en klasse og vælge:
Generate → Test

JUnit 5 anbefales.

```
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;
```
## 2. Simpel test

```
public class MyDateTest {

    @Test
    public void testIsBefore() {

        MyDate d1 = new MyDate(2024, 1, 1);
        MyDate d2 = new MyDate(2024, 1, 2);

        assertTrue(d1.isBefore(d2));
    }
}
```
@Test markerer en testmetode.
assertTrue kontrollerer, at betingelsen er sand.

## 3. Centrale assertions

```
assertEquals(5, value);
assertTrue(condition);
assertFalse(condition);
assertNotNull(object);
```
Assertions udtrykker forventet adfærd – ikke implementeringsdetaljer.

## 4. Test af exceptions

```
@Test
public void testInvalidMonth() {

    assertThrows(IllegalArgumentException.class, () -> {
        new MyDate(2024, 13, 1);
    });
}
```
assertThrows verificerer, at den forventede exception kastes.

## 5. Arrange – Act – Assert

En god test følger strukturen:

Arrange: Opret objekter
Act: Udfør handling
Assert: Kontroller resultat

```
@Test
public void testWithdraw() {

    // Arrange
    Account a = new Account(100);

    // Act
    a.withdraw(40);

    // Assert
    assertEquals(60, a.getBalance());
}
```
## 6. Designprincip i PRO1

JUnit er et værktøj – ikke en erstatning for design.

Hvis det er svært at skrive tests, er designet ofte uklart.

Test bør fokusere på:
- Offentlig adfærd
- Invariants
- Boundary values
- Exceptions

## 7. Typiske fejl og misforståelser

1) At teste private felter direkte.
2) At skrive tests, der afhænger af kørselsrækkefølge.
3) At ignorere edge cases.
4) At bruge JUnit uden at forstå, hvad der testes.

Brug JUnit som struktureret støtte – men tænk altid før du tester.
