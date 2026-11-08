# ZK Drogi 0.34 — wspólny Dodaj spadek, strzałki i rzadsze skarpy

## Jeden przycisk
Dodaj spadek (RSLABEL) obsługuje elementy drogi i skarpy.
- Wskaż powierzchnię skarpy albo jej strzałkę: wskaż miejsce na planie i podaj n w proporcji 1:n, np. 2 dla 1:2. Nie trzeba wcześniej mieć widocznego manipulatora.
- Można wskazać polilinię źródłową, np. pobocze. Jeżeli ma skarpę, wybierz kontekst Skarpa (domyślny); Element oznacza zwykłą zależność procentową elementu drogi. Przy kilku skarpach tego samego źródła program podaje listę zakresów do wyboru.
- Nowy manipulator punktowy działa od swojego kilometrażu do następnej istniejącej granicy. Nie usuwa dalszych reguł.
- Dla zamkniętego odcinka wybierz opcję Odcinek przy pytaniu o miejsce manipulatora, wskaż początek i koniec, a następnie n. Za końcem wraca wcześniejsza proporcja.
- Edytuj spadek rozpoznaje również strzałkę lub powierzchnię skarpy i zmienia jej aktywny przedział. Nadal obsługuje dotychczasowe procentowe etykiety drogi.
- Stare polecenie RSDAYLIGHTSLOPE pozostaje do zgodności, ale osobny przycisk Zmień proporcję na odcinku został usunięty z wstążki.

## Symbole
Proporcjonalne pochylenie 1:n: strzałka z osobno przesuwanym tekstem. Po przeliczeniu skarpy kierunek wskazuje obniżenie: na zewnątrz w nasypie, do drogi w wykopie. Dotychczasowe procentowe trójkąty pozostają bez zmian. Istniejące bloki skarp są przebudowywane, bez tworzenia drugiego symbolu na tym samym węźle.

## Siatka
Skarpa nie przejmuje wszystkich wierzchołków technicznej aproksymacji łuku ani próbek krawędzi. Własny krok, np. 5 m, obowiązuje pomiędzy rzeczywistymi granicami geometrii, zmianami profilu, reguł i ręcznych szerokości. Rozstaw jest wyrównywany w każdym przedziale, aby unikać bardzo krótkiego ostatniego paska. Rzeczywiste bliskie granice mogą nadal wymagać bliskich przekrojów. Nie dodajemy przekrojów z reguł elementów niezwiązanych ze źródłem skarpy.
Automatyczne próbki poszerzenia nie są wszystkie punktami obowiązkowymi modelu; zachowane są granice przejść i korekty ręczne. W poboczu rozpoznawana jest względna szerokość do rodzica, aby nie dziedziczyło całej technicznej siatki poszerzeń.
Krok skarpy: wskaż jej powierzchnię, źródło lub strzałkę i podaj nowy krok. Wybrana skarpa zostaje przeliczona. Przelicz skarpy odświeża wszystkie zapisane skarpy.
Po aktualizacji pierwszy Model 3D przebuduje stary model drogi według nowego algorytmu, nawet jeżeli wcześniej był oznaczony jako aktualny. Istniejącą skarpę odśwież przyciskiem Przelicz skarpy, aby zastąpić starą gęstą powierzchnię i poprawnie ustalić kierunek strzałek.

## Instalacja i weryfikacja
Wersja 0.34 zawiera poprawki poprzednich wydań, w tym działające w teście WPF okno aktualizacji. Zamknij cały CAD przed instalacją. Zachowaj kopię DWG. Po uruchomieniu wybierz Aktualizuj plan, Model 3D, Przelicz skarpy.
278 sprawdzeń geometrii/logiki przechodzi: nowe przypadki dotyczą niezależnej regularnej siatki, zachowania granic, stałej szerokości pobocza względem zagęszczonego rodzica, zachowania ręcznego załamania, dodawania pojedynczej reguły i otwartej strzałki zamiast trójkąta. Nowe trasy wyboru, wygląd strzałek, transakcje i przebudowa powierzchni na DWG użytkownika nie zostały jeszcze zweryfikowane natywnie. Zrzut użytkownika potwierdzał utworzenie skarpy w poprzednim wydaniu, ale nie nową gęstość i nowe interakcje.

Tag v0.34, instalator ZKDrogi-Setup-0.34.exe. Moduł RoadSketch.Spatial30 i log startup-30.log pozostają zgodne z dotychczasowymi rysunkami.
