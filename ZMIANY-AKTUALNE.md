# ZK Drogi 0.53 — skarpa, niweleta rowu i przeciwskarpa

- „Dodaj rów” pozwala utworzyć niweletę rowu lewego lub prawego bez wcześniejszej polilinii na planie. Wybierz stronę i zakres kilometrażu, następnie narysuj/edytuj niweletę w edytorze profilu. Nowa niweleta jest od razu wybrana w edytorze. Anulowanie nie zapisuje jej do DWG.
- Dostępna pozostaje opcja „Polilinia” dla istniejącego sposobu dodawania rowu. Strona takiego rowu jest rozpoznawana z położenia względem osi. Polilinia staje się odniesieniem zakresu/profilu; geometria rowu do skarpy wynika z rzędnej dna i proporcji skarpy.
- W zakresie aktywnej niwelety rowu istniejąca skarpa od pobocza schodzi do rzędnej dna, tworzy poziome dno o domyślnej szerokości 0,50 m i przeciwskarpę do terenu z Xrefa. Poza tym zakresem zachowuje bezpośrednie dowiązanie do terenu.
- Rów L działa tylko po lewej stronie osi, P tylko po prawej (zgodnie z rosnącym kilometrażem). Rzędne dna są obliczane również na łukach pionowych niwelety.
- W edytorze profilu dodano stronę/aktywność rowu, szerokość dna i proporcję przeciwskarpy (domyślnie 1:1,5). Zakres nowej, niezależnej niwelety można zmieniać kilometrażami jej końców. Dwa aktywne rowy po tej samej stronie nie mogą nakładać się kilometrażem.
- Spadek skarpy wewnętrznej nadal wynika z dotychczasowych manipulatorów 1:n. Zmiana proporcji przesuwa dno w planie przy zachowaniu jego rzędnej. Przeciwskarpa ma osobny parametr dla zakresu danej niwelety; wskazanie jej powierzchni przy edycji spadku zmienia ten parametr zamiast skarpy wewnętrznej.
- „Przelicz skarpy” zastępuje dotychczasowy wynik trzema pasmami w ramach tego samego właściciela — nie dokłada drugiej skarpy. Obliczenia korzystają ze wspólnego indeksu trójkątów terenu w transakcji.
- Przekroje korzystają z tego samego obliczenia: pokazują obie krawędzie dna, jego szerokość, rzędną i przeciwskarpę. Nowa linia przekroju obejmuje również dowiązanie do terenu.
- Dno powyżej pobocza, zbyt duży zasięg lub brak przecięcia przeciwskarpy z terenem są zgłaszane jako brak rozwiązania. Program nie odwraca przeciwskarpy w dół i nie łączy powierzchni przez brakujące dane.
- Po zapisie profilu wybierz „Przelicz skarpy”, a następnie „Odśwież przekroje”. Zmiana samej niezależnej niwelety rowu nie wymusza przebudowy całego modelu drogi. Istniejąca definicja skarpy musi wskazywać właściwe pobocze i teren; samo dodanie profilu nie wybiera Xrefa.

Ograniczenia: terrain nadal wymaga 3DFACE w Xrefie. Przeciwskarpa ma jedną proporcję na zakres niwelety rowu. Nie są dodawane automatyczne przejścia/wyokrąglenia na końcach rowu ani konstrukcje przepustów. Linię przekroju należy poprowadzić przez cały rów.

Weryfikacja: testy geometrii rowu i przecięć z terenem, zakresów i stron, łuków pionowych, braków danych, edytora profilu oraz regresji wcześniejszych funkcji. Działania na natywnym DWG w BricsCADzie jeszcze nie zweryfikowano. Instalacja po zamknięciu wszystkich sesji BricsCAD.
