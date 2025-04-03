# 1. Instrukcje sterujące w językach programowania
Takie słowa które sterują przebiegiem programu jak if, else, switch, go to, return, while, for itp. Zarządzają one tym jak postępuje kod i co się kiedy wykonuje. Można tutaj trochę opisać te instrukcje co robią i kiedy się ich używa. Nie wszystkie słowa kluczowe są instrukcjami sterującymi na przykład `override` jest słowem kluczowym w C# ale nie steruje przebiegiem programu w sensie logiki wykonywania krok po kroku.
# 2. Przeciążanie (overloading) i przesłanianie (overriding) na przykładzie wybranego języka programowania
Overloading polega na stworzeniu wielu instancji tej samej metody, które różnią się tym co przyjmują i/lub tym co zwracają i/lub body metody. Pozwalają one na przykład stworzyć metodę `Add(int a, int b) int { return a + b;}` oraz `Add(float a, float b, float c) float { return a + b + c;}` (idk czy tak się w C# to pisze ale o to mniej więcej chodzi). Dzięki temu możemy wywołać metodę o tej samej nazwie i takiej samej lub podobnej funkcjonalności na różnych typach. Overriding jest wtedy kiedy mamy typ bazowy, który zawiera definicję jakiejś metody, a w typie który dziedziczy nadpisujemy tą metodę inną. Możemy na przykład mieć typ zwierzę, które ma metodę `Dzwiek()` wypisującą na ekranie *“zwierzę wydaje dźwięk”*. Następnie tworzymy typ kot który dziedziczy po zwierzęciu, ale nadpisuje metodę `Dzwiek()` swoją własną definicją, która zwraca *“miau”*.
# 3. Dziedziczenie i polimorfizm na przykładzie wybranego języka programowania
Dziedziczenie polega na tworzeniu typów, które zawierają pewne deklaracje, definicje oraz wartości domyślne, a następnie tworzone są inne metody, które dziedziczą po nich wszystko czego same nie nadpiszą. Pozwala to na tworzenie typów bazowych, które później rozszerzane są o potrzebną funkcjonalność. Polimorfizm pozwala na stworzenie interfejsu, który inne typy mogą implementować. Interfejs to taki zbiór wymagań. Aby zaimplementować interfejs typ musi spełniać wszystkie wymogi interfejsu. Dzięki temu każdy typ który spełnia wymogi danego interfejsu może być użyty w miejscu gdzie oczekiwany jest ten interfejs. Pozwala to na pisanie kodu, który może być wywołany przy użyciu wielu różnych typów jeśli wszystkie spełniają wymagania interfejsu.
# 4. Omów j porównaj kolekcje: kolejki LIFO, FIFO oraz listę jedno i dwukierunkową
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
# 19. Algorytmy sortowania
# 20. Zadania, funkcje i protokoły warstwy sieciowej modelu OSI/ISO
# 21. VLAN - funkcje, zadania i zastosowanie
# 22. Architektury sieciowe klient-serwer a peer-to-peer
# 23. Technologie i rozwiązania dostępowe do sieci LAN
# 24. Przykłady i zastosowanie adresowania warstwy łącza danych oraz warstwy sieci w sieciach typu Ethernet
# 25. Reguły dotyczące wyboru tzw. najlepszej trasy do sieci docelowej dla routingu statycznego
# 26. Przykłady realizacji koncepcji izolacji ruchu w sieciach dla warstwy łącza danych oraz warstwy sieci
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
# 35. Istota i rodzaje podpisu elektronicznego
# 36. Metody szyfrowania: steganografia, metody podstawiania, metody transpozycyjne
# 37. Systemy IDS oraz IPS. Zalety i wady obydwu rozwiązań
# 38. Wyjaśnij pojęcia: kryptologia, kryptografia i kryptoanaliza
# 39. Planarność i kolorowanie grafów
# 40. Algorytm szyfrowania RSA
# 41. Charakterystyka i wykorzystanie wzorców projektowych
# 42. Omów kreacyjne, strukturalne i behawioralne wzorce projektowe
# 43. Zasady projektowania SOLID
# 44. Wyjaśnij dlaczego JavaScript jest językiem skryptowym, funkcyjnym, proceduralnym i obiektowym
# 45. Kaskadowość i dziedziczenie w języku CSS
# 46. Istota semantyczności języka HTML (opisz i podaj przykłady dobrych praktyk)
# 47. Optymalizacja stron WWW
# 48. Metody zarządzania projektami: klasyczna (proaktywna), zwinna (Scrum) i szczupła (Kanban)
# 49. Zastosowanie metod szczupłych (Lean) do wytwarzania oprogramowania
# 50. Zarządzanie ryzykiem w projekcie informatycznym