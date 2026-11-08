# ZK Drogi 0.31 — aktualizacja osi po ruchu PI

Log użytkownika potwierdził: Axis PI build complete, następnie Teigha.Runtime.Exception: Layer is locked w DrawAxisTypes. Błąd przy usuwaniu starej, kolorowej reprezentacji powodował rollback całej aktualizacji, więc wynik osi nie podążał za przesuniętym PI. Dotyczył również zmian geometrii przez okno i odświeżania po utworzeniu profilu. Kolejny rzeczywisty stos potwierdził tę samą ścieżkę przy AddDaylight → UpdatePlan → DrawAxisTypes, przed wyborem terenu skarpy.

Poprawka otwiera do zapisu z forceOpenOnLockedLayer wyłącznie stare obiekty własnej reprezentacji osi, wskazane przez RS_AXIS_VISUAL_INDEX_30. Nie odblokowuje globalnie warstw użytkownika i nie zmienia polityki ochrony reprezentacji. Nowa geometria nadal powstaje na własnej warstwie, a źródło pozostaje edytowalne przez Uchwyty osi.

Zmieniono także nazwę przycisku na Dodaj łuk / krzywe przejściowe. Pozostały przebieg pracy z wersji 0.30 jest zachowany.

Instalacja: zapisz DWG, zamknij cały BricsCAD, zainstaluj 0.31 i otwórz rysunek. Aktualizuj plan powinno dokończyć oczekującą edycję PI, ponieważ program porównuje faktyczne współrzędne z zapisanymi. Następnie można edytować przez Uchwyty osi. Model 3D nadal przeliczany na żądanie.

Poprawka wynika z rzeczywistego stosu błędu, nie z przypuszczenia. Kompilacja oraz dotychczasowe testy obliczeniowe przechodzą; ten natywny przypadek na DWG użytkownika nie został jeszcze ponownie wykonany. Nie przedstawiamy testów poza CAD jako potwierdzenia działania blokad warstw i transakcji w BricsCADzie.

Szczegółowy opis funkcji: wydanie 0.30. Log modułu pozostaje startup-30.log; moduł RoadSketch.Spatial30. GitHub: tag v0.31, ZKDrogi-Setup-0.31.exe.

