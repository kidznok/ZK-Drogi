# ZK Drogi 0.47 — dodawanie PI natywnym uchwytem

- Usunięto ogólną blokadę „Zmiana liczby PI nie jest jeszcze obsługiwana tym uchwytem” dla dodania jednego wewnętrznego wierzchołka do łamanej RS_CONTROLS.
- Natywna edycja rozpoznaje nowy punkt pomiędzy dotychczasowymi punktami, a następnie korzysta z tego samego mechanizmu co Dodaj PI w oknie geometrii: przesuwa indeksy istniejących łuków, dodaje kotwicę kilometrażu i aktualizuje powiązania krawędzi, poboczy, ręcznych poszerzeń, niwelet i skarp.
- Zwykłe przesuwanie istniejących PI pozostaje bez zmian. Po dodaniu PI wybierz Geometria osi i wskaż nowy wierzchołek, aby nadać R/L₁/L₂.
- Obsługiwane jest dodanie jednego wewnętrznego PI na polecenie przy zachowaniu pozostałych punktów. Jednoczesne dodawanie i przesuwanie dawnych punktów, usuwanie PI oraz dopisywanie punktu poza końcami osi są odrzucane z osobnym wyjaśnieniem zamiast ogólnej blokady. W razie błędu wraca ostatnia poprawna oś.
- Nowa topologia jest przygotowana przed sprawdzeniem WR-D, tak aby walidacja nie używała starej liczby kotwic. Rysunek jest zapisywany transakcyjnie; model 3D i skarpy nadal wymagają osobnego przeliczenia.

Weryfikacja: 425 testów obliczeniowych, w tym rozpoznanie dodania przy pierwszym i ostatnim odcinku, zgodność geometrii i indeksów łuków dla uchwytu i okienka, odrzucenie niejednoznacznych zmian. Kompilacja pluginu dla BricsCAD V26 i testy aktualizatora. Natywnej edycji uchwytem na rysunku użytkownika jeszcze nie zweryfikowano.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.47. Dodaj punkt uchwytem na łamanej RS_CONTROLS albo użyj Dodaj PI w edytorze geometrii. Przy wyłączonej automatyce wybierz Aktualizuj plan.
