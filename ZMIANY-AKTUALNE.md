# ZK Drogi 0.38 — manipulatory na pasmach

Wdrożenie wybranego wariantu: trójkąt dla spadku procentowego i wypełniona strzałka dla proporcji skarpy.

- Teksty REGULA / SKARPA są wielowierszowymi atrybutami bloków z natywną maską tła, zależną od tła CAD (BackgroundFill + UseBackgroundColor). Maska jest częścią napisu i podąża za nim. Linia od symbolu do napisu aktualizuje się po jego odsunięciu.
- Atrybut ma LockPositionInBlock=false. Blok ma uchwyt położenia symbolu, a napis osobny uchwyt atrybutu. Przesunięcie napisu nie zmienia kilometrażu ani wartości; przesunięcie symbolu zmienia kilometraż wewnątrz zakresu.
- Strzałka skarpy znajduje się w środku jej pasma pomiędzy źródłem a dowiązaniem do terenu. Ma wypełniony grot, kolor żółty i widoczną grubość. Przy wykopie kierunek wskazuje niższą krawędź drogi, przy nasypie — niższy teren.
- Domyślne położenie napisu skarpy jest liczone od środka pasma. Ręczne odsunięcie tekstu zapisuje się osobno. Zwykły ruch bloku i jego atrybutu nie jest błędnie rozpoznawany jako ręczna zmiana odsunięcia tekstu.
- Rozpoznawanie przesunięcia symbolu odbywa się w XY; wysokość adnotacji nie zmienia kilometrażu. Oś/krawędź pozostaje źródłem odniesienia mimo przesunięcia punktu wstawienia strzałki na środek skarpy.
- Adnotacje są podnoszone ponad wysokość końców opisywanego pasa i przesuwane na wierzch kolejności rysowania, aby nie chowały się pod powierzchnią 3D w widoku z góry.
- Przycisk „Manipulatory” (`RSMANIPULATORS`) pozwala ustawić skalę opisów, wysokość tekstu i długość strzałki w mm na wydruku. Rysunek jest prowadzony w metrach. Domyślnie 1:1000, tekst 2,5 mm i symbol 3,5 mm (odpowiednio 2,5 m i 3,5 m w modelu). Jest to własna skala opisów, nie automatycznie adnotatywny blok CAD.
- Poprawione pierwsze położenie napisu procentowego — początek układu nie jest doliczany drugi raz.

## Po aktualizacji
Zamknij wszystkie sesje BricsCAD przed instalacją. Następnie wybierz Aktualizuj plan, a potem Przelicz skarpy, aby wyznaczyć rzeczywistą szerokość i środek skarp. Dostosuj wielkość w przycisku Manipulatory do skali opracowania.

Zaznacz blok. Uchwytem symbolu przesuwasz jego kilometraż; osobnym uchwytem napisu odsuwasz sam tekst i jego maskę. Początek/koniec skarpy pozostają granicami zakresu — zmieniasz je parametrami, nie przesuwaniem granicznego uchwytu. Po zmianie kilometrażu/proporcji powierzchnię skarpy przelicz jawnie. Samo odsunięcie napisu nie wymaga przeliczania terenu.

Zachowane są poprawki 0.37: PPM profilu, dziedziczenie proporcji po usunięciu wewnętrznego manipulatora i brak nakładających się skarp tego samego źródła/strony.

## Weryfikacja
Kompilacja względem API BricsCAD V26, testy obliczeń wielkości/położeń, rozdzielenia ruchu tekstu i symbolu oraz dotychczasowe testy projektu. Rzeczywiste właściwości MTextAttribute/BackgroundFill/LockPositionInBlock sprawdzono w lokalnym API. Wyglądu maski i zachowania uchwytów tej wersji nie zweryfikowano jeszcze wewnątrz natywnego BricsCAD-a.

`UpdateMTextAttribute` i niezależne położenie atrybutu: [Bricsys .NET API](https://developer.bricsys.com/bricscad/help/en_US/V25/DevRef/source/html/938961a5-76b6-ed3a-2e2e-d50c220a2727.htm).
