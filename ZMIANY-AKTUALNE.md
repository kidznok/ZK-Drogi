# ZK Drogi 0.42 — wąskie okno geometrii i długie powiązania

- Geometria osi otwiera się jako osobne, wąskie, pływające okno (350 px), bez dokowania i bez zakładki palety. Można przesuwać je po ekranie i nadal pracować w CADzie. Zamknięcie ukrywa okno; ponowne wywołanie pokazuje je ponownie.
- Pozostają pola R, L₁, L₂, podgląd, nawigacja PI, wskazywanie na rysunku i Zastosuj geometrię. Zapis nadal odbywa się przez polecenie CAD, nie bezpośrednio z obsługi modeless WPF.
- Naprawiono błąd Expected end of string / ReadBinding po wydłużeniu osi: powiązania szerokościowe czytają wszystkie fragmenty tekstu Xrecord, a nie tylko pierwszy. Zapis długich list punktów jest dzielony na fragmenty po maksymalnie 1024 znaki. Ten sam odczyt stosowany jest do planu, poboczy i starszych ścieżek przebudowy.
- Obsługiwane są istniejące poprawne zapisy jedno- i wielofragmentowe. Nie odtwarzamy brakujących danych przez zgadywanie szerokości.
- Zachowane poprawki 0.41: otwarcie edytora bez przebudowy planu, naprawa niezgodnej listy próbek przy zastosowaniu geometrii i aktualizacja zależnych krawędzi/poboczy z zapisanych powiązań. 3D i skarpy pozostają do jawnego przeliczenia.

Weryfikacja: 386 testów obliczeniowych, w tym zapis/odczyt 2000 punktów szerokości na odcinku ok. 10 km, odtworzenie błędu odczytu pierwszego fragmentu, zgodność starych zapisów; test panelu WPF i testy aktualizatora. Plugin kompilowany z API BricsCAD V26, w tym ShowModelessWindow. Otwarcia nowego okna i edycji na rysunku w natywnym BricsCADzie nie zweryfikowano automatycznie.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wersja 0.42. Po ponownym uruchomieniu użyj Aktualizuj plan; model 3D i skarpy przelicz osobno. Geometria osi otworzy wąskie okno.
