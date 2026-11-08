# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.37 — PPM i pojedyncza definicja skarpy
- Naprawa Sequence contains no elements przy PPM w profilu mającym wyłącznie niweletę drogi. PVI są podmieniane atomowo bez opróżniania kolekcji związanej z tabelą. Dotyczy też Cofnij i cofania błędnego przeciągnięcia.
- Usunięcie wewnętrznego manipulatora skarpy usuwa lokalną regułę: obowiązuje poprzednia proporcja do kolejnej etykiety. Dotyczy też wewnętrznych trójkątów procentowych. Granice początku/końca pozostają wymagane.
- Ponowne utworzenie nakładającej się skarpy z tego samego źródła i strony jest blokowane.
- Aktualizuj plan / Przelicz skarpy porządkuje wcześniejsze duplikaty: w części wspólnej obowiązuje najnowsza definicja, starsze niepokrywające się końce pozostają. Poprzednie definicje są archiwizowane w DWG, a ich wygenerowane powierzchnie usuwane według indeksów.
- Wygląd czytelniejszych manipulatorów jest osobną wizualizacją i nie został jeszcze wdrożony w tej wersji.

Po instalacji przy zamkniętym CAD wybierz Aktualizuj plan → Przelicz skarpy. Po usunięciu manipulatora nieaktualna powierzchnia jest ukrywana do jawnego przeliczenia.

332 testy obliczeniowe, 12 aktualizatora oraz testy rzeczywiście załadowanego, niewidocznego okna WPF przechodzi. Test starego Clear/Add odtwarza Sequence contains no elements dla jednej niwelety. Integracji nowych reguł z natywnym BricsCAD jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Wymagany BricsCAD V26 x64 i .NET Desktop Runtime 8.0.33+ z linii 8. Zamknij wszystkie sesje BricsCAD przed instalacją. Wersja: 0.37.
