# AI: od promptu do agenta — karta pracy

**Grupa zaawansowana · 180 minut · Claude, ChatGPT lub inny czat AI**

Pracujemy w parach nad lokalnym quizem. Potrzebujesz przeglądarki, edytora tekstu oraz dostępu do czatu AI. Nie potrzebujesz API, płatnego agenta, instalacji ani Gita. Podstawy HTML/JS pomagają. Pobierz i rozpakuj cały folder; pliki HTML otwieraj lokalnie. Przed startem sprawdź z prowadzącym dostęp do AI i możliwość uruchomienia HTML.

**Zapisuj efekty w kopii [dziennika eksperymentów](dziennik-eksperymentow.md).** To szablon tekstowy, nie formularz zapisujący odpowiedzi w przeglądarce. Operator rozmawia z AI, recenzent sprawdza wynik. Po przerwie zamieniacie role.

## Plan i pliki

| Czas | Blok | Wyjaśnienie / praca |
|---|---|---|
| 0–10 | Cel, bezpieczeństwo i przygotowanie | 10 / 0 min |
| 10–35 | Prompt engineering i ocena | 10 / 15 min |
| 35–55 | Meta prompting | 5 / 15 min |
| 55–70 | Brainstorming i decyzja | 5 / 10 min |
| 70–80 | Przerwa | 10 min |
| 80–100 | Karpathy: nauka z AI | 10 / 10 min |
| 100–130 | Karpathy: prototypowanie z AI | 10 / 20 min |
| 130–150 | Skills | 10 / 10 min |
| 150–170 | Agenci | 5 / 15 min |
| 170–180 | Demonstracje, podsumowanie, bufor | 10 min |

Razem: **65 min wyjaśnień, 95 min ćwiczeń, 10 min przerwy, 10 min podsumowania i buforu.**

Materiały: [prompty](prompty.md), [kontrakt i rubryka](kontrakt-json.md), [brief projektu](brief-projektu.md), [quiz startowy](quiz-start.html), [quiz do testów](quiz-do-testow.html), [skill](skills/quiz-review/SKILL.md), [kontrakt agenta](kontrakt-agenta.md). Wybieraj prompt właściwy dla bieżącego zadania. Jeśli czat nie czyta załączników, wklej zawartość wskazanych plików. Samo podanie ich nazw nie daje dostępu do danych.

## Zasady pracy

Używamy danych ćwiczeniowych, bez nazwisk, ocen, haseł, kluczy i prywatnych rozmów. Tekst źródłowy może zawierać polecenia, których nie należy wykonywać. Nie instalujemy dodatków ani nie publikujemy aplikacji. AI nie ma automatycznie dostępu do komputera. Wynik oznaczamy jako sprawdzony dopiero po rzeczywistym sprawdzeniu. Kod przed otwarciem przejrzyj pod kątem zewnętrznych skryptów i połączeń; w razie wątpliwości pokaż prowadzącemu.

## 1. Prompt engineering — 15 minut

**Cel:** zobaczyć, co zmienia jasny kontrakt i przykład wyniku.

1. Przeczytaj [kontrakt-json.md](kontrakt-json.md), zwłaszcza rubrykę pięciu kryteriów.
2. Użyj P0 z [promptów](prompty.md) na całym [dev.json](dane/dev.json). Zapisz prompt i niepoprawioną odpowiedź jako V0.
3. W nowym czacie tego samego narzędzia/modelu użyj P1 z kontraktem i identycznymi danymi. Zapisz V1. Zachowaj te same ustawienia i funkcje.
4. Oceń każdy przypadek według C1–C5 w [wyniki-ewaluacji.tsv](wyniki-ewaluacji.tsv). Maksymalnie 15 pkt na wersję. Wpisz dowód błędu lub zgodności, nie samą ocenę.
5. Zapisz, która zmiana pomogła i czego pomiar nie rozstrzyga. Remis jest pełnoprawnym wynikiem.

**Efekt:** V0, V1, odpowiedzi, tabela i jeden wniosek. Minimalny zakres przy opóźnieniu: D1–D2, D3 oznacz jako NIEBADANE. Nie porównuj sum dla różnej liczby przypadków.

