# ZK Drogi 0.33 — naprawa okna aktualizacji

Przyczyna potwierdzona testem konstruktora starego okna: System.IO.IOException, nie można zlokalizować assets/zkdrogi.ico. GraphicTheme.Apply próbował ustawić ikonę okna z zasobu, którego nie dodano do projektu menedżera. Proces kończył się przed pokazaniem okna; użytkownik widział brak reakcji po kliknięciu. W CrashDumps istniały świeże zrzuty ZKDrogi.Manager.exe.

- Ikona okna korzysta teraz z istniejącego zasobu ZK-logo.png.
- Dodano obsługę błędów startu i wyjątków UI: komunikat oraz %LOCALAPPDATA%/ZKProjekt/Drogi/logs/manager-startup.log zamiast milczącego zakończenia.
- Polecenie ZKDROGIUPDATE uruchamia konkretny EXE bez skojarzeń powłoki, z poprawnym katalogiem roboczym. Raportuje start i wykrywa szybkie zakończenie procesu kodem błędu.
- Funkcje i poprawki geometrii z 0.32 pozostają bez zmian.

Test regresyjny ManagerUiChecks: przed poprawką FAIL z brakującą ikoną; po poprawce PASS, zasoby i konstruktor poprawne, natywne okno WPF zostało pokazane i zamknięte. Ten test nie wykonuje pobierania z GitHuba. Testy transportu/logiki aktualizatora są oddzielne. Nie jest to potwierdzenie działania skarpy ani innych funkcji CAD.

Zainstaluj 0.33 ręcznie przy zamkniętym BricsCADzie — stary menedżer nie potrafi pokazać okna, więc nie da się skorzystać z jego przycisku aktualizacji. Po instalacji uruchom CAD i wybierz Program → Aktualizacja programu.

GitHub: v0.33, ZKDrogi-Setup-0.33.exe. Wymagany .NET Desktop Runtime 8.0.33+ z linii 8.
