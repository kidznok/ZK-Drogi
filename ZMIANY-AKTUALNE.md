# ZK Drogi 0.49 — mniejsze opisy i otwarte okno ramp

- Zastosowanie przechyłki pozostawia okno ramp otwarte. Po udanym zapisie odświeżany jest stan sesji, więc można wykonać kolejne korekty i ponownie zastosować je do tego samego DWG. Zmiany rysunku wykonane poza oknem nadal wymagają ponownego otwarcia podglądu.
- Domyślne napisy spadków są mniejsze: skala opisów 1:200 i tekst 2 mm dają 0,40 m w modelu zamiast poprzednich 2,50 m. Stare, niezmienione ustawienia domyślne są przenoszone na mniejszy rozmiar również w istniejących DWG. Własne ustawienia skali lub wysokości pozostają zachowane.
- Napisy procentowe mają zapis bez zbędnych zer, np. -2%, -8%, 3.5%. Znaczące miejsca dziesiętne są zachowane do dwóch cyfr. Wartości spadków zapisane w modelu nie są zmieniane przez formatowanie.
- Po aktualizacji wybierz Aktualizuj plan (RSPLANUPDATE), aby odświeżyć opisy istniejącego rysunku. Wielkości można nadal ustawić przyciskiem Manipulatory.

Weryfikacja: testy obliczeniowe, migracji ustawień, formatowania, testy WPF z wielokrotnym zastosowaniem ustawień i testy aktualizatora. Zapis do natywnego DWG w BricsCADzie pozostaje niezweryfikowany. Zamknij wszystkie sesje BricsCAD przed instalacją.