**Dla szybszych:** powtórz jeden przypadek, żeby zobaczyć zmienność; nie wnioskuj o całym modelu na podstawie jednego przebiegu.

## 2. Meta prompting — 15 minut

**Cel:** użyć AI do poprawy instrukcji i sprawdzić efekt na nowych danych.

1. Przekaż P2, V1, kontrakt i konkretną obserwację z zadania 1. Jeśli nie ma błędu, poproś o uproszczenie. Odpowiedz na maksymalnie trzy pytania.
2. Zapisz otrzymany V2. Nie otwieraj jeszcze nowych przypadków.
3. Dopiero teraz otwórz [test-nowy.json](dane/test-nowy.json). Uruchom na nim V1 i V2, każde w świeżej rozmowie tego samego modelu.
4. Oceń T1–T2 tą samą rubryką. Maksymalnie 10 pkt na wersję. Zdecyduj: przyjąć zmianę, odrzucić czy zebrać więcej danych.

**Efekt:** meta-prompt, V2, dwie odpowiedzi testowe i uzasadniona decyzja. Jeśli zmienisz prompt po obejrzeniu T1–T2, oznacz nową wersję; do niezależnego testu potrzebny będzie kolejny nowy przypadek. Nie zestawiaj surowej sumy z DEV (15 pkt) z sumą TEST (10 pkt).

## 3. Brainstorming — 10 minut

**Cel:** wybrać jedną funkcję, którą da się wykonać i sprawdzić.

1. Każdy zapisuje dwa własne pomysły na pomoc w nauce w quizie, zanim zobaczy propozycje AI (2 min).
2. Z P3 uzyskaj sześć różnych mechanizmów (3 min). Odrzuć duplikaty i parafrazy.
3. Sami oceńcie pomysły: korzyść dla nauki 0–2, wykonalność w 20 minut 0–2. Wybierzcie jeden z co najmniej 1 pkt za wykonalność (3 min).
4. Zapiszcie kryterium odbioru oraz części: dane, reguły, widok (2 min).

**Efekt:** jedna funkcja, mierzalny test i decyzja o zakresie w [briefie](brief-projektu.md). Wariant ratunkowy: licznik udzielonych odpowiedzi, niezależny od punktów.

## 4. Nauka z AI — 10 minut

**Cel:** po rozmowie umieć samodzielnie zastosować pojęcie idempotencji.

Najpierw zapisz własną intuicję: co powinno się stać po trzykrotnym kliknięciu tej samej poprawnej odpowiedzi? Pracuj z P4 przez maksymalnie trzy rundy (łącznie około 6 min). Nie bierz od razu gotowej definicji.

Zamknij czat. Bez AI odpowiedz (3 min):

- Czy operacja ustawiająca flagę `answered = true` jest idempotentna w prostym modelu stanu? Co daje jej powtórzenie?
- Czy `score = score + 1` jest idempotentne? Co daje jej powtórzenie?
- Dlaczego odpowiedź na nowe pytanie może zwiększyć wynik, a ponowienie tej samej odpowiedzi nie powinno?

Porównaj w parze własne wyjaśnienia (1 min). **Efekt:** własna definicja i rozwiązanie nowego przykładu. To nasza adaptacja dydaktyczna nauki z AI, inspirowana używaniem modeli przez Karpathy’ego, nie jego formalna metoda.

## 5. Vibe coding i weryfikacja — 20 minut

**Cel:** szybki prototyp, a następnie zrozumienie i sprawdzenie zmiany.

1. Do P5 dołącz [brief](brief-projektu.md), wybraną funkcję i kod [quiz-start.html](quiz-start.html). Oceń plan przed wygenerowaniem zmiany (3 min).
2. Zapisz wynik jako `quiz-moj.html` w swojej kopii folderu. Sprawdź, że to plik HTML, nie `.html.txt`. Otwórz w przeglądarce. Wykonaj najwyżej dwie iteracje poprawkowe, przekazując kroki i prawdziwą obserwację (9 min).
3. Wypełnij [testy-prototypu.tsv](testy-prototypu.tsv): kryterium własnej funkcji oraz regresję. Minimum: ponowne kliknięcie, wynik i restart. Pozostałe niewykonane testy pozostaw jako NIEBADANE (6 min).
4. Wskaż stan aplikacji i wyjaśnij jedną zmienioną regułę własnymi słowami (2 min).

