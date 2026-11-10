# ZK Drogi 0.71 — automatyczne skarpy od poboczy

Nawigator → Skarpy → **Skarpy od poboczy**. To nowy domyślny przebieg polecenia `RSDAYLIGHT`:

- Jedno pytanie: pochylenie **1:n**, domyślnie **1:1,5**.
- Źródła: wszystkie przypisane elementy typu Pobocze aktywnej drogi.
- Zakres: pełny wspólny zakres modelowy każdego pobocza, bez wpisywania kilometraży.
- Kierunek: na zewnątrz od osi, rozpoznawany z zapisanej strony pobocza.
- Teren: Xref i warstwa zapisane przy drodze, bez ponownego wskazywania. Dla starszych projektów dopuszczony jest jeden wspólny teren istniejących skarp; jeżeli nie ma jednoznacznego terenu, program prosi o przypisanie go w sekcji Teren.
- Nowe odcinki używają kroku 5 m i zasięgu dowiązania 100 m. Istniejące parametry krok/zasięg są zachowywane. Krok skarpy pozostaje dostępny osobno.

Program tworzy powierzchnie i dotychczasowe strzałkowe manipulatory proporcji na skarpie. Zapisane niwelety rowów są nadal uwzględniane: skarpa do dna, dno i przeciwskarpa.

Ponowne uruchomienie aktualizuje istniejące skarpy na zewnętrznej stronie i uzupełnia wyłącznie brakujące zakresy. Nie tworzy drugiej skarpy na już obsłużonym zakresie tego samego źródła/strony. Ręczne zmiany proporcji i manipulatory istniejących skarp pozostają zachowane; podana domyślna proporcja dotyczy nowych odcinków. Skarpy ręczne na innych źródłach pozostają bez zmian.

Pobocze przecinające oś lub leżące na osi jest pomijane z komunikatem zamiast zgadywania strony. Nieprzypisane polilinie nie są automatycznie przejmowane przez to polecenie — trzeba je najpierw zmapować. Brak dowiązania do terenu jest zgłaszany, bez tworzenia sztucznego zakończenia.

Poprzedni szczegółowy przebieg pozostał jako `RSDAYLIGHTMANUAL` do nietypowych pojedynczych przypadków. Domyślny przycisk nie pyta o źródło, kilometraż, Xref, warstwę, krok, zasięg ani stronę.

574 testy geometrii/polityk, w tym kierunek dla lewego/prawego pobocza, odrzucenie niejednoznacznej strony i niepoprawnych danych, uzupełnianie luk oraz brak duplikatów przy ponownym wywołaniu. Kompilacja SDK BricsCAD V26. Pełnego utworzenia skarp dla wszystkich poboczy w uruchomionym CAD po zmianie jeszcze nie zweryfikowano.
