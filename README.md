# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.52 — W i przybliżanie planu
- Geometria osi otwiera okno od razu, bez wskazywania punktu na rysunku. Strzałki przełączają wybrany W (wierzchołek).
- U góry domyślnie włączone „Przybliż do W”: przełączenie W pokazuje jego okolicę wraz z łukiem i klotoidami w bieżącej rzutni planu. Przełącznik można wyłączyć.
- Niezależne przełączniki dla promienia, L₁, L₂, przechyłki oraz ramp wejściowej i wyjściowej. Wartości ręczne pozostają zachowane, tryby zapisują się przy danym PI w DWG.
- Automatyczny dobór przechyłki z R i prędkości zamiast stałego 5%; zachowanie daszka tam, gdzie pozwalają na to tabela, klasa i szerokość jezdni. Automatyczne rampy z kontrolą dodatkowych pochyleń krawędzi.
- Stare ustawienia pozostają ręczne — zaznacz Auto przy parametrach, które program ma dobierać. Nowe ustawienia ramp domyślnie korzystają z automatyki. To kontrola obsługiwanych warunków WR-D-22-2, nie pełny audyt projektu.
- Sekcja „Przekroje”: Wstaw przekrój oraz Odśwież przekroje. Wskaż miejsce na osi, potem punkt wstawienia przekroju w DWG. Powstaje też edytowalna linia na planie.
- Wstawienie od razu rysuje przekrój z rzędnymi, szerokościami i pochyleniami, również przy wyłączonej automatycznej aktualizacji. Bez przebudowy modelu 3D.
- Napisy spadków mają mniejszy domyślny rozmiar i zapis bez zbędnych zer: -2%, -8%, 3.5%. Istniejące domyślne ustawienia są migrowane; własne rozmiary pozostają zachowane. Po aktualizacji odśwież plan.
- Zastosowanie przechyłki pozostawia okno ramp otwarte. Można wykonywać kolejne korekty i ponownie je zapisywać.
- Wąskie okno geometrii z przyciskiem Proponuj oraz osobne okno Przechyłka i rampy.
- Dobór R i klotoid dla prędkości osi; kontrola tablicowych promieni, przyrostu przyspieszenia, kąta klotoid i miejsca między PI. Propozycja dla przechyłki 5%; widoczność i warunki lokalne wymagają osobnej oceny.
- Sterowanie długością rampy albo |Δi| krawędzi L/P. Wynikowe pochylenia krawędzi uwzględniają niweletę, łuki pionowe i zmienne szerokości pasa.
- Zapis spadków jezdni i poboczy na planie; automatyczne etykiety powiązane z łukiem, ochrona ręcznych korekt i usuniętych manipulatorów.
- Najpierw zastosuj geometrię, potem otwórz rampy. W tej wersji obrót odbywa się wokół osi drogi. Model 3D i skarpy pozostają do osobnego przeliczenia.

461 testów obliczeniowych, testy okien WPF i 12 testów aktualizatora przechodzą. Kompilacja bez ostrzeżeń i błędów. Natywny zapis, przebudowa i nowe przybliżanie rzutni w BricsCADzie nie zostały jeszcze zweryfikowane. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.52.
