# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.81 — reguły sąsiedztwa i ciągłość krawędzi
- Warstwy rozpoznają typy, osobne reguły określają spadek / różnicę Z między najbliższymi elementami od osi na zewnątrz.
- Ustawiana tolerancja ciągłości (domyślnie 0,25 m), logiczne ciągi wielu polilinii, brak zbędnych automatycznych etykiet na ich stykach i krótkie łączniki modelu drogi 3D.
- Ustawienia: Domyślne reguły → Mapuj krawędzie → odśwież 3D / skarpy. Ręczne wartości pozostają chronione. 661 testów geometrii, testy WPF i 13 testów aktualizatora. Bez pełnej próby na aktualnym DWG użytkownika.

## 0.80 — mapowanie i punkty szerokości
- Nowe okno analizy: odniesienia według zakresu i strony osi, widoczne listy wyboru i jawne częściowe pokrycie.
- Naprawiono kolizję bliskich punktów ze wspólnym znacznikiem wierzchołka po przesunięciu osi. Dokładniejsza diagnostyka szerokości.
- 635 testów geometrii i testy WPF na izolowanym pulpicie. Bez pełnej próby na aktualnym DWG użytkownika.

## 0.79 — granice próbkowania modelu 3D
- Poprawiono rekurencję na niemal identycznych kilometrażach, przycięcie do rzeczywistego zakresu oraz wybór jednej strony granicy reguł. Zachowane są prawdziwe skoki wysokości i zabezpieczenia próbkowania.
- Scalanie dodatkowych bliskich węzłów zapobiega nieprawidłowej siatce szerokości. 626 testów; pierwszy model wymaga pełnego przeliczenia. Bez pełnej próby na żywym DWG.

## 0.78 — postęp mapowania krawędzi
- Jedna kompaktowa karta dla skanowania DWG, doboru odniesień, zapisu i symboli; opóźnienie 0,4 s, rzeczywiste liczniki etapów i Ukryj do końca operacji.
- Analiza warstw i automatyczne rozpoznawanie również mają postęp. RSENGINESTATUS podaje faktyczną wersję. Testy karty na odizolowanym pulpicie przeszły; bez pełnej próby mapowania z kartą w CAD.

## 0.77 — skarpa tylko przy parze jezdnia + pobocze
- Wymaga jezdni o określonej wysokości i zewnętrznego pobocza z wysokością w tym samym zakresie, osobno L/P. Sama jezdnia lub samo pobocze nie tworzą skarpy.
- Luki nie są mostkowane; przeliczenie usuwa nieaktualną powierzchnię, zachowując definicje i ręczne proporcje. 617 testów; bez pełnej próby w uruchomionym CAD.

## 0.76 — odwrotny kierunek pobocza
- Naprawiono wycofywanie mapowania przy rysowaniu opisu luki na poboczu w odwrotnym kierunku. Opis korzysta z aktualnej geometrii źródła bez sortowania wierzchołków.
- 594 testy, w tym dokładne kilometraże 5CABA z logu. Pełnego ponownego mapowania w CAD jeszcze nie wykonano.

## 0.75 — dokładna granica odniesień
- Zawiera mapowanie poboczy z 0.74 oraz poprawkę lewej granicy próbki na styku dwóch jezdni. 588 testów przechodzi.

## 0.74 — pobocza i odcinkowe odniesienia
- Pobocze może korzystać z kolejnych polilinii jezdni. Tolerancja końców 1 m; bez skracania źródła. Podążanie i wysokości uwzględniają zmianę odniesienia.
- Ponowne Mapuj krawędzie zachowuje istniejące spadki. Luki i niejednoznaczności są opisane na planie. 587 testów; pełna próba w CAD pozostaje do weryfikacji.

## 0.73 — niezależny edytor profilu
- Niemodalne okno niwelety drogi i rowów. Zastosuj zapisuje dane przez osobne polecenie CAD bez zamykania edytora. Zachowuje kopię roboczą po błędzie.
- Odczyt kilometrażu z modelu, powiązanie z DWG i ochrona przed nadpisaniem po zmianie osi. Testy WPF na osobnym pulpicie; bez próby równoległej pracy w uruchomionym BricsCAD.

## 0.72 — kompaktowy postęp
- Karta odświeżania planu, przebudowy 3D i skarp, opóźnienie 0,4 s, faktyczne etapy i liczniki. Ukryj dla automatyki; Anuluj dla przebudów z transakcją.
- Testy karty na osobnym pulpicie Windows. Bez próby przebudowy w żywym CAD; API CAD pozostaje na głównym wątku.

