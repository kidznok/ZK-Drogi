# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.36 — poprawki edytora niwelety
- Naprawiono przyczynę błędu Zastosuj i aktualizuj DWG potwierdzoną logiem użytkownika: eDegenerateGeometry przy opróżnianiu istniejącej polilinii profilu. Nowa aktualizacja nie usuwa wierzchołków poniżej docelowych dwóch.
- Przy błędzie zapisu transakcja jest cofana, a PVI wracają do edytora z komunikatem zamiast ginąć po zamknięciu okna.
- PPM na aktywnej niwelecie → Dodaj załom tutaj; na łuku zachowywany jest dotychczasowy kształt przez podział krzywej.
- Regularne kroki siatki, kilometraż 0+020, 0+040 itd., opis kroku i powiększenia pionowego. Pion automatyczny lub ×5/×10/×20.
- Żółte łuki pionowe i znaczniki PŁ/KŁ w edytorze oraz DWG.

Droga i rowy mają niezależne niwelety we wspólnym edytorze. Rów: własna polilinia → Dodaj rów → odniesienie/nazwa → Edytor niwelety → wybór rowu z listy.

320 testów obliczeniowych, 12 aktualizatora oraz testy WPF przechodzi. Nowego zapisu nie zweryfikowano jeszcze w natywnym BricsCAD; błąd poprzedniej wersji został potwierdzony logiem. Szczegóły i ograniczenia: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wymagany BricsCAD V26 x64 i .NET Desktop Runtime 8.0.33+ z linii 8. Po zapisaniu niwelety odśwież 3D i skarpy osobnymi poleceniami.
