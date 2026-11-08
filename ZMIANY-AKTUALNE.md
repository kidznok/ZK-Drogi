# ZK Drogi 0.40 — boczna paleta geometrii osi

## Wskazanie i edycja PI
Przycisk Geometria osi (RSAXISEDIT) prosi o kliknięcie w okolicy wewnętrznego PI lub łuku, następnie otwiera dokowaną paletę boczną z podglądem. Wybór końca osi nie służy do wstawiania łuku: krzywa wymaga wewnętrznego PI.

- R: promień łuku.
- L₁ i L₂: niezależne długości klotoidy wejściowej i wyjściowej; mogą być różne. Wartość 0 wyłącza daną klotoidę.
- Tryby: załamanie, sam łuk kołowy, klotoida–łuk–klotoida.
- Podgląd lokalny: proste czerwone, łuk żółty, klotoidy pomarańczowe, PI i charakterystyczne granice.
- Wyniki: kąt zwrotu, zwrot, T₁/T₂, długość łuku i układu, A₁/A₂ oraz L₁/R i L₂/R.
- Poprzedni/Następny PI oraz Wskaż PI na rysunku. Przechodzenie między PI zachowuje poprawne szkice parametrów aż do Zastosuj.
- Cofnij parametry tego PI przywraca parametry zapisane przy załadowaniu osi.

## Zapis i bezpieczeństwo
Podgląd nie modyfikuje DWG przy wpisywaniu liczb. Przy zmianie pola sprawdza wybrany PI i jego sąsiadów; pełna geometria osi jest budowana dopiero przy zatwierdzeniu. Zastosuj kolejkuje polecenie zapisu w kontekście CAD. Oś, zależny plan i opisy aktualizują się w jednej transakcji. Błąd geometrii, nachodzenie sąsiednich krzywych lub nieudana aktualizacja planu odrzuca transakcję. Model 3D i skarpy pozostają do jawnego przeliczenia; rzutnia nie jest obracana.

Paleta kontroluje rysunek i odcisk geometrii: nie nadpisuje osi zmienionej uchwytem od jej załadowania i nie zapisuje do innego aktywnego DWG. Po takim komunikacie wskaż PI ponownie. Przy trwającym innym poleceniu CAD trzeba je najpierw zakończyć.

## Zgodność i geometria asymetryczna
Dawne dane z jedną długością L są odczytywane jako L₁=L₂. Nowy zapis przechowuje osobno długość wyjściową. Silnik rozróżnia dwie długości stycznych, sprawdza ich nakładanie między sąsiednimi PI i aktualizuje granice opisów, kolorów osi oraz odcinków poszerzeń. Model osi pozostaje poliliniową aproksymacją z tolerancją 0,5 mm.

Dotychczasowy przycisk Dodaj łuk / krzywe przejściowe (RSTRANSITION) otwiera tę samą paletę. Starsza tabela pozostaje dostępna poleceniem RSAXISTABLE; dawne symetryczne wstawianie poleceniem RSTRANSITIONLEGACY.

## Weryfikacja
Testy obliczeniowe krzywych symetrycznych/asymetrycznych, zerowej klotoidy po jednej stronie, domknięcia, odbicia, limitu kąta, kolizji sąsiadów i zgodności starego JSON. Test rzeczywistego kontrolera WPF w niewidocznym oknie: osobne R/L₁/L₂, nawigacja, kolory podglądu, cofanie, odrzucenie błędnych danych, wybór PI i blokada zamkniętego rysunku. Panel wyrenderowano i obejrzano. Dokowania palety i zapisu transakcji w natywnym BricsCAD jeszcze nie zweryfikowano.

Paleta używa [PaletteSet.AddVisual](https://developer.bricsys.com/bricscad/help/en_US/V25/DevRef/source/html/19454b32-1f75-02ce-64d8-d1f6e753bb6c.htm) z API Bricsys.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wersja: 0.40.

