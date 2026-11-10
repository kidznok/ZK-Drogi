# ZK Drogi 0.74 — mapowanie poboczy do odcinków jezdni

- Mapuj krawędzie dobiera dla pobocza kolejne polilinie jezdni według kilometrażu, strony osi i reguły nazwy warstwy. Nie wymaga jednej polilinii jezdni obejmującej całe pobocze.
- Tolerancja końca odniesienia wynosi 1 m. Przypadek pobocza km 229,58–581,50 i jezdni 229,62–580,73 jest akceptowany. Polilinie źródłowe nie są skracane ani fizycznie dzielone.
- Na krótkim brakującym końcu odniesienia program przedłuża poprzeczne odsunięcie skrajnego punktu; jego wysokość utrzymuje na rzędnej końca odniesienia. To przybliżenie w granicach tolerancji, a nie odczyt brakującej geometrii.
- Odniesienie jest zapisane w odcinkach kilometrażu. Wysokości, model 3D, kreskowanie, spadki, podążanie w planie i przekroje korzystają z właściwego fragmentu jezdni. Zmiany szerokości kolejnych fragmentów propagują się na pobocze; zachowywane są ręczne wartości spadków.
- Ponowne Mapuj krawędzie analizuje również istniejące pobocza, zachowując ich etykiety i ręczne korekty.
- Rzeczywiste luki oraz nakładające się, niejednoznaczne jezdnie otrzymują czerwone opisy z kilometrażem na planie. Takie pobocze nie jest przypisywane automatycznie; pozostałe poprawne obiekty są przetwarzane. Ponowne poprawne mapowanie usuwa jego wcześniejsze opisy błędów.
- Polilinie cofające się względem kilometrażu, fragmenty poprzeczne i obiekty wykraczające poza oś nadal wymagają wyjaśnienia — warstwa nie wystarcza do bezpiecznego przypisania.

Po instalacji: Krawędzie i elementy → Mapuj krawędzie → Aktualizuj plan. Następnie przelicz 3D i skarpy.

Weryfikacja: 587 testów geometrii i polityk, w tym rzeczywista różnica końców 4/77 cm, dwa odniesienia, zmiana na styku, luki, niejednoznaczność, izolacja strony i nazwy drogi, podążanie za poszerzeniem drugiego fragmentu, zmiana długości osi i zapis/odczyt. Kompilacja z SDK BricsCAD bez błędów. Pełnego mapowania na otwartym rysunku CAD po tej zmianie jeszcze nie wykonano.
