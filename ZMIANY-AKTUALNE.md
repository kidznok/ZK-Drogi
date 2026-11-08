# ZK Drogi 0.36 — zapis profilu, PPM i czytelna geometria

## Naprawa „Zastosuj i aktualizuj DWG”
Log użytkownika wskazywał `eDegenerateGeometry` w `Polyline.RemoveVertexAt` podczas zapisu profilu. Stary kod usuwał wszystkie punkty istniejącego profilu przed ich ponownym wstawieniem. Teraz zmniejsza liczbę wierzchołków tylko do docelowej liczby (minimum dwa), dopisuje brakujące i aktualizuje współrzędne/bulge. Zachowuje uchwyt profilu.

Zapis pozostaje transakcyjny. Jeżeli wystąpi inny błąd CAD, transakcja jest cofana, a edytor otwiera się ponownie z zachowanymi PVI i czytelnym błędem zamiast porzucać zmiany.

## Dodawanie załomu pod PPM
Kliknij prawym przyciskiem na aktywnej niwelecie → „Dodaj załom tutaj”. Nowy PVI ma kilometraż kliknięcia i rzędną z rzeczywistego profilu. Na łuku kołowym program dzieli krzywą na dwa styczne łuki o tym samym R i dodaje punkt na krzywej; to wymaga dodatkowych PVI stycznych, ale zachowuje dotychczasowy kształt. Cofnij przywraca całą operację. Kliknięcie w istniejący PVI wybiera go zamiast tworzyć duplikat.

## Siatka i kolor łuków
- Okrągłe, adaptacyjne kroki osi X/Z (np. 20 m i 1 m), niezależne od sztucznego podziału widoku na osiem części.
- Kilometraż 0+020, 0+040 itd., opis kroku siatki i rzeczywistego powiększenia pionowego.
- Pion automatyczny lub ×5 / ×10 / ×20. Przy pełnym widoku stałe powiększenie dopasowuje zakres X tak, aby pokazać cały profil. Kółko myszy zbliża, Shift+kółko przesuwa, „Cały profil” przywraca zakres.
- Łuki pionowe są żółte, z poprzecznymi znacznikami i opisami PŁ/KŁ. Dotyczy edytora i wynikowego profilu w DWG. Odcinki proste zachowują kolor niwelety.

## Jak dodać rów
Narysuj otwartą polilinię w planie → „Dodaj rów” (`RSADDDITCH`) → wskaż polilinię, odniesienie i nazwę np. Rów L → otwórz „Edytor niwelety” i wybierz ten rów z listy. Niweleta rowu jest niezależna od drogi.

## Weryfikacja i zakres
Testy obejmują zachowanie próbek profilu przy wielokrotnych zmianach liczby wierzchołków z ograniczeniem minimum dwóch, dokładność podziału łuków, regularne podziałki, PPM na rzeczywistych kontrolkach WPF, powiększenie pionowe oraz żółte znaczniki PŁ/KŁ. To nie zastępuje testu zapisu w natywnym BricsCAD V26; nowej wersji nie sprawdzono jeszcze wewnątrz CAD. Błąd wersji 0.35 potwierdzono logiem użytkownika.

Profil DWG aktualizuje się po Zastosuj. Model 3D i skarpy wymagają własnego jawnego przeliczenia. Teren w profilu jest próbkowanym zapisem z Xrefa; po zmianie osi/Xrefa pobierz go ponownie. Łuki pionowe są kołowe, bez parabol i kontroli normowej.

Zamknij wszystkie sesje BricsCAD przed instalacją. Numer produktu: 0.36.
