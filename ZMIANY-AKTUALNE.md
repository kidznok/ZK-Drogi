# ZK Drogi 0.29
- W oknie tworzenia krawędzi koniec odcinka pokazany do 0,01 m. Niezmienione pole zachowuje dokładną długość osi w obliczeniach.
- Tworzenie krawędzi i poboczy przeniesione z callbacku otwartego okna WPF do polecenia po zamknięciu okna. Jedna transakcja dla całej operacji.
- Pamięć ramek osi w obrębie przebiegu planu ogranicza powtarzanie kosztownych natywnych wywołań dla kolejnych elementów.
- Scalanie siatki wyszukuje pobliskie punkty sterujące binarnie, zamiast przeglądać całą ich listę dla każdej próbki.
- Kontrola czasu 20 s przy kolejnych obliczeniach ramek. Nie przerywa trwającego pojedynczego wywołania natywnego CAD; nie jest gwarancją zapobiegania natywnym crashom. Wyjątek wycofuje transakcję; znaczniki nowo utworzonych etykiet nie pozostają po rollbacku.
- Log etapów CREATE_EDGES: start elementu, geometria, etykieta, commit, aktualizacja planu.

Log użytkownika kończył się przed nowymi etapami tworzenia; nie uzyskano stosu natywnej awarii. Przyczyna crasha nie jest dowiedziona. Poprawka ogranicza podejrzane operacje i dodaje diagnostykę; nie wykonano natywnego odtworzenia awarii.

Zamknij BricsCAD i zainstaluj ZKDrogi-Setup-0.29.exe. Zachowaj kopię odzyskanego rysunku. GitHub: tag v0.29. Moduł wewnętrzny nadal RoadSketch.Spatial28, zgodny ze schematem projektu; publiczna wersja instalatora/menedżera 0.29.
