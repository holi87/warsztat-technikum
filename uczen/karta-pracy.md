# IT wspierane AI — karta pracy

Pracujesz w ChatGPT, Claude albo innym zatwierdzonym czacie AI. Prompty nie wymagają konkretnej marki ani płatnej funkcji. Jeśli narzędzie ma podgląd aplikacji, możesz z niego skorzystać. Końcowy plik zapisz jako HTML, żeby móc do niego wrócić poza czatem.

Twój cel: mały quiz, jedna własna zmiana, trzy testy i sprawdzenie jednej poprawki. Odpowiedzi zapisuj w swoim dokumencie tekstowym. Ta karta jest instrukcją, nie formularzem zapisującym Twoją pracę.

## 1. Bezpieczna decyzja — 10 minut

Wszystkie poniższe sytuacje są fikcyjne. Nie używaj prawdziwych danych, nie otwieraj podejrzanych linków i niczego nie instaluj.

**A. Dane w prompcie**

Kolega proponuje: „Wklejmy do AI imię, nazwisko, numer telefonu i oceny ucznia, żeby przygotowała mu quiz do poprawy sprawdzianu”. Czy te dane są potrzebne do zadania?

**B. Pilna wiadomość**

Z konta znajomego przychodzi: „Potrzebuję natychmiast kodu BLIK, oddam za godzinę. Nie dzwoń, nie mogę rozmawiać”. Co zrobisz przed odpowiedzią?

**C. Dodatkowa instalacja**

Na stronie z poradą widzisz: „Żeby uruchomić quiz z AI, pobierz nasz dodatek z tego linku i przyznaj mu dostęp do wszystkich stron”. Czy zainstalujesz dodatek?

Dla każdej sytuacji zapisz: **ryzyko, decyzję i bezpieczny następny krok**. Jeśli skończysz wcześniej, przepisz prompt z sytuacji A, usuwając zbędne dane.

## 2. Własny prompt — 15 minut

Otwórz `notatka-zrodlowa.txt`. Wklej notatkę do rozmowy razem z poniższą instrukcją. Tekst w nawiasach kwadratowych zastąp własną treścią.

### P1 — pytania do quizu

```text
Przygotuj quiz do nauki dla osoby początkującej w tworzeniu stron WWW.
Użyj wyłącznie informacji z notatki poniżej.

Wymagania:
- 5 pytań, po 3 odpowiedzi: A, B, C.
- Dokładnie jedna poprawna odpowiedź na każde pytanie.
- Prosty język i krótkie wyjaśnienie poprawnej odpowiedzi.
- Nie dodawaj wiedzy, której nie ma w notatce.

Zwróć tabelę: pytanie, A, B, C, poprawna odpowiedź, wyjaśnienie.
Na tym etapie nie pisz kodu aplikacji.
Jeśli brakuje informacji potrzebnej do wykonania zadania, wskaż brak.

NOTATKA:
[wklej treść pliku notatka-zrodlowa.txt]
```

Sprawdź liczbę pytań, jednoznaczność odpowiedzi i zgodność ze źródłem. Potem doprecyzuj co najmniej jedną rzecz. Możesz użyć wzoru:

```text
W pytaniu [numer] zauważyłem [konkretny problem].
Popraw [dokładny zakres zmiany]. Pozostałe pytania zachowaj.
Ponownie podaj poprawną odpowiedź i krótkie wyjaśnienie.
```

Jeśli nie widzisz błędu, doprecyzuj język albo format. Zapisz pierwszy prompt, poprawiony prompt i jedną zauważoną różnicę.

**Bez dostępu do AI:** przeanalizuj przygotowany przykład. To celowo niedoskonała próbka do oceny, nie zapis działania konkretnego narzędzia:

| Pytanie | Odpowiedzi | Wskazany klucz |
|---|---|---|
| Co opisuje HTML? | A: strukturę i treść; B: wyłącznie kolory; C: hasło do strony | A |
| Za co odpowiada CSS? | A: wygląd strony; B: zasilanie komputera; C: numer telefonu | A |
| Co może robić JavaScript? | A: reagować na kliknięcie; B: aktualizować wynik; C: obie te czynności | C |
| W którym roku powstał JavaScript? | A: 1995; B: 2005; C: 2015 | A |
| Do czego służy element body? | A: do treści strony; B: do hasła; C: do numeru telefonu | A |

