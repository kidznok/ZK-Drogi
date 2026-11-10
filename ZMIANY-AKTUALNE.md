# ZK Drogi 0.73 — niezależny edytor profilu

- Edytor niwelety drogi i rowów jest oknem niemodalnym: pozostaje otwarty, a CAD nie czeka na jego zamknięcie.
- Zastosuj i aktualizuj DWG zapisuje zweryfikowane dane przez osobne polecenie CAD i nie zamyka edytora. Można stosować kolejne zmiany. Błąd zapisu pozostawia kopię roboczą w tym samym oknie.
- Wskazywanie początku/końca rowu w modelu również odbywa się przez osobne polecenie, a odczytany kilometraż wraca do edytora.
- Śledzenie na modelu jest realizowane po zakończeniu bieżącego polecenia CAD. Nie wykonuje zmian rysunku podczas przeciągania elementów CAD.
- Okno jest przypisane do konkretnego DWG i osi. Przy innym aktywnym rysunku zapis jest blokowany; zamknięcie źródłowego DWG zamyka jego edytor.
- Zmiana geometrii osi lub zapisanej niwelety w CAD podczas otwarcia edytora blokuje nadpisanie nieaktualnymi danymi. Należy ponownie otworzyć edytor. Zwykłe przybliżanie, przesuwanie widoku i praca nad innymi obiektami pozostają dostępne.
- Jednocześnie działa jeden edytor profilu. Przed dodaniem nowego odcinka rowu lub otwarciem innej drogi trzeba zamknąć bieżący edytor.

Sprawdzenie: kompilacja z SDK BricsCAD; testy WPF na odizolowanym pulpicie Windows: aktywne okno nadrzędne, wielokrotne Zastosuj bez zamykania, pozostawienie kopii po błędzie, asynchroniczny odbiór kilometrażu, zamknięcie oraz dotychczasowe testy profilu i rowów. Nie zweryfikowano jeszcze obsługi obu okien równocześnie w uruchomionym BricsCAD.
