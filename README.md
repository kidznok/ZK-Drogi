# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.39 — elementy rozpoznawane z warstw
- Ustawienia → Mapowanie warstw: wzorzec warstwy, typ elementu z listy, odniesienie, spadek/uskok i podążanie w planie.
- Automatyczne przypisanie po dorysowaniu otwartej polilinii lub przeniesieniu nieprzypisanej polilinii na warstwę. Rozpoznawanie następuje po zakończeniu polecenia, bez modelowania 3D podczas rysowania.
- D01_KRAW_P rozpoznawany jako krawężnik z odniesieniem do D01_JEZ_P i uskokiem +0,12 m. Dobór po stronie oraz pełnym zakresie kilometrażu. Brak jednoznacznego odniesienia daje komunikat i wymaga Analizuj warstwy.
- Zmiana całej zarejestrowanej krawędzi jezdni na warstwę krawężnika zachowuje bazowe spadki i dodaje uskok.
- Przyciski Ustawienia, Analizuj warstwy, Utwórz warstwy i ręczny Krawężnik.
- BREAK istniejącej próbkowanej krawędzi z siecią zależności NIE jest w pełni obsługiwany. Zmiana liczby jej punktów zatrzymuje aktualizację. Do lokalnego krawężnika narysuj osobną krótką polilinię zamiast przecinać powiązaną krawędź.

Po instalacji: Ustawienia → Mapowanie warstw → Utwórz warstwy → dorysuj krótki krawężnik na D01_KRAW_L/P. Model 3D przelicz osobno.

Kompilacja z API V26 i testy obliczeń/warstw/routingu wstążki. Nowego przepływu zdarzeń nie zweryfikowano jeszcze w natywnym CAD. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wymagany V26 x64 i .NET Desktop Runtime 8 z linii 8. Wersja: 0.39.
