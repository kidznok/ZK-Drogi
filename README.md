# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.41 — naprawa topologii i palety geometrii
- Paleta R/L₁/L₂ otwiera się bez przeliczania zależnych elementów i opisów.
- Poprawiono pozostawianie starej listy próbek po zmianie sposobu generowania krawędzi.
- Zastosuj geometrię odtwarza niespójne wyniki z zapisanych szerokości i poszerzeń, następnie aktualizuje oś, krawędzie i pobocza razem. Nazwy odtworzonych elementów są wypisywane w wierszu poleceń.
- Edycja R, L₁ i L₂ zachowuje zapisane korekty poszerzeń oraz szerokość pobocza. 3D i skarpy przeliczane osobno.
- Nie służy to do zatwierdzania BREAK/TRIM: niezapisane zmiany topologii wyniku zastępuje zapisane powiązanie. Krótsze elementy dodawaj osobnymi poliliniami.

382 testy obliczeniowe i test panelu WPF przechodzą. Natywnego testu w BricsCADzie nie przeprowadzono: niedostępne połączenie do aplikacji. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wersja 0.41.