## 0.71 — skarpy od wszystkich poboczy
- Przycisk Skarpy od poboczy pyta tylko o proporcję 1:n (domyślnie 1:1,5). Sam bierze przypisane pobocza, ich zakresy i teren drogi oraz odkłada skarpy na zewnątrz od osi.
- Zachowuje istniejące manipulatory i ręczne proporcje. Uzupełnia brakujące zakresy bez drugiej skarpy na tym samym źródle i stronie. Szczegółowy przebieg pozostaje jako RSDAYLIGHTMANUAL.
- 574 testy geometrii/polityk. Pełnego utworzenia kompletu skarp w CAD po zmianie jeszcze nie wykonano.

## 0.70 — przesuwanie osi uchwytami
- Ruch uchwytu zachowuje zapisane R i obie klotoidy; nie uruchamia ponownego doboru wszystkich łuków. Rzeczywista kolizja lub brak miejsca nadal odrzuca zmianę.
- 565 testów przechodzi. Na kopii parametrów aktualnej osi (9 wierzchołków, 7 krzywych) wszystkie 36 przesunięć o 1 m przeszło obliczeniowo bez zmiany R/L. Pełnego ruchu i podążania krawędzi w CAD po tej poprawce jeszcze nie wykonano.

## 0.69 — niwelety w Nawigatorze
- Profil pokazuje licznik i wszystkie zapisane niwelety, także niweletę drogi. Każda ma zakres kilometrażu, oznaczenie strony rowu i własny przycisk edycji.
- Test okna poza ekranem obejmuje drogę i dwa rowy oraz wybór właściwej niwelety.

## 0.68 — model 3D z zapisanej geometrii osi
- Model nie uruchamia ponownego doboru R i klotoid, jeżeli nie edytowano wierzchołków osi. Korzysta z zapisanego przebiegu, niwelety i spadków.
- Nowa edycja punktów nadal jest rozwiązywana i sprawdzana. Poprawka nie potwierdza zgodności projektu z Vdp. Pełnej budowy w CAD po zmianie jeszcze nie wykonano.

## 0.67 — symbole spadków po mapowaniu
- Mapuj krawędzie odtwarza trójkątne manipulatory również dla już przypisanych polilinii, bez wymuszania automatycznego przeliczenia osi. Ukrywa pomocnicze DBText; zachowuje ręczne spadki.
- Naprawia etap wyświetlania. Niezależny błąd doboru geometrii osi może nadal blokować budowę 3D. Pełnej próby w CAD po poprawce jeszcze nie wykonano.

## 0.66 — wadliwy fragment nie wycofuje mapowania
- Powtarzające się/cofające stacje są sprawdzane przed dodaniem wiązania. Nowa wadliwa polilinia jest pomijana z podaniem przyczyny; pozostałe poprawne elementy są przypisywane.
- Przypadek końca osi 3014.8864182382931 objęto regresją. 561 testów przechodzi. Źródło pozostaje bez sortowania, przycinania i sztucznego rozdzielania kilometraży.

## 0.65 — ikona terenu
- Teren w Nawigatorze ma ikonę siatki triangulacji, odrębną od geometrii osi.

## 0.64 — mapowanie krawędzi z warstw
- Nawigator → Krawędzie i elementy → Mapuj krawędzie: istniejące polilinie są przypisywane według reguł nazw warstw i odniesień. Działa także bez automatycznego wykrywania nowych polilinii.
- Zachowuje istniejące przypisania i ręczne spadki. Nie przejmuje geometrii innych dróg. Niejednoznaczne odniesienia rozstrzyga tabela Wybierz odniesienia.
- 555 istniejących testów geometrii i polityk przechodzi. Pełnego przebiegu nowego przycisku w CAD jeszcze nie sprawdzono.

## 0.63 — zapis terenu z Geoportalu
- Naprawiono eKeyNotFound przy tworzeniu DWG terenu: 3DFACE otrzymują warstwę przez identyfikator w docelowej bazie. Wcześniej CAD szukał nazwy warstwy w bieżącym rysunku.
- Ponów import tego samego zakresu — poprawnie pobrane kafle są w pamięci podręcznej. Pełna próba zapisu w CAD po poprawce pozostaje do wykonania.

## 0.62 — przesuwanie Nawigatora
- Okno można przeciągać za cały górny pasek, również za puste miejsce obok napisu. Przycisk zamknięcia pozostaje niezależny.

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




















