# ZK Drogi 0.56 — zakres rowu wskazywany w CAD lub profilu

- Dodaj rów pyta o Lewy/Prawy i otwiera edytor bez wpisywania kilometraży w wierszu poleceń. Początkowy roboczy zakres obejmuje oś; można go od razu skrócić. Zapis nadal blokuje nakładanie rowów po tej samej stronie.
- W ustawieniach rowu: Początek · CAD, Koniec · CAD oraz Początek · profil i Koniec · profil.
- CAD: chwilowe przejście do wskazania punktu w modelu, rzut XY na oś i odczyt kilometrażu z uwzględnieniem UCS. Esc zachowuje zakres.
- Profil: kliknij na wykresie w wybranym kilometrażu. Wysokości granic pochodzą z dotychczasowej niwelety; nie są pobierane z przypadkowej wysokości kliknięcia.
- Skrócenie usuwa PVI poza zakresem. Granica przecinająca łuk pionowy wymaga wcześniejszej korekty łuku, aby nie zmieniać go niejawnie.
- Gdy nie ma widoku profilu DWG, miejsce wstawienia wskazuje się po zatwierdzeniu edytora.

Przechodzą testy okna, wyboru zakresu i anulowania. Kompilacja z SDK BricsCAD; natywnego przejścia do wskazywania w CAD jeszcze nie zweryfikowano.
