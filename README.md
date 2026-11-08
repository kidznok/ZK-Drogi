# ZK Drogi
Nakładka testowa do projektowania dróg w BricsCAD V26 x64.

Instalator pobieraj z Releases. Przed instalacją zamknij całą aplikację BricsCAD. Wymagany .NET Desktop Runtime 8.0.33 lub nowszy z linii 8. Instalator nie jest podpisany cyfrowo.

Aktualizacje korzystają ze stabilnych wydań tego repozytorium. W menedżerze można sprawdzać je ręcznie lub włączyć automatykę. Instalacja następuje po zamknięciu CAD.

## Publikowanie
Dodanie numerowanego ZKDrogi-Setup-NUMER.exe do gałęzi main uruchamia workflow, który sprawdza ProductVersion, tworzy sumę SHA-256 i publikuje stabilne wydanie jako Latest. Numery kolejnych wersji: 0.29, 0.30 itd. Nie zmieniaj wyłącznie nazwy poprzedniego EXE.

## Stan
Kompilacja i testy obliczeniowe przechodzą. Nie potwierdzono natywnie usunięcia zgłoszonej awarii tworzenia krawędzi z poboczami. Wersja 0.29 dodaje optymalizacje, zabezpieczenia i diagnostykę. Szczegóły: ZMIANY-AKTUALNE.md. Zachowaj kopię DWG przed próbą.
