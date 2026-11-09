# ZK Drogi 0.50 — Przekroje na wstążce

- Nowa sekcja „4. Przekroje” z przyciskami „Wstaw przekrój” (RSSECTION) i „Odśwież przekroje” (RSSECTIONUPDATE).
- Wstawianie: wskaż miejsce na osi, następnie punkt umieszczenia rysunku przekroju w DWG. Na planie powstaje polilinia przekroju do edycji uchwytami.
- Przekrój rysuje się od razu, również przy wyłączonej automatycznej aktualizacji przekrojów. Nie wymaga przebudowy modelu 3D.
- Pokazuje przecinane elementy drogi, rzędne, szerokości i pochylenia. Początek rysunku przekroju znajduje się przy wskazanym punkcie wstawienia.
- Po zmianie linii na planie wybierz „Odśwież przekroje”. Można wstawić wiele przekrojów w różnych miejscach.
- Poprawiono obsługę punktów wskazywanych w obróconym LUW. Brak elementów we wskazanym kilometrażu lub niejednoznaczne przecięcia powodują komunikat i wycofanie wstawienia.
- Wstążka jest odtwarzana z nową sekcją. Przy ręcznym ładowaniu można użyć RSRIBBON.

Weryfikacja: kompilacja, testy obliczeniowe i tras poleceń wstążki oraz testy aktualizatora. Wstawiania na natywnym DWG w BricsCADzie jeszcze nie zweryfikowano. Instalacja po zamknięciu wszystkich sesji BricsCAD.
