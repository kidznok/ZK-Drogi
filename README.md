# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.46 — naprawa błędu Dodaj PI
- Naprawiony komunikat „Nie można narysować krawędzi nominalnej z zadaną dokładnością”.
- Nominalna krawędź poszerzenia używa wspólnego połączenia przy wierzchołkach zamiast skoku normalnej, który powodował niekończące się zagęszczanie.
- Próbkowanie pomocniczej linii jest ograniczone. Ewentualna nieciągłość tworzy lokalną przerwę w oznaczeniu, a nie wyjątek cofający poprawną oś i jej zależności.
- Zachowano walidację osi, parametry łuków i klotoid oraz zapisane szerokości i korekty. Nowy edytor profilu z wersji 0.45 pozostaje.

419 testów obliczeniowych i 12 testów aktualizatora. Kompilacja pluginu dla BricsCAD V26. Ponowienia na rysunku użytkownika w natywnej sesji CAD jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Po restarcie ponów Geometria osi → Dodaj PI. Wersja 0.46.