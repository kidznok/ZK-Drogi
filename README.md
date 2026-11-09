# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.47 — PI dodawany natywnym uchwytem
- Dodanie jednego wewnętrznego wierzchołka na RS_CONTROLS nie jest już blokowane ogólnym komunikatem o zmianie liczby PI.
- Natywna edycja używa tego samego mechanizmu co Dodaj PI w oknie geometrii: zachowanie tożsamości łuków i powiązań krawędzi, poboczy, poszerzeń, profili i skarp.
- Dodawaj jeden wewnętrzny PI na polecenie, pozostawiając pozostałe punkty bez zmian. Usuwanie PI, dopisywanie punktów poza końcami oraz mieszane operacje dostają osobny komunikat i nie zmieniają poprawnej osi.
- Po dodaniu wybierz Geometria osi i wskaż nowy PI, aby ustawić R/L₁/L₂. Przy wyłączonej automatyce użyj Aktualizuj plan.

425 testów obliczeniowych i 12 testów aktualizatora. Kompilacja pluginu dla BricsCAD V26. Natywnego dodania uchwytem na rysunku użytkownika jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.47. 3D i skarpy pozostają do osobnego przeliczenia.