Wskaż pytanie, którego odpowiedzi nie da się potwierdzić w notatce. Sprawdź też, czy odpowiedzi są dobrze skonstruowane i czy dodano wymagane wyjaśnienia. Napisz prompt poprawiający wynik i sam zaproponuj jedną poprawkę.

## 3. Plan quizu — 10 minut

Najpierw sam opisz przebieg: start, pytanie, wybór odpowiedzi, wyjaśnienie, kolejne pytanie, wynik. Wybierz 3–5 konkretnych wymagań, które potrafisz sprawdzić.

Przykład: „Restart zeruje wynik i pokazuje pierwsze pytanie”.

### P2 — pomoc w planowaniu

```text
Planuję prosty quiz w jednym lokalnym pliku HTML.
To mój przebieg działania i wymagania:
[wklej swój plan]

Wskaż niejasności i brakujące decyzje. Nie pisz jeszcze kodu.
Rozdziel opis na: ekran użytkownika, dane pytań, zasady punktacji.
Uwzględnij, że jeden wybór kończy odpowiadanie na dane pytanie,
a restart zeruje wynik i wraca do początku.
Nie dodawaj logowania, serwera ani nowych funkcji bez pytania.
```

Przeczytaj uwagi AI. Zapisz **swój zatwierdzony plan**. Możesz odrzucić sugestię, jeśli potrafisz wyjaśnić dlaczego. Bez AI omów plan z drugą osobą.

## Przerwa — 10 minut

Zapisz dotychczasową pracę. Po powrocie budujemy aplikację.

## 4. Własny quiz — 30 minut

### P3 — budowa aplikacji

```text
Zbuduj quiz do nauki na podstawie zatwierdzonych pytań i planu poniżej.
Zwróć kompletny kod jednego pliku HTML z CSS i JavaScript w środku.
Plik ma działać lokalnie w przeglądarce, bez serwera, internetu,
zewnętrznych bibliotek, logowania i zbierania danych użytkownika.

Wymagania:
- 5 pytań, po 3 odpowiedzi, dokładnie jedna poprawna.
- Jedno pytanie widoczne naraz.
- Po pierwszym wyborze zablokuj zmianę odpowiedzi w tym pytaniu.
- Poprawna odpowiedź daje 1 punkt, błędna 0.
- Każde pytanie może dodać najwyżej 1 punkt. Wynik: 0–5.
- Pokaż krótkie wyjaśnienie po odpowiedzi.
- Przycisk „Dalej” jest dostępny po udzieleniu odpowiedzi.
- Na końcu pokaż wynik i przycisk „Zacznij od nowa”.
- Restart zeruje wynik i pokazuje pierwsze pytanie.
- Polski interfejs, czytelne przyciski i obsługa klawiaturą.

Nie zmieniaj znaczenia zatwierdzonych pytań ani klucza odpowiedzi.

PYTANIA Z KLUCZEM:
[wklej sprawdzone pytania, odpowiedzi i wyjaśnienia]

PLAN:
[wklej swój zatwierdzony plan]
```

### Zapisanie i uruchomienie

1. Jeśli czat udostępni plik HTML, pobierz go. Jeśli poda kod, skopiuj sam kod, bez otaczających znaczników bloku.
2. Wklej kod do zwykłego edytora tekstu lub edytora kodu. Zapisz jako `quiz.html`, kodowanie UTF-8. Nie używaj Worda.
3. Sprawdź, czy plik nie nazywa się `quiz.html.txt`. W Windows podczas zapisu może być potrzebny typ „Wszystkie pliki”. W macOS edytor musi zapisywać zwykły tekst, nie RTF.
4. Otwórz plik w przeglądarce. Po zmianach zapisz plik i odśwież stronę.

Korzystaj ze sposobu uruchamiania zatwierdzonego przez prowadzących. Jeśli pojawi się prośba o instalację, dodatkowe uprawnienia lub połączenie z inną usługą, zatrzymaj się i poproś o pomoc.

**Twoja zmiana:** zmień tytuł, kolor albo sposób wyjaśniania odpowiedzi. Napisz konkretnie, co chcesz zmienić i co ma pozostać bez zmian. Zapisz, jak sprawdzisz efekt.

