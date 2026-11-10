# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.61 — teren z Geoportalu
- Nawigator → Teren → Pobierz z Geoportalu (`RSGEOPORTAL`). Zakres z zamkniętej polilinii albo pas wzdłuż aktywnej osi.
- PL-1992 i strefy PL-2000, wybór PL-EVRF2007-NH / PL-KRON86-NH, krok 1 / 2 / 5 m. Pobieranie w tle, anulowanie i lokalna pamięć podręczna.
- Osobny DWG z trójkątami 3DFACE, automatycznie podłączany jako Xref. Teren do przekrojów i skarp; profil terenu odczytywany przy pełnym pokryciu osi.
- 555 testów danych/geometrii, testy WPF poza ekranem oraz rzeczywiste pobieranie z GUGiK w obu układach wysokościowych. Natywnego zapisu DWG i wstawienia Xrefa w BricsCADzie jeszcze nie zweryfikowano. Zakresy duże: limit miliona próbek / 300 tys. trójkątów; zwiększ krok lub podziel zakres.
## 0.60 — wiele dróg w jednym DWG
- Dodaj drogę rejestruje kolejną niezależną oś w tym samym DWG. Każda ma własne ustawienia, krawędzie, profil i rowy, model, skarpy oraz przekroje. Rozwinięcie drogi wybiera kontekst pracy.
- Nowy nawigator z rozwijanymi sekcjami, podpisem Vdp, oznaczeniem aktywnej drogi, bursztynowymi znacznikami aktualności i czerwonymi błędami. Starsze wyniki wymagają jednokrotnego przeliczenia do zweryfikowania stanu.
- Indeksy wyników i warstwy modeli są rozdzielone według osi. Pełna przebudowa jednej drogi nie powinna usuwać wyników pozostałych. Testy danych i okna przechodzą; natywnego przebiegu trzech dróg z 3D w BricsCADzie jeszcze nie zweryfikowano.
- Na wstążce ZK Drogi zostaje jeden duży przycisk Nawigator z ikoną drzewa. Okno projektu zawiera skróty do narzędzi i aktualizację programu; bez nazwy pliku, z podpisem Vdp przy prędkości.
- Przekroje: teren, projekt, szerokości i spadki oraz pasma rzędnych projektowanych/istniejących, różnic i odsunięć od osi. Jednakowa skala pionu i poziomu, domyślnie 1:100. Odśwież przekroje przebudowuje istniejące widoki.
- Wąskie osobne okno: oś, krawędzie, profil i rowy, model 3D, skarpy oraz przekroje. Otwórz Nawigator projektu na wstążce lub RSNAVIGATOR. Rozwiń sekcję, aby wybrać polecenie. Drzewo odświeża się po poleceniach i zmianie DWG bez przeliczania modelu.
- Dodaj rów: wybierz Lewy/Prawy, potem wskaż początek i koniec w edytorze przyciskami CAD albo profil. Bez wpisywania kilometraży w wierszu poleceń. CAD odczytuje kilometraż przez rzut punktu na oś; anulowanie zachowuje dane.
- Pola kilometrażu, tabela i uchwyty rowu nie pozwalają wyjść poza rzeczywisty zakres osi z DWG. Zaokrąglenie końcowego kilometrażu do trzech miejsc nie wywołuje fałszywego błędu.
- Poprawione przenoszenie tekstu po zmianie geometrii. Nadmiernie odsunięte napisy wracają przy symbol po odświeżeniu planu/skarp; małe ręczne przesunięcia pozostają zachowane.
- Dodaj rów: wybierz L/P i zakres kilometrażu, ustaw rzędne w edytorze profilu, następnie Przelicz skarpy.
- W zakresie niwelety: skarpa od pobocza do rzędnej dna, poziome dno 0,50 m i przeciwskarpa do terenu z Xrefa. Poza zakresem zwykłe dowiązanie do terenu.
- Szerokość dna i proporcja przeciwskarpy są edytowalne. Przebudowa zastępuje poprzednie powierzchnie; przekroje korzystają z tej samej geometrii.
- Geometria osi otwiera okno od razu, bez wskazywania punktu na rysunku. Strzałki przełączają wybrany W (wierzchołek).
- U góry domyślnie włączone „Przybliż do W”: przełączenie W pokazuje jego okolicę wraz z łukiem i klotoidami w bieżącej rzutni planu. Przełącznik można wyłączyć.
- Niezależne przełączniki dla promienia, L₁, L₂, przechyłki oraz ramp wejściowej i wyjściowej. Wartości ręczne pozostają zachowane, tryby zapisują się przy danym PI w DWG.
- Automatyczny dobór przechyłki z R i prędkości zamiast stałego 5%; zachowanie daszka tam, gdzie pozwalają na to tabela, klasa i szerokość jezdni. Automatyczne rampy z kontrolą dodatkowych pochyleń krawędzi.
- Stare ustawienia pozostają ręczne — zaznacz Auto przy parametrach, które program ma dobierać. Nowe ustawienia ramp domyślnie korzystają z automatyki. To kontrola obsługiwanych warunków WR-D-22-2, nie pełny audyt projektu.
- Sekcja „Przekroje”: Wstaw przekrój oraz Odśwież przekroje. Wskaż miejsce na osi, potem punkt wstawienia przekroju w DWG. Powstaje też edytowalna linia na planie.
- Wstawienie od razu rysuje przekrój z rzędnymi, szerokościami i pochyleniami, również przy wyłączonej automatycznej aktualizacji. Bez przebudowy modelu 3D.
- Napisy spadków mają mniejszy domyślny rozmiar i zapis bez zbędnych zer: -2%, -8%, 3.5%. Istniejące domyślne ustawienia są migrowane; własne rozmiary pozostają zachowane. Po aktualizacji odśwież plan.
- Zastosowanie przechyłki pozostawia okno ramp otwarte. Można wykonywać kolejne korekty i ponownie je zapisywać.
- Wąskie okno geometrii z przyciskiem Proponuj oraz osobne okno Przechyłka i rampy.
- Dobór R i klotoid dla prędkości osi; kontrola tablicowych promieni, przyrostu przyspieszenia, kąta klotoid i miejsca między PI. Propozycja dla przechyłki 5%; widoczność i warunki lokalne wymagają osobnej oceny.
- Sterowanie długością rampy albo |Δi| krawędzi L/P. Wynikowe pochylenia krawędzi uwzględniają niweletę, łuki pionowe i zmienne szerokości pasa.
- Zapis spadków jezdni i poboczy na planie; automatyczne etykiety powiązane z łukiem, ochrona ręcznych korekt i usuniętych manipulatorów.
- Najpierw zastosuj geometrię, potem otwórz rampy. W tej wersji obrót odbywa się wokół osi drogi. Model 3D i skarpy pozostają do osobnego przeliczenia.

530 testów obliczeniowych, testy okien WPF i 12 testów aktualizatora przechodzą. Kompilacja bez ostrzeżeń i błędów. Natywny zapis, przebudowa i nowe przybliżanie rzutni w BricsCADzie nie zostały jeszcze zweryfikowane. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.60.










