# ZK Drogi 0.45 — nowy edytor profilu i śledzenie w modelu CAD

- Ciemny edytor niwelety: duży wykres z pasmami, zwarty panel parametrów PVI po prawej, stała dolna belka Zastosuj i aktualizuj DWG / Anuluj. Obsługa drogi i niezależnych niwelet rowów pozostaje.
- Tabela PVI jest zawsze dostępna pod wykresem, ale domyślnie zwinięta przy każdym otwarciu. Kliknij Tabela PVI, aby rozwinąć edytowalne kolumny kilometrażu, rzędnej i promienia R. Zwinięcie oddaje miejsce wykresowi, bez usuwania danych.
- Zachowano przeciąganie PVI, łuki pionowe żółte z PŁ/KŁ, dodawanie załomu pod PPM, cofanie oraz przesuwanie widoku środkowym przyciskiem lub trybem Przesuń. Kółko przybliża, Shift+kółko przesuwa poziomo.
- Śledź na modelu CAD rysuje tymczasowy cyjanowy znacznik i linię przekroju na rzeczywistej osi w modelu CAD, na wysokości zapisanej niwelety. Ruch kursora po profilu, wybór i przeciąganie PVI zmienia kilometraż znacznika. Nie ma miniatury planu wewnątrz edytora.
- Znacznik nie jest obiektem DWG. Wyłączenie śledzenia, opuszczenie wykresu i zamknięcie edytora usuwa go. Położenie kamery i orientacja rzutni pozostają bez zmian; model musi być widoczny w rzutni, np. po przesunięciu okna edytora na bok.
- Nagłówek służy do przesuwania okna, dolny narożnik do zmiany rozmiaru. Instrukcje w panelu bocznym są zwinięte pod Obsługa.

Weryfikacja: 412 testów obliczeniowych, rzeczywiste testy WPF profilu (tabela domyślnie zwinięta, rozwijanie, odzyskanie miejsca przez wykres, edycja PVI, cofanie, PPM, skale, przesuwanie i zdarzenia śledzenia), wyrenderowanie i inspekcja obu stanów okna. Kompilacja pluginu z API BricsCAD V26 i testy aktualizatora. Natywnego wyświetlania znacznika w BricsCADzie nie zweryfikowano.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.45. Następnie otwórz edytor niwelety. Tabela PVI rozwinie się po kliknięciu jej nagłówka; Śledź na modelu CAD włącza znacznik w CADzie. Zmiany geometrii zatwierdzaj Zastosuj i aktualizuj DWG; 3D i skarpy przeliczaj osobno.
