# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.35 — droga i rowy: osobny edytor niwelety
- Wspólny wykres i niezależne niwelety drogi oraz rowów; pasma rzędnych projektowanych, terenu, spadków i geometrii.
- Edycja PVI uchwytami w oknie i w tabeli, dodawanie/usuwanie punktów, cofanie, zbliżenie i przesuwanie wykresu.
- Łuki pionowe kołowe zadawane promieniem R; obliczenia T, długości, PŁ/KŁ, rzędnej na łuku i pochyleń stycznych. Kontrola nakładania krzywych.
- Zastosuj zapisuje dane i aktualizuje wykres z pasmami w DWG. Te same obliczenia wysokości obsługują model 3D.
- Pobieranie terenu z 3DFACE w Xrefie. Po zmianie osi/Xrefa pobierz przekrój terenu ponownie.

Praca: oś → krawędzie/pobocza → opcjonalnie własne polilinie rowów przez Dodaj rów → Teren do profilu → Edytor niwelety → Zastosuj → Utwórz / odśwież 3D → Przelicz skarpy.

Zamknij BricsCAD przed instalacją. Wymagany .NET Desktop Runtime 8.0.33+ z linii 8; instalator niepodpisany cyfrowo.

299 testów obliczeniowych, 12 aktualizatora oraz testy rzeczywistych kontrolek WPF bez użycia ekranu przechodzi. Integracji nowego edytora w BricsCAD V26 nie potwierdzono jeszcze na natywnym DWG. Łuki pionowe są kołowe, bez parabol i automatycznej kontroli WR-D. Nie wykonano benchmarku setek polilinii/10 km. To wydanie nie zawiera nowych poprawek nakładania skarp i położenia ich etykiet. Szczegóły: ZMIANY-AKTUALNE.md.

## Publikowanie
Numerowany EXE w main uruchamia workflow: kontrola ProductVersion, SHA-256, stabilne wydanie Latest. Numeracja 0.35, 0.36 itd. Nie zmieniaj samej nazwy poprzedniego EXE.
