# ZK Drogi 0.63 — poprawka zapisu terenu

Naprawiono `eKeyNotFound` po komunikacie „Tworzenie osobnego DWG terenu”. Log wskazywał `Entity.set_Layer(String)` przy tworzeniu 3DFACE w osobnej bazie: nazwa warstwy była rozwiązywana w bieżącym DWG, a nie w bazie terenu. Trójkąty otrzymują teraz ustawienia docelowej bazy i identyfikator warstwy z tej samej bazy.

Po aktualizacji ponów import tego samego zakresu z tym samym układem wysokościowym i krokiem siatki. Pobrane poprawnie kafle pozostają w pamięci podręcznej i są ponownie wykorzystywane. Nie trzeba ich usuwać ani pobierać ponownie.

Kompilacja ze SDK BricsCAD V26 i testy aktualizatora przechodzą. Poprawka wynika z rzeczywistego stosu błędu użytkownika; pełnego zapisu DWG w uruchomionym BricsCADzie po zmianie jeszcze nie wykonano.
