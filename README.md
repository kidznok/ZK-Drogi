# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.42 — wąskie okienko geometrii i naprawa wydłużania osi
- Geometria osi jest osobnym, wąskim, pływającym oknem z R, L₁, L₂ i podglądem; bez dokowania palety.
- Naprawiono błąd uciętego JSON przy długich powiązaniach po wydłużeniu osi. Odczyt wszystkich fragmentów Xrecord oraz zapis w krótkich fragmentach.
- Zachowane naprawy 0.41: otwarcie edytora bez przebudowy opisów, odtworzenie niespójnych próbek z zapisanych szerokości i przeliczenie zależnych krawędzi/poboczy po zastosowaniu geometrii.
- Model 3D i skarpy przeliczane osobno.

386 testów obliczeniowych, test panelu WPF i 12 testów aktualizatora. Native API skompilowane dla BricsCAD V26; działania nowego okna wewnątrz CAD jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wersja 0.42.