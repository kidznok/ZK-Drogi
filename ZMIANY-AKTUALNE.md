# ZK Drogi 0.52 — nawigacja W i przybliżanie planu

- Geometria osi otwiera okno bez pytania o punkt na rysunku. Otwierany jest ostatnio wybrany wierzchołek bieżącej osi albo pierwszy wewnętrzny wierzchołek.
- U góry okna dodano domyślnie włączone „Przybliż do W”. Otwarcie okna i przełączanie strzałkami między W przybliża bieżącą rzutnię modelu do wybranego wierzchołka oraz jego łuku i klotoid.
- Wyłączenie przełącznika pozwala przeglądać wierzchołki bez przesuwania widoku CAD. Ponowne włączenie pokazuje aktualnie wybrany W.
- Widok jest ustawiany w planie i obejmuje geometrię łuku z marginesem. Nie jest wykonywane przeliczanie modelu ani zmiana geometrii drogi.
- Oznaczenia PI w oknie geometrii, podglądzie, nawigacji i nagłówku ramp zastąpiono W (wierzchołek). Nazwy technicznych poleceń i identyfikatory zapisane w DWG zachowują zgodność z wcześniejszymi wersjami.
- Opcjonalne „Wskaż” nadal pozwala wybrać W kliknięciem na planie. Dodawanie W nadal wymaga wskazania odcinka i położenia nowego punktu.
- Szybkie kolejne przełączenia aktualizują docelowy wierzchołek. Przy wyłączonym przybliżaniu lub zamkniętym oknie oczekujące przybliżenie nie jest wykonywane. Papier bez aktywnej rzutni nie jest przybliżany.

Weryfikacja: testy obszaru przybliżenia (cały łuk, asymetryczne klotoidy, proporcje rzutni i długi odcinek drogi), testy okna WPF oraz kompilacja dla BricsCAD V26. Samego przesuwania rzutni w natywnym BricsCADzie jeszcze nie zweryfikowano. Instalacja po zamknięciu wszystkich sesji BricsCAD.
