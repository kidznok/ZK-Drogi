# ZK Drogi 0.55 — rów wyłącznie w zakresie osi

- Edytor niwelety otrzymuje rzeczywistą długość osi z DWG, niezależnie od zakresu zapisanej niwelety drogi.
- Kilometraż rowu poza osią jest odrzucany w polu i tabeli, zanim zostanie zapisany. Przeciąganie końców jest ograniczone do osi; dodawane punkty zachowują te ograniczenia.
- Końcówka zaokrąglona w polu do 0,001 m jest sprowadzana do dokładnej granicy osi (tolerancja wyłącznie zaokrąglenia 0,0005 m).
- Walidacja przy zapisie pozostaje dodatkowym zabezpieczeniem.

Testy edytora poza ekranem i kompilacja. Natywnego działania w BricsCADzie jeszcze nie zweryfikowano.
