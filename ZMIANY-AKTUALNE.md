# ZK Drogi 0.30 — prosty przebieg pracy

## 1. Oś
W pustym DWG narysuj otwartą polilinię, a następnie Wskaż oś. Kierunek polilinii wyznacza rosnący kilometraż. Proste są czerwone, łuki żółte, a rozpoznane klotoidy pomarańczowe; wzór kreska-kropka. Rysowana jest powiązana reprezentacja na zablokowanej warstwie ZKD_GEOMETRIA_OSI. Źródło pozostaje edytowalne przez Uchwyty osi. Dla łuków istniejącej polilinii zachowane są oryginalne bulge; krzywe przejściowe są identyfikowane z parametrów programu, nie odgadywane z dowolnej gęstej polilinii. Geometria osi służy do edycji PI, R i L. Nowa reprezentacja jest odświeżana po zmianie źródła, nie po każdej zmianie spadku.

## 2. Krawędzie i spadki
Domyślne reguły otwierają małe okno z wartościami oś → jezdnia -2% i jezdnia → pobocze -8%. W nowym projekcie są to wartości początkowe; w istniejącym DWG zachowujemy jego ustawienia, które można tu zmienić. Nowe wartości nie zmieniają już istniejących reguł wysokościowych.
Utwórz krawędzie: szerokości lewa/prawa, spadek jezdni, opcjonalne pobocza z szerokością i spadkiem. Każdy element dostaje trójkąty na początku i końcu. Tekst można odsuwać niezależnie. Dodaj spadek tworzy kolejną regułę kilometrażową. Model 3D nie jest przebudowywany przy każdym ruchu. Poszerzenia WR-D są opcjonalne; bez wybranego pojazdu początkowo wyłączone.

## 3. Profil
Utwórz profil: wskazujesz położenie niwelety, edytujesz jej polilinię. Skala pionowa x10, początkowa wysokość pochodzi z parametrów osi. Nie jest to automatyczny profil terenu istniejącego.

## 4. Model 3D
Utwórz / odśwież 3D przelicza geometrię wysokościową osi i elementów. Wróć do planu przywraca widok do edycji.

## 5. Skarpy
Skarpa do terenu: źródłowa polilinia (np. pobocze), początek i koniec zakresu, Xref terenu oraz jego warstwa 3DFACE, proporcja 1:n (domyślnie 1:1,5), krok, zasięg i strona. Powstaje powierzchnia oraz blokowe trójkąty z atrybutem SKARPA na początku i końcu zakresu. Układy i jednostki muszą być zgodne. Teren nadal musi zawierać 3DFACE, a nie raster lub obiekt proxy.
Zmień proporcję na odcinku: wskaż trójkąt skarpy, dwa punkty zakresu na planie i np. 1:2. Na tym przedziale działa nowa wartość, a za końcem powraca wcześniejsza. Powstają manipulatory granic. Wewnętrzny trójkąt można przesunąć uchwytem wzdłuż źródła (bez przekraczania sąsiadów); zmienia kilometraż granicy. Manipulatory końców są kotwami zakresu i wracają na miejsce przy przeciąganiu. Atrybut SKARPA przyjmuje 1:2 lub 2; można osobno przesuwać tekst. Edycja wartości końcowego manipulatora zmienia ostatni aktywny przedział; edycja początkowego — pierwszy. Dodatnia wartość oznacza proporcję pion:poziom, nie procent.
Po edycji atrybutu/uchwytu użyj Przelicz skarpy. Nie wykonujemy ciężkiego odczytu terenu po każdym ruchu. Dodanie przedziału przyciskiem przelicza wybraną skarpę od razu. Przejście proporcji jest skokowe, bez interpolacji; w przekroju granicznym tworzone są dwie strony bez sztucznej powierzchni łączącej skok. Braki dowiązania nie są mostkowane powierzchnią.

## Program
Aktualizacja programu otwiera menedżer ustawień/aktualizacji z repozytorium kidznok/ZK-Drogi. Na głównej wstążce pozostają tylko opisane etapy. Inne polecenia są zachowane do zgodności starszych DWG, ale nie zajmują wstążki.

## Instalacja i weryfikacja
Zamknij cały BricsCAD i uruchom instalator 0.30. Nie przeładowuj DLL do starej sesji. Przed próbą zachowaj kopię DWG. Nowy moduł RoadSketch.Spatial30 ma odrębną nazwę od starego silnika. Zachowuje odczyt zapisanych danych. Log: %LOCALAPPDATA%/ZKProjekt/Drogi/logs/startup-30.log.
Kompilacja przeciw SDK BricsCAD V26 bez błędów. Testy obejmują reguły przedziałowe, powrót poprzedniej proporcji, przedziały zagnieżdżone, zapis identyfikatorów oraz kolejność i kompletność nowej wstążki. Nie potwierdzono jeszcze natywnie nowych bloków, stylu linii, uchwytów i Undo w BricsCADzie. Wcześniejsza awaria tworzenia poboczy nadal wymaga weryfikacji na rysunku użytkownika; przebudowa nie jest dowodem usunięcia jej przyczyny.


