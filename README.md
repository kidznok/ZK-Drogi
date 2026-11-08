# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.34
- Wspólny Dodaj spadek dla drogi i skarpy: wybierz powierzchnię, źródło lub manipulator. Nie trzeba wcześniej mieć widocznego symbolu skarpy.
- Proporcja 1:n oznaczana strzałką, procenty nadal trójkątem. Edytuj spadek obsługuje oba typy.
- Dodanie punktu zmienia proporcję do następnej granicy; opcja Odcinek ustawia zamknięty przedział.
- Własny krok skarpy i polecenie Krok skarpy do zmiany istniejącego modelu. Techniczne próbki osi i automatycznych poszerzeń nie są wszystkimi obowiązkowymi przekrojami.
- Zawiera poprawki wcześniejszych wydań: okno aktualizacji, blokada warstwy osi, zachowanie rzutni i małe wymiary.

Po instalacji przy zamkniętym CAD: Aktualizuj plan → Model 3D → Przelicz skarpy, aby zastąpić stare gęste powierzchnie. Zachowaj kopię DWG. Wymagany .NET Desktop Runtime 8.0.33+ z linii 8; instalator niepodpisany cyfrowo.

278 testów obliczeniowych i 12 aktualizatora przechodzi. Nowych interakcji CAD nie potwierdzono natywnie na DWG użytkownika. Nie wykonano benchmarku setek polilinii/10 km; nie deklarujemy gotowości produkcyjnej dla tej skali. Szczegóły: ZMIANY-AKTUALNE.md.

## Publikowanie
Numerowany EXE w main uruchamia workflow: kontrola ProductVersion, SHA-256, stabilne wydanie Latest. Numeracja 0.34, 0.35 itd. Nie zmieniaj samej nazwy poprzedniego EXE.
