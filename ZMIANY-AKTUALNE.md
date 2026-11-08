# ZK Drogi 0.32 — rzutnia, wymiary i podział modelu

- Utwórz / odśwież 3D nie wywołuje już zmiany kierunku, targetu, zoomu, środka ani skręcenia bieżącej rzutni. Przelicza model i włącza jego warstwy. Przycisk Wróć do planu pozostaje jawną zmianą widoku.
- Wymiary szerokości mają własne nadpisania: skala 1, tekst 0,25 m, strzałki 0,15 m, odsunięcie 0,60 m, wystawanie linii pomocniczej 0,12 m i zapis do 0,01 m. Nie dziedziczą ogromnych rozmiarów z bieżącego stylu DWG. Styl użytkownika nie jest globalnie zmieniany.
- Punkty aproksymacji klotoidy/łuku w źródłowej polilinii i techniczne próbki wygenerowanych krawędzi nie są wszystkie traktowane jako obowiązkowe przekroje modelu. Zachowane są punkty charakterystyczne geometrii, reguł, szerokości, profilu i zakresów elementów. Podział modelu pozostaje zależny od maksymalnego kroku i tolerancji cięciwy; bardziej wymagająca geometria może zagęścić go dodatkowo. Kontrolne węzły szerokości, w tym poszerzeń, są zachowywane.
- Nowy przycisk Model i wymiary w grupie Model 3D pozwala ustawić powyższe parametry. Zapis rozmiaru wymiarów odświeża opisy, a zmiana próbkowania oznacza model do przebudowy na żądanie.
- Zawiera poprawkę 0.31: forceOpenOnLockedLayer tylko dla własnych starych obiektów kolorowej reprezentacji osi. Rzeczywisty log potwierdził tę przyczynę błędu po ruchu PI i przy uruchomieniu Skarpy do terenu.

Zamknij cały BricsCAD, zainstaluj 0.32, otwórz kopię DWG i wybierz Aktualizuj plan, a potem Utwórz / odśwież 3D. Jeśli chcesz rzadszej siatki, ustaw krok i tolerancję w Model i wymiary. To ustawienia modelu wynikowego, a nie dokładności osi projektowej.

Weryfikacja obejmuje kompilację przeciw BricsCAD V26 i testy geometryczne. Nowe testy próbkowania sprawdzają zachowanie granic, krok maksymalny, błąd cięciwy, brak konieczności dziedziczenia gęstej siatki widoku osi oraz rzeczywiste zmniejszenie liczby próbek po zwiększeniu tolerancji. Nie potwierdzono natywnie na rysunku użytkownika zachowania widoku, wyglądu wymiarów i naprawy blokady warstwy. Szczegółowy opis przebiegu pracy: wersja 0.30.

Tag GitHub v0.32, instalator ZKDrogi-Setup-0.32.exe. Moduł RoadSketch.Spatial30, log startup-30.log.
