# ZK Drogi 0.39 — rozpoznawanie elementów z warstw

## Ustawienia i rysowanie
Dodano do wstążki Ustawienia, Analizuj warstwy i Utwórz warstwy. W Ustawienia → Mapowanie warstw określasz wzorzec warstwy, typ elementu (lista wyboru), warstwę odniesienia, podążanie w planie oraz wartość spadku / uskoku.

Domyślna reguła: D01_KRAW_* → Krawężnik, odniesienie D01_JEZ_*, uskok +0,12 m. Końcówka L/P jest przenoszona do wzorca odniesienia: D01_KRAW_P szuka D01_JEZ_P.

Gdy włączone jest automatyczne rozpoznawanie, dorysowana otwarta polilinia lub nieprzypisana polilinia przeniesiona na pasującą warstwę jest analizowana po zakończeniu polecenia. Program rozpoznaje zakres kilometrażu, stronę i jednoznaczne odniesienie pokrywające cały fragment, tworzy element i regułę wysokości. W trakcie rysowania i przeciągania nie powstaje model 3D. Powierzchnie pozostają do jawnego przeliczenia.

Brak jednoznacznego odniesienia lub pasujące sprzeczne reguły powodują komunikat i pominięcie polilinii; Analizuj warstwy pozwala wskazać odniesienie ręcznie. Podkłady i reguły nieaktywne są pomijane. Można wyłączyć automatyczne rozpoznawanie checkboxem w Mapowaniu warstw.

## Zmiana typu istniejącego elementu
Przeniesienie całej zarejestrowanej krawędzi jezdni na warstwę krawężnika zachowuje dotychczasową bazową zależność wysokościową i dodaje uskok. Przykład: rzędna osi 100 m, szerokość 3,5 m i spadek -2% → krawędź 99,93 m; po zmianie na krawężnik +0,12 m → 100,05 m. Zachowane są wcześniejsze zmiany spadków i ich interpolacja.

## Ważne: przerwanie polilinii
Ta wersja NIE zapewnia automatycznego przepinania całej sieci poboczy/chodników po BREAK istniejącej, próbkowanej krawędzi. Zmiana liczby jej punktów jest wykrywana, aktualizacja zatrzymywana, a nieaktualny model ukrywany. Należy cofnąć takie przerwanie i narysować osobną krótką polilinię krawężnika. Samo mapowanie warstw nie zastępuje podziału logicznych zależności.

## Dostęp ręczny
Zachowano przycisk Krawężnik (RSADDCURB) w grupie 2. Krawędzie i spadki. Służy do ręcznego przypisania własnej krótkiej polilinii, odniesienia i uskoku.

## Weryfikacja
Testy doboru L/P, krótkich zakresów, niejednoznacznych odniesień, zachowania rzędnej bazowej i uskoku oraz istniejących funkcji. Kompilacja z API BricsCAD V26; nowego automatycznego przepływu zdarzeń nie zweryfikowano jeszcze w natywnym CAD.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wersja produktu: 0.39.
