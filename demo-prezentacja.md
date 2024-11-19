---
marp: true
theme: default
paginate: true
title: Tworzenie Programów CLLE na IBM i
---

# Tworzenie Programów CLLE na IBM i

### Informacje wstępne
  
<br />
📁 Materiały, dokumenty i kody źródłowe dostępne są w publicznym repozytorium:

🔗 [https://github.com/ako74programmer](https://github.com/ako74programmer)

---

## Krok 1: Tworzenie Biblioteki STUDENTx

### Wprowadzenie

Każdy student utworzy swoją bibliotekę o nazwie:

**`STUDENTx`**

- Gdzie `x` to numer przypisany do logowania do środowiska IBM i.

---

### Tworzenie biblioteki

Na IBM i zaloguj się i wprowadź następującą komendę w terminalu:

```plaintext
CRTLIB LIB(STUDENTx) TEXT('Biblioteka studenta x')
```
<br />
🎯 Wynik: Utworzona zostanie nowa biblioteka `STUDENTx`.

---

## Krok 2: Przygotowanie środowiska dla kodów źródłowych

### Tworzenie plików źródłowych

Utwórz pliki źródłowe dla różnych typów programów:

```plaintext
CRTSRCPF FILE(STUDENTx/QCLSRC) RCDLEN(112) TEXT('SOURCE CL')
CRTSRCPF FILE(STUDENTx/QCMDSRC) RCDLEN(112) TEXT('SOURCE CMD')
CRTSRCPF FILE(STUDENTx/QDDSSRC) RCDLEN(112) TEXT('SOURCE DDS')
CRTSRCPF FILE(STUDENTx/QRPGLESRC) RCDLEN(112) TEXT('SOURCE RPGLE')
CRTSRCPF FILE(STUDENTx/QRPGSRC) RCDLEN(112) TEXT('SOURCE RPG')
```
<br />
🎯 Wynik: W bibliotece `STUDENTx` pojawią się katalogi na źródła.

---

## Krok 3: Utworzenie programów CLLE w STRPDM

### Wejdź do środowiska STRPDM

1. Wprowadź komendę:
   ```plaintext
   STRPDM
   ```

2. Wybierz opcję: **3. Work with Members**.

---

### Dodaj nowy member w pliku źródłowym QCLSRC

1. Wybierz bibliotekę `STUDENTx` i plik `QCLSRC`.
2. Utwórz nowy member **F6=Create**:
   - Nazwa membra (Source member): `PROGRAM1`
   - Typ membra (Source type): `CLLE`.    

<br />
🎯 Wynik: Otworzysz edytor dla nowego membra.

---

## Krok 4: Edycja programu CLLE

### Przykład prostego programu CLLE:

W edytorze wprowadź następujący kod:

```plaintext
PGM
   DCL VAR(&MESSAGE) TYPE(*CHAR) LEN(50)
   CHGVAR VAR(&MESSAGE) VALUE('Witaj, IBM i!')
   SNDPGMMSG MSG(&MESSAGE)
ENDPGM
```
<br />
🎯 Wynik: Program, który wyświetla wiadomość na ekranie.

---

## Krok 5: Kompilacja programu

### Kompilacja członu CLLE

1. W STRPDM zaznacz człon `PROGRAM1`.
2. Naciśnij **14=Compile** (kompilacja).


<br />
🎯 Wynik: Program zostanie skompilowany.

---

## Krok 6: Uruchomienie programu

1. Wprowadź w terminalu:

   ```plaintext
   CALL STUDENTx/PROGRAM1
   ```
<br />
🎯 Wynik: Na ekranie pojawi się komunikat `Witaj, IBM i!`.

---

## Podsumowanie

1. Utworzyłeś bibliotekę `STUDENTx`.
2. Przygotowałeś pliki źródłowe.
3. Utworzyłeś program CLLE.
4. Skompilowałeś i uruchomiłeś swój program.

<br />
  
Gotowe do uruchomienia i przedstawienia! 🎉
