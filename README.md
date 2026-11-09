# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.48 — geometria i osobne okno ramp
- Wąskie okno geometrii z przyciskiem Proponuj oraz osobne okno Przechyłka i rampy.
- Dobór R i klotoid dla prędkości osi; kontrola tablicowych promieni, przyrostu przyspieszenia, kąta klotoid i miejsca między PI. Propozycja dla przechyłki 5%; widoczność i warunki lokalne wymagają osobnej oceny.
- Sterowanie długością rampy albo |Δi| krawędzi L/P. Wynikowe pochylenia krawędzi uwzględniają niweletę, łuki pionowe i zmienne szerokości pasa.
- Zapis spadków jezdni i poboczy na planie; automatyczne etykiety powiązane z łukiem, ochrona ręcznych korekt i usuniętych manipulatorów.
- Najpierw zastosuj geometrię, potem otwórz rampy. W tej wersji obrót odbywa się wokół osi drogi. Model 3D i skarpy pozostają do osobnego przeliczenia.

439 testów obliczeniowych, testy okien WPF i 12 testów aktualizatora przechodzą. Kompilacja bez ostrzeżeń i błędów. Natywny zapis i przebudowa na DWG w BricsCADzie nie zostały jeszcze zweryfikowane. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.48.
