# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.44 — Dodaj PI, sterowanie profilem i kolory osi
- Geometria osi → + Dodaj PI → wskaż odcinek łamanej i nowe położenie punktu → ustaw R/L₁/L₂. Także dla osi złożonej z dwóch punktów.
- Dodanie PI uwzględnia zmianę indeksów istniejących łuków i kotwic powiązań krawędzi, poboczy, ręcznych poszerzeń, profili i skarp. Operacja jest transakcyjna.
- Profil: środkowy przycisk lub Przesuń do przesuwania wykresu w poziomie i pionie. Cały profil przywraca zakres. Śledź na planie włącza tymczasowy znacznik kilometrażu kursora/PVI na osi, bez zmiany rzutni i bez zapisywania znacznika w DWG.
- Prosta czerwona, łuk żółty, klotoidy pomarańczowe. Przywracanie widoczności i kolejności rysowania stylu; reprezentacja na wysokości niwelety zapobiega zasłanianiu kolorów przez czerwoną oś modelu w widoku cieniowanym.
- Nowy wygląd dużego edytora profilu pozostaje osobną propozycją. W tej wersji dodano sterowanie i śledzenie do obecnego okna.

412 testów obliczeniowych, testy rzeczywistych okien WPF osi/profilu i 12 testów aktualizatora. Natywnego dodania PI, znacznika i kolorów w otwartym BricsCADzie jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Następnie Aktualizuj plan. 3D i skarpy przeliczaj osobno. Wersja 0.44.