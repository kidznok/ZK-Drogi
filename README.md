# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.43 — kompaktowe okno i oznaczenia poszerzeń
- Ciemne okno geometrii zgodne z zaakceptowanym układem: R/L₁/L₂ w jednym rzędzie, podgląd, rozwijane parametry, stała belka Cofnij zmiany / Zastosuj.
- Nagłówek z PI, nazwą osi i kilometrażem; wybieranie PI na rysunku i nawigacja.
- Przerywana krawędź nominalna na zakresie poszerzenia, z zachowaniem zapisanych korekt ręcznych.
- Wymiary w jednym ciągu prostopadłym do osi: pas | pas na początku wprowadzenia, pas | pas | poszerzenie na początku łuku. Analogicznie na wyprowadzeniu. Natywne wymiary CAD, bez odnośnika poszerzenia.
- Aktualizacja planu odtwarza oznaczenia bez kolejnych kopii. 3D i skarpy pozostają ręczne.

396 testów obliczeniowych, test rzeczywistego panelu WPF z inspekcją wyrenderowanego wyglądu i 12 testów aktualizatora. Nowych wymiarów w natywnej sesji BricsCAD jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Potem Aktualizuj plan oraz Geometria osi. Wersja 0.43.