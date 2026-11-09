# ZK Drogi 0.48 — geometria i osobne okno ramp

- Wąskie okno geometrii zachowuje szerokość. „Przechyłka i rampy →” otwiera osobne okno obok; można je niezależnie przesuwać i zamykać.
- „Proponuj” dobiera kandydaturę R/L₁/L₂ dla prędkości zapisanej w osi i przechyłki 5%. Sprawdza promień z tab. 7.1.2 WR-D-22-2:2023, granicę przyrostu przyspieszenia z tab. 7.1.5, kąt klotoidy i miejsce na stycznych wraz z sąsiednimi łukami. Brak miejsca kończy się komunikatem, bez obniżania wymagań.
- Propozycja nie jest pełnym audytem projektu: widoczność, warunki lokalne i zalecenia dotyczące przebiegu sąsiednich elementów wymagają osobnej oceny.
- Najpierw zastosuj geometrię. Potem otwórz rampy dla tego PI: ustaw daszek, przechyłkę, długości lub |Δi| lewej/prawej krawędzi oraz spadki poboczy. Obrót w tej wersji odbywa się wokół osi drogi.
- Okno pokazuje dodatkowe Δi oraz zakres rzeczywistego pochylenia podłużnego obu krawędzi z zapisanej niwelety, również na łukach pionowych. Uwzględnia szerokości i poszerzenia. Na rampie interpolowana jest wysokość krawędzi, nie sam procent.
- Kontrola promienia/przechyłki i minimalnego/maksymalnego Δi blokuje zapis poza obsługiwanym zakresem. Dobór obsługuje prędkości 30–140 km/h i przechyłki 2,5–7%; prędkości pośrednie sprawdzane są konserwatywnie według wyższego wiersza tabeli.
- „Zastosuj spadki na planie” zapisuje ustawienia przy osi i aktualizuje istniejące manipulatory przypisane do łuku lub tworzy brakujące. Obsługiwane są krawędzie jezdni odniesione do osi i pobocza odniesione do tych krawędzi; krótsze elementy są ograniczane do własnego zakresu.
- Po zmianie geometrii osi automatyczne etykiety podążają za granicami ramp. Ręcznie zmienione wartości i kilometraże oraz istniejące ręczne etykiety nie są nadpisywane. Usunięty automatyczny manipulator nie jest odtwarzany przy kolejnym przeliczeniu.
- Zachowano identyfikację ramp po dodaniu wewnętrznego PI. Nakładające się rampy lub wyjście poza oś są odrzucane transakcyjnie.
- Aktualizacja ramp nie przelicza automatycznie modelu 3D ani skarp. Zmiana rysunku po otwarciu okna blokuje zapis starego podglądu — otwórz rampy ponownie.

Źródło tabel: https://www.gov.pl/attachment/489a909f-ca76-4841-b485-bcdfc88f9bd2

Weryfikacja: testy obliczeniowe i testy obu okien WPF bez sterowania ekranem. Pełny zapis i przebudowa na natywnym DWG w BricsCADzie nie zostały jeszcze zweryfikowane. Instalacja wymaga zamknięcia wszystkich sesji BricsCAD.