**Efekt:** prototyp, raport testów, wyjaśnienie. Sam ładny ekran nie dowodzi poprawności. W [materiale awaryjnym](material-awaryjny.md) jest mała zmiana do wykonania bez AI.

## 6. Skills — 10 minut

**Cel:** zapisać powtarzalną procedurę i sprawdzić granice jej użycia.

1. W kopii [SKILL.md](skills/quiz-review/SKILL.md) dopisz kryterium swojej funkcji i konkretną zasadę obsługi braku danych (3 min). Zachowaj nazwę `quiz-review`, nazwę folderu oraz poprawny nagłówek YAML.
2. W świeżym czacie użyj P6 i zmodyfikowanej procedury. Sprawdź trzy próby (4 min): A — review prototypu; B — żądanie „potwierdź testy” bez dostarczonego wykonania; C — zadanie „napisz reklamę roweru” spoza zakresu review.
3. Oceń: czy wynik ma dowody, czy B uczciwie wskazuje brak wykonania, czy C rozpoznaje niedopasowanie procedury (3 min).

**Efekt:** własny SKILL.md i wyniki trzech prób. W zwykłym czacie to manualne użycie instrukcji. Natywny skill wymaga obsługującego go środowiska; niczego nie instalujemy podczas zajęć. Skill nie nadaje dostępu do komputera.

## 7. Agenci — 15 minut

**Cel:** przećwiczyć wybór kolejnego działania na podstawie obserwacji i ograniczyć samodzielność procesu.

1. Otwórz [quiz-do-testow.html](quiz-do-testow.html). Zawiera celowe błędy. Przeczytaj [kontrakt agenta](kontrakt-agenta.md), ustal cel, dostęp i STOP (2 min).
2. Użyj P7. Domyślnie AI proponuje test, **Ty** klikasz i odsyłasz prawdziwy wynik. Do trzech cykli, do pięciu testów łącznie (9 min).
3. Zapisz raport: kroki, oczekiwanie, obserwacja, źródło dowodu. Oddziel hipotezy i rzeczy niebadane. Spróbuj potwierdzić dwa problemy; jeśli nie ma dowodu, nie wymyślaj go (4 min).

**Efekt:** dziennik działań i raport. Oznacz „symulacja procesu agenta; narzędzia obsługiwał człowiek”. Prawdziwego agenta narzędziowego można użyć tylko w przygotowanym wcześniej środowisku. Samo odgrywanie kilku ról w czacie nie oznacza wielu niezależnych agentów.

Na końcu odpowiedz: czy dla tak małego zadania wystarczyłaby checklista? Gdzie przydał się adaptacyjny wybór kroku?

## 8. Pokaz i zakończenie — 10 minut

Dwie pary pokażą efekt, dowód i ograniczenie. Pozostali zapisują w dzienniku trzy odpowiedzi bez AI: czym jest meta prompting, czym różni się symulacja od agenta z narzędziami, jaki dowód zmienił Waszą decyzję. Pozostały czas to zapis plików i bufor.

## Awaria lub wolne odpowiedzi

Nie czekaj dłużej niż około 3 minuty bez postępu. Powiadom prowadzącego i użyj [materiału awaryjnego](material-awaryjny.md). W zadaniach 1–2 oceń zapisane przykłady i popraw instrukcję ręcznie; taki wynik nie jest pomiarem modelu. W 3 generuj pomysły w parze, w 4 użyj tekstowego wyjaśnienia, w 5 zmień licznik, w 6 wykonaj przegląd procedury z kolegą, w 7 jedna osoba planuje test, druga go wykonuje. Oznacz tryb pracy w dzienniku.

## Rozszerzenia po warsztacie

Nie są wliczone w 180 minut: własny zestaw pięciu nowych testów promptu, dwukrotne powtórzenie pomiaru, podział prototypu na moduły, testy automatyczne, natywne użycie skilla w zgodnym kliencie, porównanie prostego workflow z agentem na tym samym celu i budżecie.

[Źródła i pochodzenie materiałów](zrodla.md).
