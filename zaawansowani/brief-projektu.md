# Projekt: quiz, który pomaga się uczyć

Użytkownik zna podstawy HTML/CSS/JS i chce sprawdzić wiedzę. Rozbuduj lokalny quiz o **jedną** funkcję edukacyjną wybraną podczas brainstormingu. Masz 20 minut na implementację, testy i zapis wyniku.

## Wymagania bazowe

- Pięć pytań z `dane/notatka-www.txt`, po trzy odpowiedzi, jedna poprawna.
- Jeden punkt za poprawną odpowiedź; zakres wyniku 0–5.
- Jedno pytanie może zmienić wynik tylko raz, także po szybkim wielokrotnym kliknięciu.
- Wyjaśnienie po odpowiedzi; przycisk następnego pytania dostępny dopiero po wyborze.
- Restart zeruje wynik, postęp i stan udzielonych odpowiedzi.
- HTML, CSS i JavaScript w jednym lokalnym pliku. Bez połączeń sieciowych, zewnętrznych bibliotek, logowania i zapisu danych osobowych. Świadome ograniczenie małego prototypu.
- Przyciski dostępne z klawiatury; widok czytelny przy szerokości 390 px.

## Twoja decyzja przed kodowaniem

Zapisz w dzienniku: odbiorcę, problem, wybraną funkcję, kryterium odbioru, czego nie budujesz. Wskaż, które części aplikacji zmienisz: dane / reguły / widok. Zapisz jeden kompromis, np. brak trwałego zapisu dla prostoty.

Przykładowy mały zakres: licznik udzielonych odpowiedzi, komunikat z obszarem do powtórki, wyjaśnienie typowego błędu. Timer, konta i ranking sieciowy łatwo przekraczają czas ćwiczenia.

## Domyślny wariant ratunkowy

Dodaj licznik odpowiedzi. Po dwóch różnych pytaniach ma pokazywać 2/5. Wielokrotny wybór w jednym pytaniu nie zwiększa licznika. Restart daje 0/5. Licznik mierzy liczbę odpowiedzi, a nie liczbę punktów.
