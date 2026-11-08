# ZK Drogi 0.37 — PPM bez utraty wykresu

Naprawa błędu „Sequence contains no elements” po dodaniu załomu prawym przyciskiem w edytorze niwelety.

Przyczyna: kod najpierw opróżniał kolekcję PVI powiązaną z tabelą, następnie dopisywał punkty. WPF mógł odświeżyć zaznaczenie i wykres w środku tej operacji. Dla jedynej niwelety dane były chwilowo puste; wyjątek przerywał dodawanie i pozostawiał pusty wykres.

Teraz nowy, sprawdzony zestaw PVI jest budowany poza tabelą i podmieniany jednorazowo. Ta sama poprawka obejmuje Cofnij i przywracanie punktów po nieprawidłowym przeciągnięciu. Odświeżanie ignoruje stan przejściowy i zawsze przywraca flagę blokady zdarzeń.

Test regresji obejmuje jedną niweletę drogi (bez rowów), prawy przycisk, zdarzenia powiązanej kolekcji oraz rzeczywiście załadowane, niewidoczne okno WPF. Osobny kontrolowany test starego Clear/Add odtwarza błąd. Dotychczasowe testy kilku niwelet nie obejmowały przypadku jedynej pustej kolekcji.

Zachowane funkcje 0.36: naprawa zapisu do DWG, regularna siatka, PPM, żółte łuki pionowe z PŁ/KŁ i powiększenie pionowe.

Nie dodano nowych stylów manipulatorów skarp — ich wizualizacja jest osobną propozycją. Integracji wersji 0.37 w natywnym BricsCAD nie zweryfikowano; sprawdzono działanie okna WPF i obliczenia. Zamknij wszystkie sesje CAD przed instalacją.

## Usuwanie manipulatorów i pojedyncza skarpa
- Usunięcie wewnętrznego manipulatora skarpy usuwa jego regułę. Do następnej etykiety obowiązuje poprzednia proporcja. Późniejsze manipulatory pozostają bez zmian. Początek i koniec pozostają wymaganymi granicami zakresu (na początku bez poprzedniej etykiety obowiązuje bazowa proporcja).
- Usunięcie wewnętrznego trójkąta procentowego usuwa powiązaną regułę wysokościową; poprzednia etykieta przejmuje zakres. Reguła początkowa pozostaje obowiązkowa.
- Ponowne „Skarpa do terenu” dla nakładającego się zakresu tego samego źródła i strony jest blokowane. Zmianę proporcji dodawaj przez „Dodaj spadek”.
- Istniejące duplikaty są porządkowane przy aktualizacji planu oraz przeliczaniu skarp. W części wspólnej pierwszeństwo ma najnowsza definicja. Nienakładające się końce starszych skarp i ich lokalne proporcje pozostają; stare definicje są archiwizowane w DWG. Przeciwna strona i inne źródła są niezależne.
- Poprzednie powierzchnie są usuwane według indeksu właściciela, a nie tylko ukrywane. Po usunięciu manipulatora powierzchnia danego zakresu jest oznaczana jako nieaktualna/ukrywana; użyj Przelicz skarpy, aby odtworzyć ją z poprzednią proporcją.
