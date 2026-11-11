# ZK Drogi 0.80 — mapowanie i punkty szerokości

- Analiza warstw dobiera odniesienia po warstwie, zakresie kilometrażu i stronie osi. Inne odcinki tej samej warstwy nie powodują fałszywej niejednoznaczności.
- Nowe ciemne okno ma widoczną listę odniesienia w każdym wierszu, zawijane komunikaty i gotowe elementy na początku. Częściowe pokrycie wymaga ręcznego wyboru; nie jest automatycznie uznawane za pełne.
- Pobocza korzystają z odcinkowego doboru jezdni, również kilku kolejnych polilinii. Istniejące przypisania pozostają zapisane; zatwierdzenie nowych elementów odbywa się w jednej transakcji. Błąd zachowuje wybory w oknie.
- Polilinie o niejednoznacznym kilometrażu, np. kilka punktów poza końcem osi, nadal wymagają sprawdzenia geometrii i nie są przypisywane przez zgadywanie.
- Naprawiono odtwarzalny przypadek kolizji znaczników wierzchołka: kilka bliskich punktów szerokości z tym samym znacznikiem nie zapada się już do jednego kilometrażu po zmianie osi. Zachowane są punkty, ich szerokości i korekty. Najbliższy punkt zachowuje przypisanie do wierzchołka, pozostałe położenie na odcinku.
- Diagnostyka nieprawidłowych szerokości podaje indeks i kilometraże; podczas nakładania wiązania także handle i warstwę elementu.

Weryfikacja: 635 testów geometrii i polityk; testy WPF na odizolowanym pulpicie obejmują wybór odniesień, częściowe pokrycie, blokadę nieprawidłowych wierszy, zachowanie wyborów po błędzie i układ bez przewijania w bok przy szerokości 880 px. Kompilacja z SDK BricsCAD. Nie wykonano pełnej próby na aktualnym DWG użytkownika; dostępny log nie zawierał nowego błędu ze zrzutu, więc nie potwierdzono, że kolizja znaczników jest jego jedyną przyczyną.