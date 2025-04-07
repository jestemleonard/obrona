# 1. Instrukcje sterujące w językach programowania
Takie słowa które sterują przebiegiem programu jak if, else, switch, go to, return, while, for itp. Zarządzają one tym jak postępuje kod i co się kiedy wykonuje. Można tutaj trochę opisać te instrukcje co robią i kiedy się ich używa. Nie wszystkie słowa kluczowe są instrukcjami sterującymi na przykład `override` jest słowem kluczowym w C# ale nie steruje przebiegiem programu w sensie logiki wykonywania krok po kroku.
# 2. Przeciążanie (overloading) i przesłanianie (overriding) na przykładzie wybranego języka programowania
Overloading polega na stworzeniu wielu instancji tej samej metody, które różnią się tym co przyjmują i/lub tym co zwracają i/lub body metody. Pozwalają one na przykład stworzyć metodę `Add(int a, int b) int { return a + b;}` oraz `Add(float a, float b, float c) float { return a + b + c;}` (idk czy tak się w C# to pisze ale o to mniej więcej chodzi). Dzięki temu możemy wywołać metodę o tej samej nazwie i takiej samej lub podobnej funkcjonalności na różnych typach. Overriding jest wtedy kiedy mamy typ bazowy, który zawiera definicję jakiejś metody, a w typie który dziedziczy nadpisujemy tą metodę inną. Możemy na przykład mieć typ zwierzę, które ma metodę `Dzwiek()` wypisującą na ekranie *“zwierzę wydaje dźwięk”*. Następnie tworzymy typ kot który dziedziczy po zwierzęciu, ale nadpisuje metodę `Dzwiek()` swoją własną definicją, która zwraca *“miau”*.
# 3. Dziedziczenie i polimorfizm na przykładzie wybranego języka programowania
Dziedziczenie polega na tworzeniu typów, które zawierają pewne deklaracje, definicje oraz wartości domyślne, a następnie tworzone są inne metody, które dziedziczą po nich wszystko czego same nie nadpiszą. Pozwala to na tworzenie typów bazowych, które później rozszerzane są o potrzebną funkcjonalność. Polimorfizm pozwala na stworzenie interfejsu, który inne typy mogą implementować. Interfejs to taki zbiór wymagań. Aby zaimplementować interfejs typ musi spełniać wszystkie wymogi interfejsu. Dzięki temu każdy typ który spełnia wymogi danego interfejsu może być użyty w miejscu gdzie oczekiwany jest ten interfejs. Pozwala to na pisanie kodu, który może być wywołany przy użyciu wielu różnych typów jeśli wszystkie spełniają wymagania interfejsu.
# 4. Omów i porównaj kolekcje: kolejki LIFO, FIFO oraz listę jedno i dwukierunkową
Mowa o strukturach danych. **L**ast **I**n **F**irst **O**ut to przykład stosu, gdzie możemy push coś na górę stosu, albo pop coś z góry stosu. **F**irst **I**n **F**irst **O**ut to kolejka, gdzie możemy zrobić enqueue czyli zakolejkować (dodać na koniec kolejki) albo dequeue (czyli usunąć z początku kolejki). Listy jedno i dwukierunkowe to listy wiązane. Są one rodzajem struktury danych, gdzie obiekt posiada wartość oraz wskaźnik na kolejny obiekt (albo też na poprzedni w przypadku listy dwukierunkowej)
# 5. Typy i własności relacji w bazach danych
Żeby na to odpowiedzieć to warto powiedzieć wcześniej o kluczach. W relacyjnych bazach dany w każdej tabeli znajduje się klucz główny, który jest unikalny. Relacje między tabelami są tworzone przy pomocy kluczy obcych, które wskazują na klucz główny w innej tabeli. Dzięki temu możemy tworzyć relacje takie jak 1:1 gdzie jedno pole w tabeli odpowiada jednemu polu w innej tabeli. Na przykład jeden użytkownik (jego unikalne id) posiada tylko jeden login. 1:N czyli jeden do wielu gdzie na przykład jeden użytkownik biblioteki może wypożyczyć wiele książek. N:N czyli wiele do wielu tworzone są przy pomocy tabeli pomocniczej. Przykładem może być, że jeden student może być zapisany na wiele przedmiotów, a na każdy przedmiot może być zapisanych wielu studentów.
# 6. Rodzaje kluczy w bazach danych i ich zadania
Klucze to kolumny, które służą do identyfikacji i tworzenia relacji. Klucz główny (primary key) musi być unikalny i nie może być pusty. Zazwyczaj jest to kolumna **ID**. Umożliwia identyfikację i pozwala na podłączenie tej tabeli do innych (gdzie ten klucz główny będzie kluczem obcym). Drugiej rodzajem jest właśnie klucz obcy (foreign key). To kolumna która wskazuje na klucz główny w innej tabeli i pozwala na tworzenie relacji. Jest jeszcze klucz unikalny, który w przeciwieństwie do klucza głównego może być pusty i stosuje się go na przykład do adresu e-mail, gdzie kilku użytkowników nie może mieć tego samego. Klucz kandydat to każdy klucz który mógłby być kluczem głównym. Klucz złożony jak nazwa wskazuje składa się z kilku kolumn jeśli użycie jednej nie pozwala na unikalność.
# 7. Rodzaje złączeń, ich własności i zastosowanie w tworzeniu zapytań do baz danych
Złączenia w bazach danych służą do łączenia danych z różnych tabel. Najczęściej używany jest `INNER JOIN`, który zwraca część wspólną dwóch tabel. Kolejny jest `LEFT JOIN`, który zwraca wszystkie elementy z lewej, nawet jeśli nie mają odpowiednika z prawej. Przykładem może być joinowanie użytkowników i zamówień. `INNER JOIN` wyświetli użytkowników, którzy mają zamówienia. `LEFT JOIN` wyświetli wszystkich użytkowników nawet tych bez zamówień (przy takim użytkowniku będzie wtedy NULL). `RIGHT JOIN` wyświetliłby wszystkie zamówienia, nawet te, które nie mają przypisanych użytkowników. `CROSS JOIN` tworzy wszystkie możliwe pary, ale nie wiem o nim zbyt wiele i jest rzadko używany na przykład przy tworzeniu kombinacji produktów.
# 8. Pojęcie własności i rola transakcji w systemach bazodanowych
Transakcja to taki zestaw operacji, które muszą zostać wykonane wszystkie. Jeśli jakaś część nie zostanie wykonana to cała transakcja nie zostanie wykonana. Przykładem może być transakcja: `1. Odejmij 100 zł z konta A` `2. Dodaj 100 zł na konto B`. Jeśli krok pierwszy się nie wykona to nagle na koncie B pojawią się pieniądze znikąd. **Transakcje mają 4 podstawowe własności ACID:**
- **A**tomicity - niepodzielność czyli wszystkie operacje są wykonywane w całości albo wcale
- **C**onsistency - transakcja przeprowadza bazę danych ze stanu spójnego (wszystko jest poprawne) do stanu spójnego
- **I**solation - transakcje wywoływane są jednocześnie i nie przeczą sobie nawzajem
- **D**urability - po zatwierdzeniu zmiany są trwałe
Stosujemy je tam gdzie potrzebujemy operacji jednocześnie na wielu tabelach, spójności danych i występuje jednocześnie wiele operacji. Są szczególnie ważne w systemach bankowych.
# 9. Normalizacja w procesie projektowania baz danych
Normalizacja polega na rozbijaniu baz danych na mniejsze i tworzeniu między nimi relacji. Pozwala to eliminować powtórzenia, zwiększa logiczność danych i ułatwia utrzymanie bazy. Są różne stopnie normalizacji. Możemy mieć na przykład taką tabelę zamówień:

| ZamowienieID | Klient       | Produkty            | Adres             | KodPocztowy |
| ------------ | ------------ | ------------------- | ----------------- | ----------- |
| 1            | Jan Kowalski | Mleko, Chleb        | Kraków, ul. A 1   | 30-001      |
| 2            | Adam Nowak   | Jajka, Masło, Mleko | Warszawa, ul. B 2 | 00-002      |

**1NF** (1st Normal Form czyli pierwsza forma normalna) wymaga jednej wartości w jednej komórce, więc rozbijamy na osobne wiersze produkty i wtedy mamy więcej wpisów w tabeli, ale w każdym wpisie jest jeden produkt:

| ZamowienieID | Klient       | Produkt | Adres             | KodPocztowy |
| ------------ | ------------ | ------- | ----------------- | ----------- |
| 1            | Jan Kowalski | Mleko   | Kraków, ul. A 1   | 30-001      |
| 1            | Jan Kowalski | Chleb   | Kraków, ul. A 1   | 30-001      |
| 2            | Adam Nowak   | Jajka   | Warszawa, ul. B 2 | 00-002      |
| 2            | Adam Nowak   | Masło   | Warszawa, ul. B 2 | 00-002      |
| 2            | Adam Nowak   | Mleko   | Warszawa, ul. B 2 | 00-002      |

**2NF** wymaga, że dane zależne są od klucza głównego, a nie od jego części. Obecnie kluczem głównym jest **klucz kompozytowy** składający się z `ZamowienieID` oraz `Produkt`. W drugiej postaci normalnej rozbijamy tabelę na dwie:

| ZamowienieID | Klient       | Adres             | KodPocztowy |
| ------------ | ------------ | ----------------- | ----------- |
| 1            | Jan Kowalski | Kraków, ul. A 1   | 30-001      |
| 2            | Adam Nowak   | Warszawa, ul. B 2 | 00-002      |

| ZamowienieID | Produkt |
| ------------ | ------- |
| 1            | Mleko   |
| 1            | Chleb   |
| 2            | Jajka   |
| 2            | Masło   |
| 2            | Mleko   |

**3NF** - brak zależności przechodnich. Adres wskazuje na kod pocztowy, więc `KodPocztowy` jest zależny od Adresu, a nie od `ZamowienieID`. Możemy w takim razie wydzielić adresy do osobnej tabeli:

| ZamowienieID | Klient       | Adres             |
| ------------ | ------------ | ----------------- |
| 1            | Jan Kowalski | Kraków, ul. A 1   |
| 2            | Adam Nowak   | Warszawa, ul. B 2 |

| ZamowienieID | Produkt |
| ------------ | ------- |
| 1            | Mleko   |
| 1            | Chleb   |
| 2            | Jajka   |
| 2            | Masło   |
| 2            | Mleko   |

| Adres             | KodPocztowy |
| ----------------- | ----------- |
| Kraków, ul. A 1   | 30-001      |
| Warszawa, ul. B 2 | 00-002      |

Ostatecznie ważną rzeczą tutaj jest to, że pierwsza postać normalna mówi, żeby w komórce była tylko jedna wartość. Druga mówi, żeby dane zależały od klucza, a nie od jego części. Trzecia mówi, że dane nie mogą należeć od siebie nawzajem, tak jak `Adres` i `KodPocztowy` - wystarczy tylko jedno w zamówieniu, a drugie wynika z niego i można je przenieść do innej tabeli. Żeby to wszystko zrozumieć warto zwrócić uwagę na to jak zmniejsza się ilość powtórzeń w tabelach i ułatwia się modyfikacja. BTW w tabeli z `ZamowienieID` i `Produkt` nic nie jest unikalne i tam jest `klucz kompozytowy` bo na przykład mleko w zamówieniu 1 jest innym wierszem niż mleko w zamówieniu 2 więc kombinacja obu kolumn tworzy unikalny klucz.
# 10. Cykl życia produktu informatycznego. Zalety i wady modelu wodospadowego
Cykl życia produktu informatycznego to etapy przez które przechodzi oprogramowanie. Po angielsku nazywa się to **Software Development Life Cycle - SDLC**. Składa się na niego:
- **Analiza wymagań** - co ma robić system, jakie ma mieć funkcje i kto go będzie używać?
- **Projektowanie** – jak to będzie wyglądać i działać? (struktura bazy, interfejsy, logika)
- **Implementacja** – programiści piszą kod.
- **Testowanie** – sprawdzanie, czy system działa poprawnie i bez błędów.
- **Wdrożenie** – system trafia do użytkownika.
- **Utrzymanie i rozwój** – poprawki, aktualizacje, reakcja na błędy, rozbudowa.
Ten cykl realizuje się różnymi modelami. O modelu wodospadowym mogę tylko parafrazować Churchilla i powiedzieć, że Agile jest najgorszą formą planowania projektu poza każdą inną jaką posiadamy (w tym waterfallu). Model wodospadowy to sekwencyjne podejście, czyli przechodzimy przez wszystkie fazy po kolei i każda musi się zakończyć zanim zacznie się kolejna. Nie przewiduje się też cofania.
Nielicznymi zaletami tego modelu są:
- Prostota i przewidywalność - wszystko jest zaplanowane z góry, a nieszczęśnicy, którzy muszą w nim pracować nie potrzebują dodatkowych szkoleń żeby go stosować
- Dobra dokumentacja - w idealnym świecie każda faza powinna być dobrze udokumentowana
- Sprawdza się dobrze w prostych projektach
- Wiadomo kiedy kończy się każdy etap
Spośród wielu wad tego modelu możemy wymienić:
- Brak elastyczności - wszystko jest planowane z góry ☭
- Opóźnione testowanie - błędy wychodzą dopiero po pisaniu kodu
- Mało kontaktu z klientem - nie do końca wada bo klient lubi zmieniać zdanie, ale w tym przypadku jak już zmieni to ciężko to uwzględnić
- Nieprzydatny przy dynamicznych wymaganiach np. startupach albo większych projektach (albo takich z XXI wieku)
# 11. Wymaganie funkcjonalne i pozafunkcjonalne aplikacji
Wymagania funkcjonalne to funkcje i zachowania, które system ma realizować z punktu widzenia użytkownika. Można je zapisać w stylu: *"użytkownik może..."*, *"system ma umożliwiać..."*. Czyli funkcjonalne = co się dzieje po kliknięciu przycisku albo co użytkownik może zrobić.
Wymagania pozafunkcjonalne to jak aplikacja ma to robić. Nie mówią one co aplikacja robi tylko jak dobrze to robi. Takim wymaganiem może być na przykład *"aplikacja ma się uruchamiać w mniej niż 2 sekundy"* albo *"system musi obsługiwać 10000 użytkowników jednocześnie"*. Typowe kategorie, z których chociaż kilka warto zapamiętać to **wydajność, niezawodność, bezpieczeństwo, skalowalność, użyteczność i przenośność** (np. platformy na jakich ma działać aplikacja). 
# 12. Jakość oprogramowania i metody zapewniania jakości
W tym pytaniu chodzi o dwie rzeczy: co znaczy, że oprogramowanie jest dobrej jakości i jak możemy to osiągnąć. Jakość oprogramowania oznacza, że oprogramowanie działa zgodnie z założeniami (funkcjonalnymi i pozafunkcjonalnymi), jest stabilne, bezpieczne, wydajne, łatwe w utrzymaniu, użytkownikowi się łatwo z niego korzysta oraz że łatwo je zmodyfikować i naprawić potencjalne błędy. Żeby zapewnić jakość już od samego początku pisania programu można stosować dobre praktyki takie jak SOLID. Poza tym metody takie jak:
- code review
- unit testy (testowanie pojedynczych funkcjonalności)
- testy integracyjne (jak części programu ze sobą współpracują)
- testy manualne
- testy automatyczne end-to-end (testowanie całej aplikacji z punktu widzenia użytkownika jak manualne tylko automatycznie)
- CI/CD (continuous integration/deployment czyli automatyczne)
- statyczna analiza kodu
- monitoring i logowanie (w sensie tworzenie logów, a nie logowanie)
- udział QA/testerów w projekcie
Myślę, że wystarczy wymienić kilka z nich i będzie ok.
# 13. Język UML. Rodzaje diagramów i przykłady wykorzystania UML w rozwoju oprogramowania
**UML** to **U**nified **M**odeling **L**anguage. Graficzny język do projektowania i dokumentowania oprogramowania. Trochę dziwne, że to język bo jest graficznym przedstawieniem schematów działania. Są różne diagramy UML, ale kilka najważniejszych to:
- Diagram klas - służy do projektowania struktury aplikacji i przedstawia klasy (ich pola i metody) i relacje między nimi
- Diagram przypadków użycia - jak użytkownik wchodzi w interakcję z systemem. Służy do planowania funkcjonalności z punktu widzenia użytkownika
- Diagram aktywności - co po kolei się dzieje w programie. Przedstawia przebieg procesu i jego różne rozgałęzienia
- Diagram stanów - przejścia stanów obiektów, czyli co po kolei dzieje się na przykład z zamówieniem (jest tworzone, opłacone, realizowane, nadawane, odebrane)
# 14. Działania na macierzach
Macierze można dodawać, ale tylko jeśli są tej samej wielkości. Dodaje się wtedy element po elemencie, czyli dodajemy te które znajdują się w tym samym miejscu w obu macierzach i ich suma będzie w tym samym miejscu w nowej macierzy. Mnożenie przez skalar to po prostu przez liczbę i wtedy każdy element jest przez tą liczbę mnożony. Dwie macierze można pomnożyć tylko jeśli ich "wewnętrzne" wymiary są takie same czyli dla AxB liczba kolumn `A` musi być taka sama jak wierszy `B`. Mnożenie macierzy nie jest przemienne. Macierz jednostkowa to takie 1 dla mnożenia zwykłego. Zapisujemy ją jako **`I`** i `A x I = A`. Taka macierz ma same jedynki na przekątnej, reszta to 0. Zawsze jest kwadratowa. Macierze można **transponować** czyli zmieniać wiersze z kolumnami. Pierwszy wiersz staje się pierwszą kolumną itd. Macierze kwadratowe można też odwracać, ale tylko jeśli mają wyznacznik różny od 0. Żeby odwrócić macierz `A` możemy ułożyć równanie $A × A⁻¹ = I$ i rozwiązać. Jednym ze sposobów żeby to obliczyć jest ustawić macierz A i macierz I obok siebie i dodawać i odejmować wiersze tak, żeby z `A` zrobić macierz jednostkową i wszystkie te operacje powtarzać też na `I`. Na końcu I zmieni się w naszą macierz `A⁻¹`. Obliczanie wyznacznika w macierzy 2x2:

```
| a b |
| c d | → det = a*d - b*c
```

Dla 3x3 liczyło się to tak:

```
| a b c |
| d e f |
| g h i | → det = a*e*i + b*f*g + c*d*h - c*e*g - b*d*i - a*f*h
```

Bo trzeba sobie tak jakby dorysować tą macierz, bo ona się zapętla i wtedy możemy mieć trzy elementy na ukos. Na przykład tutaj mamy `b` i `f` ukośnie, ale brakuje nam trzeciego elementu, więc przepisujemy to `g` na dole, bo dół to `g h i` więc to się "zapętla" i następnym elementem znowu będzie `g` i wtedy dopełnia ono przekątną `b f g`. 
# 15. Metody rozwiązywania układów równań liniowych
Równania liniowe to takie, gdzie zmienne są tylko w pierwszej potędze. Układy tych równań oznaczają, że są co najmniej dwa równania. Żeby dało się je rozwiązać musi być przynajmniej tyle równań co zmiennych. Można je przedstawić przy pomocy macierzy. Łatwym sposobem rozwiązania ich jest podstawianie, czyli jedno równanie sprowadzamy do postaci, w której z jednej strony jest tylko jedna zmienna, a z drugiej cała reszta. Wtedy w drugim równaniu za tą zmienną przedstawiamy drugą stronę równania i wtedy mamy równanie jednej zmiennej, które możemy rozwiązać. Jak znamy już jedną zmienną to rozwiązujemy drugie równanie podstawiając rozwiązanie za zmienną i mamy drugą. Druga opcja to metoda eliminacji. Manipulujemy równaniem przez mnożenie **obu** stron tak, żeby jedna zmienna była przeciwnego znaku w tym równaniu co w drugim i je dodajemy do siebie i zostaje nam równanie jednej zmiennej. Jest też eliminacja Gauss'a, ale tam się podstawia pod macierze i próbuje uzyskać układ trójkątny i dużo roboty i tłumaczenia więc najlepiej o tym nie wspominać.
# 16. Metody reprezentacji grafów
Graf to struktura danych złożona z wierzchołków i krawędzi. Łatwiej to zrozumieć jako punkty i ich połączenia. Krawędzie (połączenia) mogą być skierowane (drogi jednokierunkowe), nieskierowane (drogi dwukierunkowe), albo ważone (czasem droga jest pod górkę, więc ciężej jest gdzieś się dostać). Można je przedstawić na **macierzy sąsiedztwa** (adjacency matrix) gdzie używamy tablicy `NxN` gdzie N to liczba wierzchołków. Wartość `1` albo jakaś inna w przypadku krawędzi ważonych oznacza istnienie krawędzi pomiędzy wierzchołkami. Przykład nieskierowanego grafu z wierzchołkami A, B, C:

```
   A B C
A [0 1 1]
B [1 0 0]
C [1 0 0]
```

Na tym grafie istnieją połączenia pomiędzy `A` i `B` oraz `C`, ale żadne inne. Wynika to z tego, że `1` są na punktach wspólnych `A` z pozostałymi wierzchołkami, ale nie ma żadnych krawędzi pomiędzy `B`, a `C`. Jest to prosta i szybka implementacja, ale zajmuje dużo pamięci. Drugą opcją jest **lista sąsiedztwa** (adjacency list). Do każdego wierzchołka jest przypisana lista jego sąsiadów. Można to zaimplementować w C# jako `Dictionary<string, List<string>>`. Przykład dla takiego samego grafu jak poprzednio:

```
A: B, C  
B: A  
C: A 
```

To rozwiązanie jest bardzo popularne i oszczędza pamięć, ale sprawdzanie czy istnieje krawędź jest wolniejsze. Możemy też po prostu wypisać wszystkie krawędzie w grafie:

```
[(A, B), (A, C)]
```

# 17. Kolejki priorytetowe i metody ich realizacji
Kolejka priorytetowa to struktura danych, w której każdy element ma przypisany priorytet. W przeciwieństwie do zwykłej kolejki FIFO czy LIFO, tutaj elementy są wyjmowane nie w kolejności dodania, ale w kolejności priorytetu – czyli najpierw wychodzą te najważniejsze. Najczęściej realizuje się to przy użyciu kopca binarnego, co pozwala na szybkie dodawanie i usuwanie elementów, ale opiera się na drzewie binarnym więc nie wchodzę w szczegóły. To rozwiązanie jest wbudowane w C# i realizowane przy użyciu klasy `PriorityQueue<TElement, TPriority>`. Można też użyć listy zawierającej elementy (para wartość i priorytet) i sortować ją po priorytecie po każdym dodaniu, ale to mniej wydajne. Kolejki priorytetowe są wykorzystywane np. w algorytmie Dijkstry, systemach kolejkowania zadań, grach czy systemach operacyjnych.
# 18. Słowniki i metody ich realizacji
Słownik to struktura danych klucz-wartość. W C# istnieje klasa `Dictionary<TKey, TValue>`, której można używać, żeby dostać się do konkretnej wartości przy pomocy klucza. Są wygodne i szybkie w użyciu. Istnieje też `HashSet<T>`, który przechowuje tylko klucz, który musi być unikalny. Ciekawostką jest, że w Go używa się wyłącznie `map` i nie istnieje typ `HashSet`, trzeba go stworzyć robiąc mapę klucz-`struct{}` który nic nie waży, więc posiadamy jedynie unikalne klucze. Zarówno w `Dictionary` jak i `map` możemy sprawdzić istnienie klucza, dodać element, usunąć element i wyciągnąć wartość.
# 19. Algorytmy sortowania
Algorytmy sortowania układają dane w określonej kolejności. Może to być kolejność rosnąca, malejąca, alfabetyczna i wiele innych. Istnieje wiele algorytmów sortujących, które różnią się wydajnością i sposobem działania, dlatego należy często dobrać najlepszy do danego zadania. Większość języków posiada wbudowane algorytmy sortujące `Sort()`. Przykładami takich algorytmów są: Bubble Sort, Selection Sort, Quick Sort. Są też algorytmy sortowanie stworzone jako żart, na przykład Bogosort, który losowo ustawia elementy i sprawdza czy są posortowane, albo [Stalin Sort](https://github.com/gustavo-depaula/stalin-sort), który usuwa nieposortowane elementy, ale chyba nie warto o tym wspominać.
# 20. Zadania, funkcje i protokoły warstwy sieciowej modelu OSI/ISO
**OSI** (**O**pen **S**ystems **I**nterconnection) to model komunikacji sieciowej. Opisuje jak dane przechodzą przez sieć od aplikacji aż do kabla, w 7 warstwach, z których każda ma swoją funkcję. Warstwy modelu OSI z przykładem nadawania paczki to:

| Warstwa | Nazwa        | Co robi i co ją używa                                        | Przykład                                                  |
| ------- | ------------ | ------------------------------------------------------------ | --------------------------------------------------------- |
| 7       | Aplikacji    | Programy użytkownika: przeglądarki, e-maile                  | Piszesz list do znajomego                                 |
| 6       | Prezentacji  | Kodowanie, szyfrowanie, konwersje (np. UTF-8)                | Tłumaczysz list na język angielski                        |
| 5       | Sesji        | Zarządzanie połączeniami (otwórz, utrzymaj, zamknij)         | Ustalasz, kiedy kurier ma przyjechać                      |
| 4       | Transportowa | Dzieli dane na segmenty, zapewnia niezawodność (np. TCP/UDP) | Dzielisz paczkę na mniejsze pudełka                       |
| 3       | Sieciowa     | Routing, adresy IP, pakiety                                  | Ustalasz adres odbiorcy i nadawcy (IP)                    |
| 2       | Łącza danych | Adresy MAC, ramki, przełączniki                              | Dajesz kurierowi dane o trasie w mieście (MAC)            |
| 1       | Fizyczna     | Bity, napięcia, fale – czyli kabel, sygnał, Wi-Fi            | Kurier jedzie furgonetką – czyli sygnał idzie przez kabel |

W tym pytaniu należy skupić się na **warstwie sieciowej** czyli trzeciej. Dodaje ona do pakietu IP adres źródła i docelowy, a następnie odpowiada za transport po sieci. Jeśli cel jest w tej samej sieci to wskazuje na adres IP, jeśli nie to najpierw kieruje do bramy domyślnej (routera), a następnie przez internet po adresach IP dociera do sieci docelowej. Jeśli pakiet jest za duży to jest dzielony na części. Taki pakiet, którym posługuje się warstwa 3 to tak naprawdę pakiet z warstwy 4 (taka paczka) z doklejoną etykietą (adresem IP nadawcy i odbiorcy), a sama warstwa trzecia opisuje drogę od początku do końca po adresach IP, nie wchodząc w szczegóły takie jak przełączniki, bity, fale czy Wi-Fi. Ta warstwa używa głównie protokołu IP (IPv4 / IPv6).

# 21. VLAN - funkcje, zadania i zastosowanie
**VLAN** (**V**irtual **L**ocal **A**rea **N**etwork) to logiczne wydzielenie sieci na poziomie warstwy 2 modelu OSI. VLAN pozwala na przykład na to, żeby kilka sieci było podłączonych do jednego łącza internetowego, ale pozostawały od siebie oddzielne i nie mogły się ze sobą komunikować. Przykładem może być biuro, które posiada osobną sieć dla serwerów, osobną dla pracowników, a osobną dla gości. Dzięki temu nie mają do siebie dostępu, wirus nie może się do nich dostać, a administracja może przydzielić różne pasma do różnych sieci. Ten podział robi się na switchu.
# 22. Architektury sieciowe klient-serwer a peer-to-peer
Połączenie klient serwer nie jest równorzędne. Klient może tylko wysyłać zapytania i otrzymywać odpowiedzi z serwera. Do jednego serwera może być podłączonych wiele klientów. Klienci też nie mogą się ze sobą bezpośrednio komunikować, tylko przez serwer. Przykładem takiego połączenia jest przeglądarka a serwer WWW. Połączenie **P2P** jest równorzędne. Każdy może wysyłać i odbierać dane. Nie ma też centralnego punktu i cała sieć jest rozproszona. Najlepszym przykładem tego są torrenty (używane wyłącznie do udostępniania dystrybucji Linuxa), gdzie każdy kto pobiera plik jednocześnie udostępnia innym pobierającym części tego pliku, które już posiada. Architektura klient-serwer jest prostsza do zarządzania i lepiej nadaje się do centralnych systemów (np. aplikacje webowe), natomiast P2P jest bardziej skalowalne i odporne na awarie pojedynczych węzłów.
# 23. Technologie i rozwiązania dostępowe do sieci LAN
**LAN** (**L**ocal **A**rea **N**etwork) to sieć lokalna. Chyba każdy taką ma w domu. Jest ona tworzona na przykład przez Ethernet albo Wi-Fi. Urządzenia w tej samej sieci widzą się i mogą się ze sobą komunikować (bez potrzeby "wychodzenia" do internetu). Pozwala to między innymi na dostęp do internetu, drukarek, serwerów, kamer czy plików ze wszystkich urządzeń w sieci. Można wspomnieć o VLAN, który jest technologią dzielenia dostępu w obrębie sieci LAN, co pozwala na separację urządzeń, albo o tym, że oprócz Ethernetu i Wi-Fi można też łączyć się przez Powerline, który przesyła dane przez instalację elektryczną. Nie wiem co tu więcej napisać po prostu trzeba lać wodę.
# 24. Przykłady i zastosowanie adresowania warstwy łącza danych oraz warstwy sieci w sieciach typu Ethernet
Pytanie o drugą i trzecią warstwę OSI w sieci LAN. Ethernet w sieci LAN używa adresów **MAC** do adresowania w warstwie łącza danych (warstwa 2), natomiast w warstwie sieci (warstwa 3) używa się adresów **IP**. MAC to fizyczny adres przypisany do karty sieciowej (np. `00:1A:2B:3C:4D:5E`) i pracują na nim switche. Służy on do komunikacji lokalnej. Adres IP (np. `192.168.1.5`) jest dynamiczny i pracują na nim routery. Służy on do komunikacji przez internet (zwykle). Kiedy urządzenie łączy się z drugim urządzeniem w tej samej sieci (np. `ssh 192.168.1.5`) to wtedy wysyła zapytanie do sieci o to kto ma ten adres IP, drugie urządzenie odpowiada swoim adresem MAC i komunikacja przebiega bezpośrednio między tymi dwoma urządzeniami przy użyciu MAC, bez udziału routera. Trochę inaczej to ujmując można powiedzieć, że IP to taki adres, a MAC to tożsamość. Adresy można zmieniać i kiedy chcemy się komunikować możemy stanąć na środku ulicy i krzyknąć pytanie kto mieszka pod tym adresem, a wtedy poznamy tożsamość mieszkańca i możemy prowadzić z nim już bezpośrednią rozmowę. Mam nadzieję, że ma to sens.
# 25. Reguły dotyczące wyboru tzw. najlepszej trasy do sieci docelowej dla routingu statycznego
Do tego ważne jest zrozumienie masek podsieci. Maski podsieci można zapisać na dwa sposoby: `255.255.255.0` oznacza to samo co `/24`. To znaczy, że trasa z maską `/24` doprowadzi do sieci, w której znajdują się maksymalnie 254 urządzenia (bo pierwsze 24 bity adresu wskazują na sieć, więc pozostaje nam 8 bitów na urządzenia w tej sieci). Router wybiera trasę, która wskazuje na jak najbardziej szczegółowy adres, czyli jak największa część tego adresu jest "zakryta" jedynkami, dlatego trasa z maską `/30` będzie preferowana przed maską `/8`. Jeśli kilka tras ma taką samą maskę, to zostanie wybrana trasa, która ma najniższą **metrykę** czyli wartość przypisaną trasie na podstawie np. kosztu, liczby przeskoków czy przepustowości. Jeśli dalej jest kilka tras które są takie same to router wybiera pierwszy numer interfejsu sieciowego np. `eth0` zamiast `eth1`. W przypadku kiedy brakuje pasującej trasy to router używa trasy domyślnej `0.0.0.0/0`. Ale skąd w ogóle biorą się te trasy? Niektóre router sam zna, bo na przykład ma interfejs `eth0` z IP `192.168.1.1/24` co znaczy, że zna całą sieć `192.168.1.0/24` bo jest jej częścią. Trasy statyczne (te o których mowa tym pytaniu) są wpisane ręcznie przez administratora i mówią coś w stylu "Jeśli chcesz dotrzeć do sieci `10.0.0.0/8`, idź przez `192.168.1.254`". Trasy dynamiczne pochodzą z routingu dynamicznego gdzie przy pomocy różnych protokołów routery wymieniają się informacjami między sobą (router który znam mówi, że zna drogę do innego routera, więc dodaję go do swojej tabeli).
# 26. Przykłady realizacji koncepcji izolacji ruchu w sieciach dla warstwy łącza danych oraz warstwy sieci
W **warstwie łącza danych** (warstwa 2) izolacja osiągana jest przez [[#21. VLAN - funkcje, zadania i zastosowanie|VLAN]]. Urządzenia w różnych sieciach VLAN nie widzą się nawzajem tak jakby były w osobnych sieciach. Realizowane są na switchach. W **warstwie sieci** (warstwa 3) izoluje się przez adresację i routing. Znaczy to, że tworzy się podsieci na przykład `192.168.1.0/24` dla jednego działu, a `192.168.2.0/24` dla drugiego. Reguły routingu i firewall mogą blokować ruch między tymi sieciami, albo pozwalać na wybrane połączenia.
# 27. *Garbage Collection* w środowisku .Net. Cykl życia obiektu w języku C\#
Garbage Collector w środowisku .Net automatycznie zarządza pamięcią więc nie trzeba się nim zbyt przejmować. Z punktu widzenia programisty pamięć jest zwalniana kiedy kończy się scope obiektu (zwykle scope jest w tych klamrach `{...}`). Śledzi wszystkie obiekty w pamięci i referencje do nich i usuwa te, które nie są nigdzie używane. GC działa na zasadzie generacji - Gen 0, Gen 1 i Gen 2. Obiekty nowo utworzone trafiają do Gen 0 i są często sprawdzane. Jeśli przetrwają kolejne przebiegi GC, są przenoszone do Gen 1, a następnie do Gen 2. GC sprawdza obiekty w Gen 0 najczęściej, w Gen 1 rzadziej, a w Gen 2 najrzadziej. Obiekty w Gen 2 to te, które żyją najdłużej np. dane globalne. GC usuwa obiekty, do których nie ma już referencji, na przykład po zakończeniu scopa. Można też wspomnieć o interfejsie `IDisposable`, ale ja się na tym nie znam, więc nie będę o tym więcej pisać. Coś tam ma wspólnego z ręcznym zwalnianiem zasobów takich jak pliki czy połączenia sieciowe.
# 28. Typy wartościowe i referencyjne - podobieństwa, różnice i realizacja w języku C\#
Typy wartościowe są bezpośrednio w pamięci, a typy referencyjne to takie, które przechowują adres w pamięci. Typy referencyjne można łatwo modyfikować, a wartościowe tylko nadpisywać. Chodzi o to, że zmiana typu wartościowego tworzy nową kopię, a zmiana referencyjnego działa bezpośrednio na oryginale, bo kopiuje się adres w pamięci. Typy wartościowe są prostsze, szybsze, ale mniej elastyczne, a referencyjne są bardziej złożone, ale dają więcej możliwości np. mogą być dziedziczone, albo mieć `null`. Przykładem typu wartościowego jest `int`, `bool`, `float`, `struct`. Przy przekazywaniu są kopiowane, więc ich zmiana nie wpływa na oryginał. Przykładem typu referencyjnego jest `string`, `array`, `class`, `List<T>`. Żeby to lepiej zrozumieć można spojrzeć na `int[]`, który jest obiektem. Przechowuje on typ elementów, długość tablicy, dane (które są ciągłymi elementami w pamięci). Dzięki temu, że jest referencyjny przechowuje obiekty poprzez ich adresy w pamięci, więc bezpośrednio może modyfikować ich wartości, a nie kopie. Dlatego jeśli zrobimy `a[1] = 2` to zmienimy faktycznie wartość drugiego elementu w tablicy na `2`. 
# 29. Klasy abstrakcyjne i interfejsy - podobieństwa i różnice, obszary wykorzystania
To w sumie porusza temat dziedziczenia i polimorfizmu. Przy ostatnich zmianach do C# zatarła się granica pomiędzy klasami abstrakcyjnymi a interfejsami, więc nakreślę różnice pomiędzy nimi bazując na tym jak wyglądało to w starszych wersjach. Klasy abstrakcyjne tworzą pewien schemat, który następnie możemy adaptować poprzez **dziedziczenie** do różnych podobnych zadań. Dzięki temu strukturyzujemy kod i unikamy powtórzeń. Mogą one zawierać zarówno deklaracje jak i definicje. Interfejsy pozwalają na **polimorfizm**. Są one takim zestawem wymogów, które implementujące je obiekty muszą spełniać, żeby mogły zostać użyte w miejscu tego interfejsu. Oryginalnie mogły one posiadać jedynie deklaracje, bez definicji. Jeśli jakiś obiekt implementuje interfejs to znaczy, że posiada on wszystkie zadeklarowane w nim elementy. Dzięki temu możemy np. napisać funkcję, która przyjmuje interfejs i używa metod, które są w nim zadeklarowane, a następnie przekazać tam **każdy** obiekt który dany interfejs implementuje bo wiemy, że on również będzie spełniać te wymogi (w tym przykładzie posiadać zadeklarowane w interfejsie metody). Kolejną różnicą, którą nie wiem jak wpleść w te definicje jest to, że klasa może dziedziczyć tylko po jednej klasie, ale implementować wiele interfejsów. Pojęcia te są na tyle podobne, że można zastosować w niektórych przypadkach klasę abstrakcyjną w miejscu interfejsu, ale nie jest to dobra praktyka i kłóci się z oryginalnymi założeniami tych konceptów. Dziedziczenie również może być w pewnym stopniu zastąpione polimorfizmem. Ja osobiście głównie piszę w Go, które nie posiada dziedziczenia, ale polega na bardzo rozbudowanym polimorfizmie.
# 30. Indexer i iterator - definiowanie i użycie w języku C\#
Indexer to mechanizm w C#, który pozwala traktować element jako tablicę (i jest też mechanizmem w samej tablicy). To to co pozwala nam zrobić na przykład `a[n]` gdzie wyciągamy `n`-ty element z tablicy `a`. Można go zdefiniować samodzielnie w klasie jako `this[index]`. Żeby to zrobić musimy stworzyć w klasie pole w klasie które jest tablicą na przykład oraz metodę, która pozwala po tej tablicy dostać się do wartości na przykład:

```cs
class MyArray
{
	private string[] data = new string[10];
	
	public string this[int index]
	{
		get { return data[index]; }
		set { data[index] = value; }
	}
}
```

Dzięki temu możemy potem poruszać się po instancji tej klasy jak po tablicy.
Iterator to mechanizm który pozwala nam przechodzić po elementach w kolekcji tak jak `foreach`. C# wspiera iteratory przez interfejs `IEnumerable` i `yield return`. Podobnie jak indexery możemy je zaimplementować w swojej własnej klasie jak na tym przykładzie:

```cs
class RomanNumerals : IEnumerable<string> // implementuje interfejs IEnumerable
{
    public IEnumerator<string> GetEnumerator()
    {
        yield return "I";
        yield return "II";
        yield return "III";
    }
}
```

Po zdefiniowaniu tego możemy wywołać na tej klasie `foreach`. Przykładowe użycie:

```cs
var rn = new RomanNumerals();
foreach (var v in rn)
{
	Console.Writeline(v); // I,II,III
}
```

Łatwo zapamiętać bo indexer ma index, a po iteratorze iterujemy.
# 31. Delegaty (ang. *delegates*) i zdarzenia (ang. *events*) - podobieństwa i różnice oraz kierunki wykorzystania
Delegat to typ w C#, który przechowuje referencję do metody, czyli możemy przypisać metodę do zmiennej. Żeby go stworzyć, najpierw deklarujemy typ delegata, potem metodę, a na końcu przypisujemy i wywołujemy:

```cs
public delegate void PowiedzCos();
void Powitaj() => Console.WriteLine("Cześć!");
PowiedzCos d = Powitaj;
d(); // uruchamia Powitaj
```

Delegaty pozwalają na tworzenie **zdarzeń** (`event`). Zdarzenie to mechanizm powiadamiania czyli jedna część programu może „ogłosić”, że coś się stało, a inne mogą się do tego zapisać i zareagować.

Przykład:

```cs
public class Gracz
{
    public event Action OnDeath;

    public void Zabij()
    {
        Console.WriteLine("Gracz zginął");
        OnDeath?.Invoke();
    }
}
```

A gdzieś indziej (np. w innej klasie):

```cs
Gracz g = new Gracz();
g.OnDeath += () => Console.WriteLine("Wyświetlam ekran Game Over");
g.Zabij();
```

W tym przypadku:

- Zdarzenie `OnDeath` jest ogłaszane przez klasę `Gracz`.
- Inna część programu subskrybuje to zdarzenie (`+=`) i przypisuje metodę, która się ma wykonać.
- Delegat przechowuje referencję do tej metody.
- Wywołanie `OnDeath?.Invoke()` oznacza: "jeśli ktoś się zapisał, to uruchom te metody".

Zaletą takiego podejścia jest to, że `Gracz` nie musi wiedzieć, co ma się stać po jego śmierci, tylko wystarczy, że „powie”, że zginął, a inne obiekty same zdecydują, jak na to zareagować.
# 32. Pochodna funkcji jednej zmiennej. Definicja, zastosowanie do szukania ekstremów lokalnych
Nie będę pisać jak się oblicza pochodną bo to powinno być oczywiste. Pochodna funkcji oznacza jej monotoniczność. Kiedy:
- `f′(x) > 0` to funkcja rośnie
- `f′(x) < 0` to funkcja maleje
- `f′(x) = 0` to funkcja ma punkt krytyczny (który jest minimum, lub maksimum zależy czy wcześniej rosła czy malała albo czy później rośnie czy maleje całkiem intuicyjnie można to ogarnąć)
Żeby wskazać czy ekstremum jest lokalne czy globalne najlepiej porównać te ekstrema, czyli podstawić sobie x i zobaczyć które maksimum jest największe, a które minimum jest najmniejsze i wtedy mamy ekstrema globalne.
# 33. Całka nieoznaczone i całka oznaczona. Twierdzenie Newtona-Leibniza
Całka nieoznaczona to odwrotność pochodnej. Wyznaczenie całki to tak naprawdę wyznaczenie każdej funkcji, której pochodna jest naszą oryginalną funkcją (dlatego na przykład mamy to `+ C` bo każda liczba może się tam znajdować bo i tak zniknie w pochodnej). Nie pamiętam na to żadnego wzoru, ale można tak na logikę przenieść sobie współczynnik przed niewiadomą do potęgi i dopisać `+ C` i powinno być ok. [Całka oznaczona](https://streamable.com/ar3vmz) to pole pod wykresem funkcji w przedziale `[a, b]` i zapisujemy ją tak:
$∫ᵃᵇ f(x) dx$
Twierdzenie Newtona-Leibniza mówi, że całkę oznaczoną można obliczyć za pomocą całki nieoznaczonej:
$∫ᵃᵇ f(x) dx = F(b) − F(a)$
czyli prostszymi słowami można powiedzieć, że całka oznaczona w przedziale `[a, b]` to wartość całki nieoznaczonej w punkcie `b` minus jej wartość w punkcie `a`. Można wspomnieć, że ze względu na definicję całki oznaczone ma ona zastosowanie do obliczania pól powierzchni.
# 34. Szyfrowanie symetryczne i asymetryczne
Szyfrowanie symetryczne to jedno hasło dla obu stron komunikacji. Szyfrujemy i odszyfrowujemy tym samym kluczem. To wygodne i szybkie rozwiązanie, ale stanowi problem kiedy chcemy komuś udostępnić ten klucz. Przykładem tego może być na przykład plik ZIP zabezpieczony hasłem - każdy może go otworzyć jeśli zna hasło, które zostało użyte do zaszyfrowania go. Szyfrowanie asymetryczne (o wiele ciekawsze) składa się z dwóch kluczy: publicznego i prywatnego. Klucz publiczny chcemy udostępnić każdemu, a prywatny trzymamy tylko dla siebie. Każdą rzecz zaszyfrowaną kluczem publicznym można odszyfrować tylko przy użyciu klucza prywatnego. Dzięki temu można go łatwo używać w komunikacji. Jeśli osoba A chciałaby się komunikować z osobą B szyfrem, to może najpierw przesłać jej swój klucz publiczny kompletnie niezaszyfrowany, bo nic się nie dzieje jeśli inni ludzie go znają. Dzięki temu osoba B może wysłać wiadomość zaszyfrowaną kluczem publicznym A, którą może przeczytać tylko osoba która ma odpowiedni klucz prywatny, czyli osoba A. Po wstępnej wymianie kluczy te osoby mogą wymienić się zaszyfrowanymi kluczami symetrycznymi, które są szybsze i lepiej radzą sobie z dużymi plikami.
# 35. Istota i rodzaje podpisu elektronicznego
Podpis elektroniczny to forma podpisu, która pozwala zarówno potwierdzić tożsamość osoby jak i zapewnić, że dokument nie został zmieniony. Najpierw dokument, który chcemy podpisać zostaje przepuszczony przez funkcję hashującą, a następnie ten hash jest szyfrujący kluczem prywatnym. Ten zaszyfrowany hash to podpis elektroniczny, który każdy kto posiada klucz publiczny może odszyfrować i sprawdzić czy odszyfrowany hash zgadza się z hashem dokumentu. Tylko osoba posiadająca klucz prywatny może podpisać w taki sposób zaszyfrować hash, żeby można go było odszyfrować tym kluczem publicznym. Potwierdza to również, że dokument został podpisany w konkretnej formie, a nie został zmieniony, bo przy jakiejkolwiek modyfikacji dokumentu jego hash by się kompletnie zmienił i nie zgadzał się z tym, który został podpisany. Podpisem elektronicznym może być również zwykły zeskanowany podpis, ale nie posiada on mocy dowodowej. Zaawansowany podpis elektroniczny to taki jaki opisaliśmy, oparty o kryptografię. Kwalifikowany podpis elektroniczny jest dodatkowo zabezpieczony certyfikatem wydanym przez zaufanego dostawcę. Taki certyfikat jest prawnie równoznaczny z tradycyjnym podpisem (np. podpis profilem zaufanym).
# 36. Metody szyfrowania: steganografia, metody podstawiania, metody transpozycyjne
Są to "tradycyjne" sposoby szyfrowania znane od dawna. Steganografia to nie do końca szyfrowanie a ukrywanie informacji. Dane ukrywane są w innych danych na przykład obrazach, dźwiękach czy tekstach. Przykładem może być ukrywanie wiadomości w inicjałach wierszy, bitach pikseli czy w muzyce (ciekawy przykład: w "Cyberdemon" Mick'a Gordon'a na spektografie jest [ukryta wiadomość](https://i.ytimg.com/vi/yzFit0nldf4/hqdefault.jpg)). Wadą tego rozwiązania jest to, że jeśli ktoś znajdzie tą wiadomość to nie jest ona w żaden sposób zabezpieczona. Metody podstawiania polegają na zamianie znaku na inny według jakiegoś klucza. Świetnym i prostym przykładem jest szyfr cezara, który przesuwa każdą literę o kilka miejsc w alfabecie, albo trochę bardziej złożony szyfr Vigenère’a. Są one jednak łatwe do złamania metodami statystycznymi takimi jak sprawdzanie częstotliwości występowania liter. Metody transpozycyjne zmieniają kolejność znaków miejscami nie zmieniając samych znaków. Problemem tego podejścia jest łatwość złamania przy dłuższych wiadomościach. 
# 37. Systemy IDS oraz IPS. Zalety i wady obydwu rozwiązań
**IDS** (**I**ntrusion **D**etection **S**ystem) oraz **IPS** (**I**ntrusion **P**revention **S**ystem) to systemy bezpieczeństwa, które monitorują ruch sieciowy i reagują na zagrożenia. IDS wykrywa nieprawidłowości i podejrzaną aktywność w sieci lub systemie i wysyła powiadomienia do administratora. Z powodu braku bezpośredniej ingerencji ma on mniejszy wpływ na działanie systemu i nie blokuje fałszywych alarmów oraz nie wpływa na wydajność ruchu sieciowego. Problemem z tym systemem jest opóźniona reakcja, bo zanim człowiek dostanie powiadomienie, zapozna się z nim i je rozwiąże to minie trochę czasu. IPS zapobiega włamaniom czyli aktywnie podejmuje działania takie jak blokowanie pakietów, zrywanie połączeń czy banowanie adresów IP. Zaletą tego rozwiązania jest szybka ochrona w czasie rzeczywistym oraz to, że nie wymaga stałego nadzoru człowieka. Minusem jest większa złożoność, a co za tym idzie obciążenie sieci, oraz potencjał do zablokowania fałszywych alarmów.
# 38. Wyjaśnij pojęcia: kryptologia, kryptografia i kryptoanaliza
Kryptologia to ogólna dziedzina wiedzy zajmująca się ukrywaniem, zabezpieczaniem i łamaniem zabezpieczeń. Dzieli się na dwie główne gałęzie: kryptografię i kryptoanalizę. Kryptografia to zabezpieczanie danych na przykład szyfrowanie, podpisy elektroniczne, certyfikaty, czy bezpieczne protokoły wymiany informacji (np. HTTPS). Z kolei kryptoanaliza to odwrotna strona kryptografii. Zajmuje się analizowaniem i łamaniem metod kryptograficznych. Celem jest odzyskanie informacji bez znajomości klucza szyfrującego, ale również sprawdzanie czy dana metoda szyfrowania jest bezpieczna.
# 39. Planarność i kolorowanie grafów
Graf planarny to taki, który da się narysować (na płaszczyźnie) bez krzyżowania krawędzi. Kwadrat, trójkąt, drzewo są planarne, natomiast na przykład graf K₅ (**K** - kompletny czyli gdzie każdy wierzchołek łączy się z każdym i **5** bo na pięciu wierzchołkach) nie jest planarny. Kolorowanie grafu to przypisanie koloru każdemu wierzchołkowi, tak aby żadne dwa sąsiadujące wierzchołki nie miały tego samego koloru. Liczba chromatyczna to minimalna liczba kolorów, która wystarczy do pokolorowania grafu. Dla drzewa jest to 2, dla trójkąta 3, a dla kwadratu 2. Dla każdego grafu planarnego liczba chromatyczna będzie zawsze mniejsza lub równa 4. Ciekawostką, która z tego wynika jest to, że mapę świata (która jest grafem planarnym) można pokolorować tak, żeby żadne dwa sąsiadujące kraje nie miały tego samego koloru, używając maksymalnie 4 kolorów.
# 40. Algorytm szyfrowania RSA
**RSA** (skrót od nazwisk twórców) to asymetryczny algorytm szyfrowania, czyli taki, który używa dwóch kluczy. Używany jest w systemach takich jak HTTPS, podpisy cyfrowe czy klucze SSH. Tworzenie klucza jest dość skomplikowane a w skrócie opiera się na iloczynie dwóch bardzo dużych liczb pierwszych. Rozłożenie ich iloczynu na czynniki jest praktycznie niemożliwe w rozsądnym czasie przy użyciu klasycznych komputerów, ale komputery kwantowe stanowią zagrożenie dla tej metody szyfrowania. Ciekawostka: z tego powodu powstają nowe metody szyfrowania nazywane *post quantum cryptography* jak ML-KEM (Module-Lattice-Based Key-Encapsulation Mechanism), które zostało ostatnio dodane do Chrome jako dodatkowy algorytm szyfrowania w komunikacji TLS.
# 41. Charakterystyka i wykorzystanie wzorców projektowych
Wzorce projektowe to znane i sprawdzone rozwiązania typowych problemów programistycznych, które występują w projektowaniu oprogramowania. Nie są one gotowym kodem, ale takim szablonem, który możemy dostosować do problemu, z którym się spotykamy. Typowym wzorcem projektowym jest **Singleton** - zapewnia on, że istnieje tylko jedna instancja danego typu. Używa się go często w konfiguracji czy loggerze. Przykładowa implementacja w Go:

```go
package config

import "sync"

var (
	instance *Config
	once     sync.Once
)

type Config struct {
	AppName string
	Port    int
}

func GetConfig() *Config {
	once.Do(func() {
		instance = &Config{
			AppName: "MyApp",
			Port:    8080,
		}
	})
	return instance
}
```

tworzy jednorazowo konfigurację i zapisuje ją do pojedynczej instancji, bo nie potrzeba nam kilku takich samych konfiguracji w programie. Kolejnym przykładem może być **Factory** które pozwala nam na tworzenie obiektu:

```go
type Animal interface {
	Speak() string
}

type Dog struct{}
func (d Dog) Speak() string { return "Woof!" }

type Cat struct{}
func (c Cat) Speak() string { return "Meow!" }

func AnimalFactory(kind string) Animal {
	if kind == "dog" {
		return Dog{}
	} else if kind == "cat" {
		return Cat{}
	}
	return nil
}
```

Takie factory tworzy obiekty (zwykle interfejsy) w zależności od warunku (np. konfiguracji) i ukrywa logikę tworzenia obiektu. Pozwala na tworzenie dynamicznych obiektów i łatwo podmienić implementację. Innymi przykładami znanych wzorców projektowych są: **Strategy** - pozwala podmienić zachowanie w czasie działania programu, czy **Observer** - powiadamia o zmianie stanu innego obiektu.
# 42. Omów kreacyjne, strukturalne i behawioralne wzorce projektowe
### Kreacyjne wzorce projektowe - dotyczą sposobu tworzenia obiektów, szczególnie wtedy, kiedy tworzenie jest złożone, zależne od kontekstu, albo wymaga ukrycia szczegółów implementacji
- **Singleton** – zapewnia, że istnieje tylko jedna instancja danej klasy/obiektu (np. konfiguracja, logger).
- **Factory Method** – deleguje tworzenie obiektów do metod, które mogą zwracać różne typy (np. na podstawie stringa).
- **Builder** – pozwala tworzyć złożone obiekty krok po kroku (np. składanie zapytania SQL).
- **Prototype** – tworzy nowe obiekty przez klonowanie istniejących.
### Wzorce strukturalne - dotyczą organizacji klas i obiektów - jak ze sobą współpracują, jak można je elastycznie łączyć, rozbudowywać i podmieniać
- **Adapter** – pozwala podłączyć do systemu obiekt, który ma „niewłaściwy interfejs” (np. stara biblioteka).
- **Decorator** – dodaje nowe funkcjonalności do obiektów w czasie działania.
- **Composite** – pozwala traktować pojedyncze obiekty i ich złożenia (np. foldery i pliki) w ten sam sposób.
- **Facade** – upraszcza złożony system, dostarczając prosty interfejs (np. klient API ukrywający szczegóły żądań).
### Wzorce behawioralne - opisują komunikację i interakcje między obiektami, czyli kto, kiedy i w jaki sposób ze sobą rozmawia.
- **Observer** – jeden obiekt informuje wiele innych o zmianie stanu (np. GUI, eventy, pub-sub).
- **Strategy** – pozwala podmieniać algorytmy w czasie działania (np. różne metody sortowania).
- **Command** – encapsuluje żądanie jako obiekt, który można przekazać, zapisać lub cofnąć.
- **State** – zmienia zachowanie obiektu w zależności od jego wewnętrznego stanu (np. automat do napojów).
Ubierając to w słowa można powiedzieć, że wzorce projektowe dzielą się na trzy główne grupy: kreacyjne, strukturalne i behawioralne. Wzorce **kreacyjne** koncentrują się na sposobie tworzenia obiektów – na przykład Singleton, który zapewnia jedyną instancję obiektu, albo Factory, który decyduje, jaki obiekt utworzyć. Wzorce **strukturalne** zajmują się organizacją i relacjami między obiektami, np. Adapter pozwala dopasować niekompatybilny interfejs, a Decorator dodaje funkcjonalności bez zmiany kodu. Wzorce **behawioralne** opisują sposób komunikacji między obiektami – np. Observer informuje subskrybentów o zmianie stanu, a Strategy pozwala dynamicznie zmieniać zachowanie programu. Znajomość tych wzorców pozwala pisać kod bardziej elastyczny, czytelny i łatwiejszy do rozwijania.
# 43. Zasady projektowania SOLID
SOLID to akronim pięciu zasad projektowania obiektowego, które mają sprawić, że kod będzie łatwiejszy do rozszerzania, trudniejszy do zepsucia i prostszy w testowaniu i utrzymaniu. Te zasady to:
- **S**ingle responsibility - klasa powinna mieć tylko jeden powód do zmiany czyli zajmować się jedną konkretną rzeczą.
- **O**pen/Closed - kod powinien być otwarty na rozszerzanie, ale zamknięty na modyfikacje. Zamiast zmieniać istniejącą klasę powinniśmy mieć możliwość rozszerzenia jej przez dziedziczenie czy interfejsy, bez zmieniania istniejącego kodu.
- **L**iskov substitution - jeśli obiekt dziedziczy po innym to powinien móc być użyty w miejscu klasy bazowej.
- **I**nterface segregation - lepiej mieć kilka mniejszych interfejsów niż jeden duży, żeby nie zmuszać do implementowania niepotrzebnych rzeczy.
- **D**ependency inversion - Moduły wysokiego poziomu nie powinny zależeć od modułów niskiego poziomu, tylko od abstrakcji.
W językach takich jak C# czy Java da się zaimplementować wszystkie te zasady, ale w niektórych (jak Go) język wymusza niektóre zasady, a inne uniemożliwia (na przykład nie da się wprowadzać dziedziczenia, ale ze względu na sposób działania interfejsów ciężko złamać interface segregation).
# 44. Wyjaśnij dlaczego JavaScript jest językiem skryptowym, funkcyjnym, proceduralnym i obiektowym
JavaScript jest:
- **skryptowy** - jest interpretowany, a nie kompilowany, służy głównie do automatyzacji działań (i ma script w nazwie)
- **funkcyjny** - funkcje w JS to *pierwszorzędne obiekty*, można je przekazywać, zwracać i przypisywać (jak [[# 31. Delegaty (ang. *delegates*) i zdarzenia (ang. *events*) - podobieństwa i różnice oraz kierunki wykorzystania|delegaty w C#]]) i można w nim pisać w czystym stylu funkcyjnym
- **proceduralny** - można pisać krok po kroku jak w **C** bez klas czy funkcji. Ponadto posiada zmienne, pętle czy warunki
- **obiektowy** - ma obiekty i obsługuje programowanie obiektowe, dostępne są klasy, dziedziczenie, metody instancyjne i statyczne.
W skrócie JS jest skryptowy, bo jest interpretowany i wykorzystywany do automatyzacji. Jest funkcyjny, bo pozwala traktować funkcje jak obiekty. Jest proceduralny, bo można w nim pisać proceduralnie, używając pętli i instrukcji krok po kroku. Jest obiektowy, bo obsługuje obiekty, klasy i dziedziczenie. To czyni go językiem **wieloparadygmatowym**.
# 45. Kaskadowość i dziedziczenie w języku CSS
CSS oznacza **C**ascading **S**tyle **S**heets i to *Cascading* oznacza kaskadowość, czyli mechanizm, który określa która reguła ma pierwszeństwo, gdy wiele reguł dotyczy tego samego elementu. To który styl zostanie zaaplikowany zależy od źródła stylu (styl domyślny przeglądarki < styl arkusza < styl w `<style>` < styl `inline` w HTML), od jego specyficzności ( `element` < `.klasa` < `#id`), a jeśli dalej mają tę samą specyficzność to wybierana jest ta która jest **później** w pliku (tak jakby się nadpisywały więc ta później jest najbardziej aktualna). Można to nadpisać używając `!important`. Niektóre właściwości CSS dziedziczą się automatycznie z elementu nadrzędnego (na przykład wszystkie `<p>` będą dziedziczyć z `<body>`). Takimi właściwościami jest `color`, `font-family` czy `text-align`. Nie dziedziczy się natomiast `margin`,`padding`, `border` itp. Można jednak wymusić dziedziczenie dodając do właściwości `inherit`.
# 46. Istota semantyczności języka HTML (opisz i podaj przykłady dobrych praktyk)
Semantyczność w HTML oznacza, że używamy znaczników zgodnie z ich przeznaczeniem. Dzięki temu opisują one znaczenie zawartości, a nie tylko wygląd. Jest to przydatne dla SEO (Search Engine Optimisation), czytelności kodu, dostępności na wielu urządzeniach i testowania. Teoretycznie możemy zrobić wszystko używając `<div>`, ale semantyczność polega na używaniu znaczników takich jak `<header>`, `<nav>`, `<section>` czy `<article>`. Dobrymi praktykami są: unikanie nadmiaru `<div>` czy `<span>`, używanie tagów zgodnie z przeznaczeniem, używanie jednego `<h1>` na stronę, czy dbanie o logiczną strukturę dokumentu.
# 47. Optymalizacja stron WWW
Optymalizacja strony WWW to zbiór działań, które mają na celu przyspieszenie działania strony, zmniejszenie jej rozmiaru oraz zwiększenie responsywności i dostępności dla użytkownika i wyszukiwarek (SEO). Polega między innymi na kompresji grafik, minimalizacji kodu, asynchronicznym ładowaniu JS, cachowaniu, czy używaniu elastycznych layoutów. Dzięki temu strona lepiej działa, szybciej się ładuje, zużywa mniej zasobów i jest lepiej oceniana przez użytkowników i wyszukiwarki.
# 48. Metody zarządzania projektami: klasyczna (proaktywna), zwinna (Scrum) i szczupła (Kanban)
Nie do końca rozumiem pytanie i czy jest ono poprawnie sformułowane, bo metodyka zwinna to **Agile**, do której należy zarówno **Scrum** jak i **Kanban** (chociaż ten często mocniej implementuje wartości metodologii szczupłych), natomiast metodyka szczupła to **Lean**, z której wywodzą się niektóre elementu Agile.
Modelem klasycznym jest przykład [[#10. Cykl życia produktu informatycznego. Zalety i wady modelu wodospadowego|waterfall]]. Jest planowany z góry, etapy postępują po sobie, dobrze działa w projektach przewidywalnych, ale jest nieelastyczny i może uniemożliwiać równoległe testowanie przez co błędy wychodzą później. Zwinne metodologie to takie, w których podejście jest iteracyjne. Projekt dzielony jest na sprinty (najczęściej 2-tygodniowe) i na taki okres określany jest plan i wymagania. Duży nacisk stawia się na komunikację z klientem i częste zmiany i dostosowanie. Minusem takiego podejścia jest dużo spotkań (tzw. ceremonii scrumowych) i często potrzeba doszkalania pracowników. Metody szczupłe polegają na eliminacji marnowania czasu. Skupiają się na przynoszeniu wartości i minimalizmie procesowym. Dobrze sprawdzają się do dostarczania MVP (Minimal Viable Product). Kanban to metoda, która opiera się tak naprawdę na tablicy z zadaniami. Są zadania do zrobienia, zadania w trakcie i zadania zrobione. Głównym założeniem jest robienie tego co jest do zrobienia i niczego innego oraz ograniczenie rzeczy nad którymi jednocześnie się pracuje. Jest to podejście zwinne, ale różni się od Scruma bardziej szczupłą metodologią. Czasem wprowadza się pośrednie metody jak Scrumban.
# 49. Zastosowanie metod szczupłych (Lean) do wytwarzania oprogramowania
Lean wywodzi się z Toyoty, ale został zaadaptowany do wytwarzania oprogramowania. Jego głównym celem jest eliminowanie marnotrawstwa i skupienie się na dostarczaniu wartości dla klienta. W praktyce oznacza to tworzenie tylko niezbędnych funkcji, szybkie dostarczanie MVP, częste wydania, testy jednostkowe, automatyzację procesu i podejmowanie decyzji dopiero wtedy, kiedy są naprawdę potrzebne. Lean zachęca do pracy w małych zwinnych zespołach, które mają dużą autonomię. Świetnym zastosowaniem są nowe projekty (np. startupy), które dzięki podejściu Lean mogą stworzyć pierwszą wersję aplikacji w krótszym czasie i z mniejszym nakładem finansowym, a dzięki opinii klientów rozwijać tylko to co przynosi wartość użytkownikowi.

# 50. Zarządzanie ryzykiem w projekcie informatycznym
Ryzyko to **możliwe** przyszłe zdarzenie, które może wpłynąć na projekt. W informatyce dotyczy to na przykład opóźnień, błędów, zmian wymagań czy problemów z bezpieczeństwem. Zarządzanie ryzykiem polega na kilku etapach:
1. Identyfikacja ryzyk - analiza co może pójść nie tak
2. Analiza ryzyk - ocena prawdopodobieństwa i skutków każdego ryzyka
3. Priorytetyzacja - skupienie się najpierw na ryzykach o wysokim wpływie i dużym prawdopodobieństwie
4. Planowanie reakcji - na przykład:
	1. unikanie (zmiana planu by ryzyko nie wystąpiło)
	2. ograniczanie (podjęcie metod, które mogą zabezpieczyć przed tym ryzykiem)
	3. akceptacja (pogodzenie się z ryzykiem)
	4. przeniesienie (przeniesienie ryzyka na kogoś innego, na przykład cloud providera, albo kontraktora)
5. Monitorowanie i przegląd - czy ryzyka się zmieniają, czy wystąpiły i czy pojawiły się nowe.
Praktycznym przykładem może być: Identyfikacja ryzyk, spisanie ich, ocena każdego pod kątem prawdopodobieństwa i skutków, posortowanie ich wedle obu tych wartości, a następnie zaplanowanie na nie reakcji, oraz cykliczne powtarzanie tego procesu. 
