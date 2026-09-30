# Materiał awaryjny — bez dostępu do AI

Wszystkie odpowiedzi poniżej są **autorskimi przykładami dydaktycznymi**, nie zapisem rzeczywistego eksperymentu z modelem. Możesz na nich przećwiczyć ocenę; nie wyciągaj wniosków o skuteczności produktu.

## Prompt engineering i meta prompting

Przykład A dla D1: „CSS odpowiada za wygląd. Pytanie: Co robi CSS? A: wygląd, B: baza, C: serwer. Poprawna: A”.

Przykład B dla D1:
```json
[{"id":"D1","status":"ok","question":"Za co odpowiada CSS?","options":["Za wygląd strony","Za naliczanie punktów w quizie","Za przechowywanie kont"],"correct_index":0,"explanation":"Notatka przypisuje CSS określanie wyglądu strony.","source_quote":"CSS określa wygląd strony: kolory, odstępy i układ."}]
```

Przykład C dla D2: „Pytanie: Co oznacza HTML? A: HyperText Markup Language, B: Home Tool, C: High Text. Odpowiedź A”.

Przykład D dla D3: „BANAN”.

Oceń każdy przykład według C1–C5. C jest merytorycznie znajomy, ale oparty na wiedzy spoza pustej notatki. Zapisz, jak zmienić instrukcję. Dla T1 i T2 samodzielnie napisz zgodny z kontraktem wynik; kolega sprawdza. To ćwiczenie projektowania i oceny, nie test modelu.

## Brainstorming

Przykładowe różne mechanizmy: licznik ukończenia, wskazówka przed odpowiedzią, lista tematów do powtórki, wyjaśnienie błędnej opcji, porównanie pewności z poprawnością, ponowna próba po zakończeniu. Nie wszystkie mieszczą się w 20 minutach. Oceń zakres i wybierz jeden.

## Tutor

Najpierw przewidź wynik operacji. Potem przeczytaj: idempotencja oznacza, że ponowienie tej samej operacji daje taki sam efekt jak wykonanie jej raz. Ustawienie pola na ustaloną wartość ma tę własność w prostym modelu; zwiększenie licznika przy każdym wykonaniu jej nie ma. Zastosuj to do quizu, potem zamknij plik i wykonaj transfer z karty pracy.

## Mała zmiana w prototypie: licznik odpowiedzi

Pracuj na kopii quiz-start.html zapisanej jako quiz-moj.html. To jawna, niewielka poprawka do samodzielnego zrozumienia.

1. Dodaj przed elementem z `id="question"` akapit:
```html
<p id="answeredCount" aria-live="polite"></p>
```
2. W definicji `updateScore()` przed końcowym nawiasem `}` dopisz:
```javascript
$('answeredCount').textContent = 'Udzielone odpowiedzi: ' + (index + (answered ? 1 : 0)) + ' / ' + questions.length;
```
3. Zapisz, odśwież stronę i sprawdź: start 0/5, po pierwszej błędnej odpowiedzi 1/5 i wynik 0, po kolejnej odpowiedzi 2/5, wielokrotne kliknięcie nie zwiększa licznika, restart 0/5.

Wyjaśnij, dlaczego `answered` jest potrzebne oprócz `index`. Jeżeli edytor nie pozwala na zmianę pliku, zapisz dokładny plan i testy; uruchomienie demonstruje prowadzący.

## Skill i agent

Wymień procedurę z drugą osobą i wykonaj review ręcznie. Zapisz, czy brakujące wymaganie zostało wykryte. W zadaniu agenta jedna osoba dobiera krok po obserwacji, druga wykonuje test na quiz-do-testow.html. Przestrzegajcie budżetu i STOP. Oznaczcie „symulacja bez modelu”.
