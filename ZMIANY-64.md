# ZK Drogi 0.64 — mapowanie istniejących krawędzi

Nawigator → Krawędzie i elementy → **Mapuj krawędzie** (`RSMAPEDGES`). Program przegląda istniejące polilinie w modelu i przypisuje je do aktywnej drogi według zapisanych reguł warstw: krawędź jezdni, pobocze, krawężnik, chodnik, zatoka.

Typ, odniesienie, pochylenie lub wysokość krawężnika i podążanie w planie pochodzą z ustawień mapowania warstw. Najpierw powstają powiązania z osią, następnie zależne krawężniki/pobocza/chodniki. Kolejność obiektów w pliku nie decyduje o kolejności przypisania. Końcówki L/P i zakres krótszych fragmentów są uwzględniane przez dotychczasowy mechanizm rozpoznawania.

Ręczne mapowanie działa również przy wyłączonym automatycznym rozpoznawaniu nowo rysowanych polilinii. Nie włącza tej automatyki na przyszłość. Powtórne użycie zachowuje istniejące przypisania, ręczne korekty i spadki. Nie przejmuje obiektów innych dróg ani wygenerowanej geometrii; nie przetwarza Xrefów i podkładów. Zamknięte i zdegenerowane polilinie nie są elementami krawędzi.

Jeżeli odniesienie nie jest jednoznaczne, polilinia pozostaje nieprzypisana, a wiersz poleceń podaje przyczynę. **Wybierz odniesienia** otwiera dotychczasową tabelę do ręcznego rozstrzygnięcia. Nie zgadujemy zależności między kilkoma pasującymi krawędziami. Błędne lub niepełne reguły warstw wymagają poprawienia w Ustawieniach → Mapowanie warstw.

Po mapowaniu aktualizowany jest plan i licznik elementów w Nawigatorze. Powierzchnie, skarpy i model 3D pozostają do jawnego przeliczenia.

Weryfikacja: kompilacja SDK BricsCAD V26; 555 testów geometrii/polityk, w tym istniejące przypadki mapowania nazw, stron L/P, krótkich fragmentów i niejednoznacznych odniesień. Pełnego przebiegu nowego przycisku w uruchomionym CAD jeszcze nie sprawdzono.