**Jeśli utkniesz:** użyj `quiz-start.html`. Jest działającym punktem wyjścia. Możesz poprosić AI o jedną zmianę w jego kodzie. Bez AI otwórz go w edytorze i zmień tytuł w elemencie `h1` albo kolor `--accent` w CSS. Zapisz kopię jako `quiz.html`, odśwież i porównaj.

**Dla chętnych:** dodaj losowanie pytań. Sprawdź, czy nadal pojawia się każde pytanie dokładnie raz. Nie dodawaj kilku funkcji naraz.

## 5. Treść i działanie — 5 minut

Wybierz jedno pytanie w swoim quizie. Porównaj odpowiedź z notatką i zapisz zdanie, które ją potwierdza. Następnie **bez AI** wymyśl trzy testy działania aplikacji.

Dla każdego testu zapisz, co zrobisz i jakiego efektu oczekujesz. Nie wystarcza „sprawdzę restart”. Napisz: „Po zdobyciu punktu kończę quiz, uruchamiam go od nowa i oczekuję wyniku 0 oraz pierwszego pytania”.

## 6. Polowanie na bugi — 15 minut

Wykonaj trzy testy: wielokrotne kliknięcie odpowiedzi, punktacja, restart. Użyj własnego quizu albo zamień się z sąsiadem. Jeśli nie znajdujesz błędu, otwórz `quiz-do-testow.html`. To celowo niedoskonały materiał ćwiczeniowy.

| Test | Kroki | Wynik oczekiwany | Wynik rzeczywisty | Status |
|---|---|---|---|---|
| Wielokrotny klik |  |  |  |  |
| Punktacja |  |  |  |  |
| Restart |  |  |  |  |

Możesz skopiować tabelę do dokumentu albo użyć `karta-testow.tsv`. Status: **zgodny, błąd lub nie sprawdzono**. Zapisuj fakty, również wtedy, gdy aplikacja działa poprawnie.

### P4 — dodatkowy pomysł na test

```text
Testuję quiz o takich wymaganiach:
[wklej wymagania]

Wykonałem już te testy:
[wklej kroki i rzeczywiste wyniki]

Zaproponuj 3 dodatkowe testy z krokami i oczekiwanym wynikiem.
Oddziel sprawdzanie wymagań od propozycji nowych funkcji.
Nie opisuj proponowanych testów jako wykonanych.
Nie deklaruj istnienia błędu bez potwierdzenia.
```

Wybierz jeden pomysł, oceń jego sens i wykonaj test. Opisz jeden **potwierdzony** błąd: tytuł, kroki, wynik oczekiwany, rzeczywisty i ewentualny zrzut. Bez AI wymień się dodatkowym pomysłem z sąsiadem.

## 7. Naprawa i retest — 10 minut

### P5 — poprawa jednego błędu

```text
Napraw jeden potwierdzony błąd w załączonym kodzie quizu.

Kroki odtworzenia:
[dokładne kroki od świeżego otwarcia strony]
Wynik oczekiwany:
[co powinno się wydarzyć]
Wynik rzeczywisty:
[co zaobserwowałeś]

Nie dodawaj nowych funkcji ani nie zmieniaj pytań, klucza i wyglądu,
jeżeli nie jest to konieczne do naprawienia zgłoszonego błędu.
Krótko wyjaśnij zmianę i zwróć kompletny poprawiony plik HTML.
Zaproponuj test naprawy i jeden test wcześniej działającej funkcji.
Nie twierdź, że testy wykonano, jeśli ich nie uruchomiłeś.

KOD:
[wklej kod pliku]
```

Zapisz nową wersję jako `quiz-v2.html`. Otwórz ją w nowej karcie. Powtórz kroki błędu i jeszcze jeden wcześniejszy test. Zapisz wynik **przed zmianą i po zmianie**.

Jeśli poprawka nie działa, zaznacz to i doprecyzuj zgłoszenie. Nie ukrywaj niepowodzenia. Bez AI poproś prowadzącego o poprawny quiz i sprawdź go tymi samymi testami. Jest to weryfikacja przygotowanej poprawki.

## Na koniec

Zachowaj prompt, plik HTML i wyniki testów. Zapisz po jednym zdaniu:

- Stworzyłem / zmieniłem…
- Samodzielnie sprawdziłem…
- AI pomyliła się w… / jeszcze nie potwierdziłem…

Nie publikujemy projektu w trakcie tego warsztatu. Możesz wrócić do niego później i do każdej nowej funkcji dopisać test.
