# ZK Drogi 0.61 — teren z Geoportalu

W Nawigatorze rozwiń drogę → **Teren → Pobierz z Geoportalu**. W pustym DWG przycisk jest obok wskazania osi. Polecenie: `RSGEOPORTAL`.

1. Wybierz zakres: zamknięta polilinia 2D albo pas wzdłuż aktywnej osi; podaj szerokość na każdą stronę.
2. Ustaw układ rysunku: PL-1992 / EPSG:2180 albo PL-2000, strefy 5–8. CAD X oznacza wschód, CAD Y północ. Rysunek musi być w metrach, w rzeczywistych współrzędnych. Układ lokalny wymaga wcześniejszego georeferencjonowania; nie zgadujemy strefy ani przesunięcia.
3. Wybierz PL-EVRF2007-NH lub PL-KRON86-NH i krok siatki 1, 2 albo 5 m. Domyślnie 5 m, aby ograniczyć liczbę trójkątów. Wybór układu wysokościowego pobiera odpowiedni model; nie przelicza wysokości istniejącej drogi.
4. Pobierz dane i zapisz **nowy** DWG terenu. Program tworzy powierzchnię z 3DFACE na warstwie `ZKD_NMT`, następnie dołącza DWG jako Xref w rzeczywistym położeniu. Nie obraca ani nie skaluje widoku.

Teren zostaje przypisany do aktywnej drogi dla przekrojów. Jeżeli pokrywa całą oś, odczytywany jest także profil terenu i odświeżany istniejący wykres profilu. Przy niepełnym pokryciu nie łączymy profilu przez luki; Xref pozostaje dostępny do przekrojów i skarp. W poleceniu skarpy można wskazać nowy Xref i warstwę `ZKD_NMT`.

Pobieranie i triangulacja działają w tle z postępem i anulowaniem. Dopiero po zakończeniu powstaje DWG i wstawienie Xrefa. Pobrane kafle są zapisywane lokalnie w `%LOCALAPPDATA%/ZKProjekt/Drogi/terrain-cache`; ponowne użycie nie wymaga pobierania tych samych danych. Oś i jej przesuwanie nie wywołują pobierania terenu. Cache nie odświeża sam danych po zmianach po stronie Geoportalu.

Obok DWG zapisany jest JSON: źródło, czas importu (nie data nalotu), nazwa, EPSG, układ wysokościowy, krok i zakres. Rozdzielczość siatki nie oznacza dokładności pomiarowej. Źródło: oficjalna usługa GUGiK WCS NMT, https://www.geoportal.gov.pl/pl/usluga/uslugi-pobierania-wcs/ .

Ograniczenia pierwszej wersji: milion próbek prostokąta pobierania i maksymalnie 300 000 trójkątów; przy większym zakresie zwiększ krok lub podziel teren. Granica powierzchni jest przybliżona siatką i próbkowaniem łuków zakresu, bez dokładnego docinania trójkątów na obrysie. Braki NMT nie są wypełniane. Źródłem jest raster NMT, bez dodatkowych linii nieciągłości z pomiaru. Wstawienie Xrefa i zapis DWG wykonywane są na wątku CAD po pobraniu; nie są anulowalne w trakcie zapisu.

Weryfikacja: 555 testów geometrii/polityk, okna WPF poza ekranem, kompilacja ze SDK BricsCAD V26. Transformację PL-1992/PL-2000 porównano z niezależną biblioteką PROJ. Rzeczywisty test usługi w obu układach wysokościowych: po 2080 próbek i 3626 trójkątów, połączenie dwóch kafli bez szczeliny. Natywnego przebiegu wyboru zakresu → zapis DWG → Xref w otwartym BricsCADzie jeszcze nie zweryfikowano.

