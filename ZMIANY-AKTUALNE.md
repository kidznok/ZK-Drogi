# ZK Drogi 0.58 — przekroje poprzeczne z pasmami

- Nowe i odświeżane przekroje mają układ dokumentacyjny: geometria projektu, zielony teren, szerokości, pochylenia, przerywana oś oraz cztery pasma: rzędne projektowane, istniejące, różnice wysokości i odsunięcie od osi.
- Jednakowa skala pionowa i pozioma, domyślny opis H/V 1:100. Usunięto poprzednie przeskalowanie X ×3, Z ×10. Odsunięcia liczone wzdłuż linii przekroju od przecięcia osi; lewa strona ujemna.
- Kilometraż, nazwa drogi i poziom porównawczy. Rzędne z dwoma miejscami, pionowe opisy kolumn i rozsuwanie bliskich kolumn bez zmiany ich wartości. Dno rowu, skarpy i przeciwskarpy pozostają częścią przekroju.
- Teren wynika z dokładnych przecięć linii przekroju z trójkątami TIN, nie z samego profilu podłużnego osi. Nie jest przedłużany przez luki powierzchni. Brak danych pokazuje — również w różnicach wysokości.
- Źródło terenu jest zapamiętywane przy Teren do profilu. Dla starszych projektów przekrój korzysta z jednoznacznego wspólnego terenu definicji skarp. Przy różnych źródłach trzeba wybrać teren przez Teren do profilu.
- Wybierz Odśwież przekroje, aby przebudować istniejące widoki. Nowy układ zachowuje ich punkty wstawienia, lecz może wymagać rozsunięcia widoków na arkuszu.
- Nie dodano fikcyjnych warstw konstrukcyjnych; przekrój pokazuje obecne punkty powierzchni drogi i dowiązania. Dokładne przecięcie skarp nadal zakłada typowy prostopadły przekrój, linie przekrojów z łukami są odrzucane.

497 testów obliczeniowych. Kompilacja i podgląd z tego samego generatora układu; natywnego wyglądu DWG w BricsCADzie jeszcze nie zweryfikowano.
