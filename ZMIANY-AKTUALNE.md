# ZK Drogi 0.57 — wąski nawigator projektu

- Przycisk Nawigator projektu w sekcji Projekt i program, polecenie RSNAVIGATOR. Osobne, wąskie, niemodalne okno 330 px, skalowalne i przesuwane za nagłówek.
- Drzewo bieżącego DWG: oś, krawędzie i elementy, profil z niweletami rowów, model 3D, skarpy i przekroje.
- Zaznaczenie pokazuje powiązane polecenia; dwuklik otwiera pierwszą akcję. Wybranie niwelety rowu otwiera edytor z właściwym rowem.
- Bez osi dostępne są Rysuj polilinię oraz Wskaż oś. Nawigator pokazuje nazwę osi, zakres, prędkość i liczbę elementów/przekrojów.
- Odświeżenie następuje po poleceniu lub przełączeniu DWG w bezczynnym CAD. Samo drzewo nie uruchamia przebudowy planu ani modelu. Zachowuje zaznaczenie i zwinięte gałęzie.
- Panel dotyczy jednej bieżącej osi z istniejącego modelu projektu w DWG; nie dodaje obsługi wielu osi w jednym DWG.

Testy okna, adresowania edycji rowu, przeładowania drzewa bez poleceń CAD i zachowania rozwinięcia. Kompilacja z SDK BricsCAD; natywnego działania okna jeszcze nie zweryfikowano.
