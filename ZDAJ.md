# INZ_E PREP
https://drive.google.com/file/d/1fydGKsEFeQmkpRct0koksVJ4cFCKkpAU/view
## <b>Pytania kierunkowe</b>
## 1. Złożoność czasowa i pamięciowa algorytmów
https://www.geeksforgeeks.org/time-complexity-and-space-complexity/
### złożoność obliczeniowa
- technika porównywania ze sobą algorytmów pod różnymi względami
### notacje asymptotyczne
https://www.geeksforgeeks.org/types-of-asymptotic-notations-in-complexity-analysis-of-algorithms/ \
Wyróżnia się złożoność pesymistyczną, średnią oraz optymistyczną
- big-O
    - górne ograniczenie złożoności algorytmu -> określa się nią złożoność <b>pesymistyczną</b>
- $\Omega$ (Omega)
    - ograniczenie dolne złożoności algorytmu -> określa złożoność <b>optymistyczną</b>
- $\Theta$ (Theta) \
    - ogranicza złożoność algorytmu od dołu i od góry - jest więc używana do opisywania złożoności <b>średniej</b>
    - zostawia się tylko czynnik najwyższego rzędu bez stałych\
    - np g(n)=2n^3+n należy do Theta(n^3)
- little-o, $\omega$
    - tak jak podstawowe wersje, ale w definicjach '>' -> '>=' , '<' -> '<='\
    np. f(x) należy_do o(g(x)) <=> A(x>n_0) A(c>0) f(n) <<b>=</b> c*g(n)
#### własności notacji asymptotycznych
- f(n) nalezy_do O(g(n)) => a*f(n) nalezy_do O(g(n))
- f(n) nalezy_do O(g(n)) , g(n) nalezy_do O(h(n)) => f(n) nalezy_do O(h(n)) // przejściowe
#### klasyfikacja złożoności
- stała O(1)                        // zsumowanie n kolejnych liczb naturalnych
- logarytmiczna O(logn)             // szukanie elementu w drzewie binarnym
- liniowa O(n)                      // szukanie elementu w tablicy
- liniowo-logarytmiczna O(nlogn)    // niektóre algorytmy sortujące (quicksort)
- wielomianowa O(n^x)               // czy któraś trójka z n integerów sumuje się do x
- wykładnicza O(x^n)                // rekursja (fibonacci)
- O(n!), superwykładnicza O(n^n)    // generowanie permutacji listy, <i>szukanie drzewa ewolucyjnego łączącego sekwencje DNA wymagające jak najmniejszej ilości mutacji jednonukleonowych</i>
### złożoność czasowa
- opisuje czas wykonania danego algorytmu jako funkcję rozmiaru danych wejściowych
- wyraża się w liczbie operacji elementarnych (wpływających bezpośrednio na czas wykonania) programu
### złożoność pamięciowa
- opisuje ilość pamięci wymaganą do wykonania danego algorytmu (nie licząc danych wejściowych)
## 2. Podstawowe struktury danych i algorytmy do ich przetwarzania
https://www.geeksforgeeks.org/data-structures/
- tablica
    - wyszukiwanie, dodawanie i usuwanie elementów (w posortowanej i nie)
    - sortowanie
- lista (jedno-, dwukierunkowa, xorlista)
    - dodawanie, usuwanie, szukanie elementów, odwracanie, merge posortowanych
- kolejka
    - FIFO, push, pop, typowo implementowana za pomocą listy
    - kolejka priorytetowa (APC w windowsach) -> ustawianie el. o danym priorytecie w odpowiednie miejsce
    - deque (double ended queue) -> [ push | pop ] [ front | back ]
- stos
    - LIFO, push, pop
    - odwrócona notacja polska ( "3 4 + 5 *" === "(3 + 4) * 5" )
- sterta (kopiec)
    - uporządkowane drzewo (binary heap, fibonacci heap)
    - typowo przechowywana w formie tablicy (kolejne piętra od lewejdo prawej)
    - heap sort (utworzenie drzewa i porządkowanie go (heapify) do postaci kopca)
    - insert jest w czasie log(n): dodajemy na końcu i wołamy heapify w górę
    - delete też jest log(n): podmieniamy usuwany element na inf i robimy podmianki od roota w dół log(n)
- graf
    - Prim (minimalne drzewo spinające)
        1. wybierz węzeł początkowy
        2. wybierz węzeł przylegający do drzewa o najtańszej krawędzi z dostępnych (i tę krawędź)
        3. itd. aż w drzewie będą wszystkie węzły
    - Dijkstra (najkrótsza ścieżka)
        1. każdy węzęł ma przypisaną wartość (najmniejsza suma wag krawędzi, początkowo INF)
        2. idąc od węzła początkowego dodaje się kolejne węzły do zbioru, tworząc drzewo
        3. po drodze updatuje się wartości węzłów jak się znajdzie krótsze dojście i dodaje się kolejne
        4. aż wszystkie węzły będą już w drzewie
- drzewo
    - BFS - pcha się na kolejkę wszystkie dzieci i obsługuje kolejny element z kolejki
    - DFS
        - w przypadku drzewa: zwykła rekursja
        - w przypadku grafu należy uważać na cykle (oznaczać elementy jako odwiedzone)
- hashtablica
    - indeks w tablicy = hash(wartość elementu)
    - w przypadku kolizji zamiast elementów można np. w tablicy trzymać listy
    - znaczne przyspieszenie dostępu do danych (stały czas dostępu)
        - wstawianie, usuwanie, wyszukiwanie
- awaryjnie: macierze gęste i rzadkie
## 3. Nowoczesne platformy programowania obiektowego
### JAVA
```diff
+ przenośna (niezależna od systemu operacyjnego)
+ wspiera przetwarzanie rozproszone
+    > np. RMI (Remote Method Invocation) pozwala na dostęp do obiektów na kilku systemach
+    ^ działa na zasadzie serwera i klientów, serwer ma rejestr udostępnionych obiektów
+ języki działające na JVM (Java Virtual Machine):
+   groovy, php, ruby, python (jython), kotlin, javascript
- stosunkowo wolna - wszystkie większe struktury trafiają na stertę
+ ale za to nie ma wskaźników - to spowalnia ale daje większe bezpieczeństwo
```
### .NET
```diff
+ opensource silnie rozwijany przez Microsoft
+ też działa na różnych systemach (jeśli mają CLR - jest implementacja dla linuxów i maców)
+ też wspiera przetwarzanie rozproszone
+   > framework (! szkielet, zrąb !) .Net Remoting
+ języki działające w CLR (Common Language Runtime):
+   C#, cpp, F#, python (IronPython), swift
+ szybszy bo wspiera structs, które mogą trafić na stos (cache)
- kosztowne migrowanie aplikacji
```
### both
- JIT - Just in Time compilation
- ujednolicenie typów danych
    - JAVA: np. pisanie modułów cpp w androidzie wymaga użycia typów zgodnych z platformą
    - .NET: Common Type System
- garbage collection
    - JAVA: minor, major GC - druga ma większy wpływ na wydajność
    - .NET: działa w tle, dzieli obiekty na generacje
    - obie platformy pozwalają na użycie destruktorów (java: void finalize())
- Exception handling
    - obie platformy udostępniają bazową klasę wyjątków
    - .NET nie pozwala na żadne skoki z bloku "finally"
    - W javie blok finally może popsuć obsługę wyjątku, nie ma dostępu do obiektu wyjątku
    - catch all:
        - JAVA: lepiej używać zbiorczego catch (Throwable T)
        - .NET: catch {}
## 4. Porównanie sieci LAN i WAN
https://drive.google.com/drive/folders/18jRDb6gjQo-uooKyRKp8BB5lRk7X5uMF
### LAN - Local Area Network
- niewielki zasięg: biuro, budynek
- liczba urządzeń od kilku do kilkuset
- duża szybkość transmisji
- obsługa organizacji, sieci domowe
- dostęp urządzeń w sieci do drukarek, internetu
### WAN - Wide Area Network
- duży zasięg: kraj, kontynent, świat
- liczba urządzeń od kilkuset do miliardów
- dostęp do odległych baz danych i systemów przetwarzania informacji
- często łączy kilka LANów należących do jednej organizacji, np. poprzez VPN
    - VPN - wirtualizuje prywatne połączenie przez sieć publiczną: szyfruje komunikację i zapewnia anonimowość
    - serwer VPN zestawia bezpieczny tunel VPN pomiędzy klientem a docelowym serwerem
    - to wprowadza dodatkowe opóźnienia
- wykorzystuje różne technologie i typowo właściciele odległych LANów nie mają kontroli nad połączeniem między nimi
### LAN vs WAN
```diff
+ LAN
- WAN
+ małe opóźnienia - odległość, utrzymywanie infrastruktury, podatność na uszkodzenia
- duże opóźnienia - większe odległości, większa ilość hopów, zdarzenia losowe na łączu
+ bezpieczeństwo - łatwość monitorowania, łatwość i koszt wdrażania bezpiecznych rozwiązań
- bezpieczeństwo - utrudnione utrzymywanie bezpieczeństwa, dużo wektorów ataku
+ koszty duużo mniejsze ofc (projektowanie, tworzenie, utrzymywanie)
```
## 5. Metody dostępu do medium transmisyjnego w lokalnych sieciach komputerowych
https://drive.google.com/drive/folders/18jRDb6gjQo-uooKyRKp8BB5lRk7X5uMF \
https://www.geeksforgeeks.org/multiple-access-protocols-in-computer-network/
- Medium transmisyjne - 
1. ALOHA
    - pure: stacja czeka na potwierdzenie odbioru danych i czeka randomo długo przed ponowieniem
    - slotted: czas jest dzielony na sloty (szczeliny), można nadawać tylko na początku slotu, \
    co zmniejsza ryzyko kolizji
2. CSMA
    - Carrier Sense Multiple Access
        - stacja nadaje tylko jeśli odczyta, że medium jest wolne
        - pozostaje ryzyko kolizji (czas propagacji)
        - różne strategie w razie zajętego medium: czekanie randomowego czasu, aktywne czekanie, hierarchia
    - CSMA/CD - Collision Detection
        - stacje przerywają transmisję w przypadku wykrycia kolizji
        - powoduje wysokie opóźnienia przy wysokim obciążeniu łącza
    - CSMA/CA - Collision Avoidance
        - podwójne sprawdzanie czy medium jest wolne (ramka pytająca -> ramka potwierdzająca)
        - czekanie na potwierdzenie odbioru -> retransmisja
### podział pasma w dziedzinie:
3. częstotliwości (FDMA) 
    - każda stacja nadaje na swojej przydzielonej częstotliwości
4. czasu (TDMA)
    - wymaga synchronizacji - każdej stacji przysługują określone szczeliny czasu
5. kodu (CDMA) // używana raczej w sieciach komórkowych
    - każda stacja komunikuje się w zakresie współdzielonego medium własnym językiem
    - stacje mówiące różnymi językami nie przeszkadzają sobie
6. Token Ring
    - protokół bezkolizyjny - stacje przekazują sobie na określony czas token pozwalający na nadawanie
## 6. Infrastruktura klucza publicznego – architektura oraz sposoby wykorzystania
https://drive.google.com/drive/folders/18jRDb6gjQo-uooKyRKp8BB5lRk7X5uMF \
https://www.geeksforgeeks.org/public-key-infrastructure/
### Klucz prywatny
https://www.geeksforgeeks.org/difference-between-private-key-and-public-key/
- klucz utrzymywany w sekrecie, potwierdzający tożsamość użytkownika systemu
- służy do szyfrowania danych -> ich odczytanie jest możliwe za pomocą klucza publicznego
- oraz do odszyfrowywania danych zaszyfrowanych kluczem publicznym
### Klucz publiczny
- klucz udostępniony publicznie, pozwalający na komunikację z nadawcą posługującym się kluczem prywatnym
### Certyfikat cyfrowy
- zapobiega atakom Man-in-the-Middle (potwierdza przynależność klucza publicznego)
- zawiera informacje o kluczu publicznym oraz jego właścicielu
### Certifivate Authority
- ciało wydające i weryfikujące klucze publiczne wraz z certyfikatami
- generuje pary kluczy i certyfikaty
- unieważnia certyfikaty w razie podejrzanego zachowania
- każdy CA ma swój certyfikat wydany przez CA wyższe w hierarchii
    - root CA jest offline przez prawie cały czas
- proces
    1. wydaje parę kluczy oraz CRS (Certificate Signing Request)
    2. właściciel podpisuje CSR kluczem prywatnym
    3. CA wydaje certyfikat
### Zastosowania
- szyfrowanie komunikacji
- podpisy cyfrowe
- uwierzytelnianie użytkowników
- zabezpieczanie sesji internetowych (TLS - Transport Layer Security)
## 7. Podać różnice w implementacji obiektowości w kilku wybranych językach programowania
### Cpp
- stanowi rozwinięcie C o implementację paradygmatu programowania obiektowego
- nie jest w pełni obiektowy (można napisać program bez obiektów, niezależna funkcja main)
- KLASY: umożliwiają ukrywanie pól i metod, abstrakcję oraz dziedziczenie
- DZIEDZICZNIE: możliwe wielokrotne i wielopoziomowe, dziedziczy się pola i metody (w tym konstr, destr)
- ENKAPSULACJA: klasy zawierają pola oraz metody (enkapsulacja danych i funkcji w obiekcie)
- HERMETYZACJA: specyfikatory dostępu (pola i metody), pliki nagłówkowe
- ABSTRAKCJA: klasy abstrakcyjne, mają funkcje abstrakcyjne (niezaimplementowane), nie mogą być instancjowane
- POLIMORFIZM:
    - statyczny: przeciążanie metod (różne parametry -> rozwiązaywany w czasie kompilacji)
    - dynamiczny: nadpisywanie metod (dopiero w czasie wykonywania wiadomo która będzie wykonana)
### java
- też nie jest czysto obiektowa bo <i>typy prymitywne</i> -> ALE są odpowiednie klasy (int->Integer)
- KLASY:
    - wszystkie dziedziczą po klasie Object -> wspólne metody np. toString()
- DZIEDZICZENIE: nie ma wielokrotnego (-> interfejsy), jest wielopoziomowe
- ENKAPSULACJA: w klasie są pola i metody
- HERMETYZACJA: zarządzanie dostępem po składników klasy (default, protected, private, public), get, set
- ABSTRAKCJA: klasy abstrakcyjne, interfejsy -> nie można tworzyć ich obiektów
- POLIMORFIZM: tak jak w Cpp (statyczny, dynamiczny)
### python
- całkowicie obiektowy - klasy (tak jak w SmallTalku) i metody są obiektami
- KLASY: najprostsza konstrukcja, domyślnie wszystkie pola są publiczne
- DZIEDZICZENIE: wielokrotne, wielopoziomowe, nadpisywanie metod i pól
- ENKAPSULACJA: klasy mogą mieć pola i metody
- HERMETYZACJA: ograniczanie dostępu poprzez konwencje nazewnictwa: _symbol, __symbol (klasa._klasa__symbol)
- ABSTRAKCJA: metody abstrakcyjne ze słowem pass -> można utworzyć obiekt ale wołanie metody -> wyjątek
- POLIMORFIZM: polimorfizm funkcji (len(str,list,dict)) - pod spodem są metody magiczne (np. def __len__())
    - NIE MA statycznego polimorfizmu w tradycyjnym sensie -> metoda może przyjmować dynamicznie typowane argumenty
## 8. Modele danych stosowane w systemach informacyjnych
s.45 https://drive.google.com/file/d/1fydGKsEFeQmkpRct0koksVJ4cFCKkpAU/view
- ### system informacyjny - wielopoziomowa struktura pozwalająca na przetwarzanie informacji za pomocą procedur i modeli
- ### system informatyczny - skomputeryzowana część systemu informacyjnego
- ### model danych - zbiór specyfikacji opisujący strukturę danych (dozwolone w modelu obiekty i związki) i dozwolone operacje <br><br> wyliczanka:
    1. Prosty - pojedyncza tablica, podobne pola w kolumnie, powiązane pola w wierszu (np. csv)
    2. Hierarchiczny - dane w strukturze drzewiastej, rekordy na tym samym poziomie są uporządkowane
        - usunięcie węzła nadrzędnego skutkuje usunięciem węzłów podrzędnych
        - przykład: system plików // except linki symboliczne itd.
    3. sieciowy - dane są opatrzone identyfikatorami / adresami
        - referencje / wskaźniki na inne dane tworzą sieć (<b>graf</b>)
        - wady: poziom programowania obniżony do fizycznej organizacji danych
    4. relacyjny
        - relacja - podzbiór iloczynu kartezjańskiego zbiorów danych - tabela jest reprezentacją relacji
        - kolumny tabeli: atrybuty encji
        - wiersze tabeli: krotki iloczynu (zbiory atrybutów) // tabela ~ klasa, krotka ~ obiekt
        - komórki tabeli: pola (dane niepodzielne przy zachowaniu spójności logicznej)
        - klucz główny, klucz obcy, krotności związków
    5. obiektowy
        - odzwiercidla obiektowość danych z punktu widzenia aplikacji
        - wprowadza hermetyzację, polimorfizm, typy danych spójne z warstwą aplikacji
    6. wielowymiarowy
        - stosowany w hurtowniach danych
        - adaptacja modelu relacyjnego w 3D pozwalająca na bardziej złożone przetwarzanie danych
        - tabele faktów: wymiary = atrybuty opisowe, miary = atrybuty liczbowe
    7. sieci semantyczne
        - w klasycznych modelach danych rekordy odzwierciedlają rzeczywiste obiekty dopiero po odpowiedniej interpretacji, która jest kosztowna
        - w sieciach semantycznych znaczenie rekordu wynika z jego połączeń z innymi danymi (z kontekstu (<b>ontologii</b>))
## 9. Pojęcie systemu wbudowanego, jego cechy oraz obszary zastosowań
https://www.geeksforgeeks.org/introduction-of-embedded-systems-set-1/
### System wbudowany (embedded) - system komputerowy dedykowany do określonych zadań, złożony z dobranych komponentów sprzętowych.
#### konkretne zadanie, mały rozmiar, mały koszt, małe zużycie energii, automatyczne działanie, niezawodność
#### można je programować różnymi językami - wersje C, Cpp, Javy, pythona na systemu wbudowane <br> (bo np. nie ma możliwości działania full ass JVM na płytce)
- ### mikroprocesor 
    https://www.tutorialspoint.com/difference-between-microprocessor-and-microcontroller
    - urządzenie wykonujące instrukcje i przetwarzające dane
    - składa się tylko z ALU (jednostka arytmetyczno logiczna), CU (Control Unit) i ew. małej pamięci cache
    - pozostałe komponenty takie jak pamięć, wejście, wyjście są na zewnątrz
    - typowo mikroprocesory stanowią część większego systemu komputerowego
- ### mikrokontroler
    - system złożony z mikroprocesora, pamięci (RAM, ROM, EEPROM), porty I/O w obrębie jednej płytki
    - mały, względnie niedrogi sprzęt zdolny do obsługi takich urządzeń jak pralki czy mikrofalówki
### Klasyfikacja systemów wbudowanych
https://www.geeksforgeeks.org/classification-of-embedded-systems/
- SW czasu rzeczywistego - krytyczne zadania, niezawodność, wykonywanie zadań w określonym krótkim czasie
- samodzielne - działające autonomicznie, np. mp3, kalkulatory
- sieciowe - połączone do sieci, np. systemy antywłamaniowe
- mobilne - przenośne, wymagające mniej zasobów, np. znowu mp3
### Przykłady
- pralki, zmywarki, lodówki
- telewizory
- drukarki
- kamery
- mp3
- kalkulatory
- sprzęt medyczny
## 10. Cykle życia oprogramowania (modele wytwarzania oprogramowania)
https://www.geeksforgeeks.org/top-8-software-development-models-used-in-industry/ \
modele wytwarzania oprogramowania - organizacja procesu wytwarzania systemu, podział na etapy, kryteria przejścia między etapami, praktyki procesu wytwarzania
- ### klasyczny (kaskadowy)
    - etapy:
    1. planowanie
    2. analiza
    3. projektowanie
    4. implementacja
    5. testowanie i walidacja
    6. utrzymanie
    - kolejny etap zaczyna się po zakończeniu poprzedniego
    - błędy w danym etapie skutkują powrotem do niego i ponownym przejściem przez następne
    ```diff
    + obejmuje cały cykl życia
    + sprawdzony
    + ustandaryzowany
    - konieczność określenia wszystkich wymagań z góry
    - ograniczony kontakt z użytkownikiem
    - błędy są kosztowne
    ```
- ### model V
    #### przypisuje etapom modelu klasycznego fazy testowania
    - wymagania -> testy akceptacyjne (testowanie w środowisku użytkownika, w kontekście innych systemów)
    - model logiczny (analiza) -> testy systemowe (walidacyjne) (cała funkcjonalność systemu)
    - projekt systemu -> testy systemowe i integracyjne (współpraca modułów systemu)
    - projekt szczegółowy -> testy jednostkowe
    - programowanie
    ```diff
    + wysoka jakość produktu
    + niższe koszty utrzymania
    - narzut kosztów (pracy)
    - też słaby przy zmiennych wymaganiach
    ```
- ### model przyrostowy
    #### proces wytwarzania podzielony na przyrosty złożone z tych samych faz <br> w kolejnych przyrostach spełnia się kolejne porcje wymagań klienta <br> po każdym przyroście można przedstawić efekty klientowi
    - fazy jednego przyrostu: projektowanie, programowanie, testowanie, wdrożenie
    ```diff
    + można w obrębie jednego przyrostu skupić się na istotniejszych wymaganiach
    + kontakt z klientem pomiędzy przyrostami
    + ocena postępów
    - dodatkowy nakład pracy menadżerskiej
    - wymagania powinny być jasno określone
    ```
- ### model iteracyjny
    #### w kolejnych iteracjach powtarza się cały proces, spełniając wymagania dynamicznie na podstawie oceny klienta
    ```diff
    + wczesne wykrywanie błędów
    + informacja zwrotna użytkowników
    - dużo zmian w kodzie w razie zmieniających się wymaganiań
    - trudność określenia postępów
    ```
- ### model spiralny
    #### łączy cechy modelu klasycznego i iteracyjnego <br> etapy modelu klasycznego = fazy modelu spiralnego
    - fazy
    1. planowanie (wymagania, ocena klienta)
    2. analiza ryzyka
    3. konstrukcja (programowanie, testy)
    4. ocena użytkownika
    ```diff
    + dodawanie i zmienianie wymagań w kolejnych cyklach
    + analiza ryzyka w każdym cyklu
    + ocena użytkownika
    - ciężki i kosztowny w zarządzaniu
    - dobry dla dużych i złożonych projektów
    ```
- ### model prototypowy
    #### pokazuje się klientowi prototypy
    ```diff
    + dobry jak nie ma szczegółowych wymagań tylko ogólny cel
    - kosztowny jak klientowi nie podoba się prototyp
    - szybkie przygotowanie prototypu może być niedokładne
    ```
- ### model zwinny
    https://www.geeksforgeeks.org/software-engineering-agile-development-models/
    #### kombinacja modeli iteracyjnego i przyrostowego <br> zwinność = dopasowywanie się do zmiennych wymagań klienta również w zaawansowanej fazie wytwarzania
    - każdy przyrost wykonuje się w czasie jednej iteracji
    - iteracje są małe dla uproszczenia zarządzania i zwiększenia kontaktu z klientem i interesariuszami
    - planuje się tylko jedną iterację do przodu
    - małe zespoły -> ścisła współpraca, komunikacja
    - metodyki \
        https://www.xpand-it.com/blog/top-5-agile-methodologies/
        - scrum - sprinty, codzienne spotkania
        - kanban - wszystkie zadania na tablicy
        - extreme programming - stawia na prostotę, programowanie w parach (rozwój programistów)
### zasady SOLID
- S - single responsibility (jedna klasa - jedna odpowiedzialność, jeden powód do zmiany)
- O - Open for extension / Closed for modification
- L - Liskov Substitution - podstawienie klasy dziedziczącej pod bazową nie powinno nic psuć
- I - Interface segregation - rozbijanie złożonych interfejsów na prostsze, żeby klasy implementowały tylko potrzebne metody
- D - Dependency inversion - moduły wysokopoziomowe powinny polegać na abstrakcji (nie bezpośrednio na niskopoziomowych)
## 11. Zasady modelowania dla konstrukcji relacyjnych baz danych
1. określenie zbiorów encji (encja ~ obiekt, zbiór encji ~ klasa)
2. sprecyzowanie atrybutów encji (typy proste)
3. zdefiniowanie klucza głównego identyfikującego encję (minimalny podzbiór atrybutów albo nowy sztuczny atrybut)
4. określenie związków pomiędzy encjami (liczebności, opcjonalność, atrybuty związku, związki is_a)
5. typowo związki *:* modeluje się jako osobne encje
### postaci normalne
https://www.geeksforgeeks.org/normal-forms-in-dbms/
- 1NF - atomiczność atrybutów relacji (komórka tabeli - typ prosty)
- 2NF - 1NF + pozostałe atrybuty niepełnie zależne od klucza głównego (atrybuty klucza głównego nie mogą wynikać z pozostałych atrybutów, pozostałe atrybuty nie mogą wynikać wprost z klucza głównego) <br> jeśli jakiś atrybut jest w pełni zależny od klucza głównego, należy umieścić go w innej tabeli
- 3NF - 2NF + brak przejściowych zależności atrybutów non-prime (np. jak jest łańcuszek zależności id -> województwo -> kraj to należy utworzyć nową tabelę)
- Boyce-Codd NF - 3NF + każdy zbiór atrybutów, który mógłby identyfikować encję (determinant) jest kluczem kandydującym <br> atrybuty muszą być zależne od super kluczy (zbiór atrybutów unikalnie identyfikujący krotkę)
- 4NF - BCND + dopuszczana jest tylko jedna zależność wielowartościowa <br> zależność wielowartościowa: dwa atrybuty nie są ze sobą powiązane ale są z jakimś innym
- 5NF - po lewej stronie zależności typu join musi być klucz kandydujący
## 12. Opis wybranej metodyki wytwarzania oprogramowania
### SCRUM - metodyka zwinna <br> przebieg:
1. przygotowanie wymagań jako user stories -> backlog produktu
2. planowanie sprintu -> backlog sprintu
3. sprint (typowo 2tyg do miesiąca) -> wydanie produktu
4. ocena sprintu (wydania produktu z dodanymi funkcjonalnościami z backlogu sprintu)
5. retrospektywa (co poszło dobrze, co poszło źle, gry)
6. planowanie kolejnego sprintu (pkt. 2)
### Role
- Scrum Master - odpowiada za sprawny przebieg procesu wytwarzania, produktywność zespołu, spotkania
- Product Owner - odpowiedzialny za backlog produktu - wyjaśnia, nadzoruje zrozumienie, Scrum Master go enforsuje
- drużyna - samoorganizująca się, członkowie o różnych kompetencjach
    - 5-9 osób
    - sprawna interakcja, komunikacja i współpraca
    - codzienne spotkania (daily scrum) -> burn-down chart szacuje ile pracy zostało (oceniany przez product ownera przynajmniej podczas oceny sprintu)
## 13. Budowa systemów plików w systemach operacyjnych
### 13.1 FAT
- metoda listowa przydziału miejsca na dysku
- BPB (BIOS Parameter Block) -> rozmiar i ilość tablic FAT, położenie i ilość plików w katalogu głównym
#### tablica FAT
- lista pustych elementów i numerów klastrów, do których należą pliki
- wpisy czy dany klaster jest wolny i zawierają wskaźniki na kolejny klaster
- pierwszy wpis należy do katalogu głównego
#### plik w katalogu
- nazwa (krótka), atrybuty, nr początkowej pozycji w tablicy FAT (zarazem nr klastra)
- krótka nazwa to 8+3 znaki, atrybuty mogą mówić że kolejne pliki to nie pliki tylko kontynuacja dłuższej nazwy
- usunięcie pliku to ustawienie pierwszego bajtu nazwy
### 13.2 ext
- metoda indeksowa przydziału miejsca na dysku
- partycje ext dzieli się na zgrupowane bloki
#### superblok
- metadane o blokach w grupie (w tym wolne bloki), i-węzłach
#### tablica i-węzłów
- jest 1 i-węzęł na plik
- struktura i-węzła:
    - położenie i rozmiar pliku, typ (np. katalog)
    - NIE ma przypisanej nazwy - kilka plików o różnych nazwach może być jednym plikiem
    - lista wskaźników na bloki (bezpośrdenie, 1x,2x i 3xpośredni - pośrednie mają odwołania do kolejnych bloków)
    - żeby dojść do danego bajtu wystarczy wyliczyć numer bloku (nr bajtu / rozmiar bloku)
- tablica i-węzłów globalna na początku partycji, ładuje się ją do pamięci
#### katalog
- działa jak zwykły plik, ale jego zawartość to nazwy plików i numery ich i-węzłów
    - można ten sam i-węzeł przypisać do kilku nazw - to będzie ten sam plik dostępny z kilku miejsc
- rekordy plikowe różnej długości
#### journaling
- pozwala na odtwarzanie operacji na plikach
- jest kilka poziomów, np. logowanie danych + metadanych albo samych metadanych
- pojawił się w ext3 i tj zmiana względem ext2
#### edytowanie pliku:
- cały plik się bierze do RAM-u i potem zapisuje jak nowy plik
### 13.3 NTFS
- metoda listowo-indeksowa przydziału miejsca na dysku
- każdy blok (w tym tablica Mater File Table (MFT)) jest plikiem
- zalety: bezpieczeństwo, olbrzymie pliki, zarządzanie dostępami do plików
#### partycja NTFS
- Volume Boot Record (Logical Cluster Number = 0), MFT, pliki systemowe, obszar danych
- VBR zawiera BPB tak jak w FAT
#### Master File Table
https://www.geeksforgeeks.org/what-is-a-master-file-table/
- trzyma się dwie kopie (niekoniecznie spójne)
#### rekord plikowy
- nagłówek rekordu: rozmiar rekordu, typ pliku (np. katalog)
- lista atrybutów: nazwa, rozmiar (zaalokowany i faktyczny), dane, indeks (rezydentny i nierezydentny do katalogów)
    - jak zawartość się nie zmieści w atrybucie rezydentnym DATA, wpisuje się do niego listę klastrów
        - Virtual Cluster Number - nr z punktu widzenia pliku
        - Logical Cluster Number - nr klastra na partycji
        - jak jest kilka klastrów obok siebie to jest podany pierwszy i ilość kolejnych
#### katalog
- zawiera indeksy plików w MFT w zbalansowanym drzewie
- katalog główny jest na konkretnej pozycji w MFT
#### dziennik transakcji
- odtwarzalność danych
## 14. Modele barw w grafice komputerowej
### model ludzki - czopki wrażliwe na różne długości fali: RGB
### modele addytywne - mieszanie światła - łączenie kolorów = sumowanie składowych // $\Sigma$ = biały, np. RGB
### modele subtraktywne - mieszanie barwników // $\Sigma$ = czarny, np. CMY
### RGB
- zgodność z ludzkim postrzeganiem
- model addytywny (światło)
- typowo zapis bajt per składowa
### HSB
- też bazuje na ludzkiej percepcji
- Hue - kolor (0-360 stopni)
- Saturation - nasycenie (rośnie na zewnątrz koła)
- Brightness (AKA Light/Value) - jasność (udział bieli, trzeci wymiar, czubek stożka jest czarny)
### CMY(K)
- subtraktywny (mieszanie barwników -> drukarki)
- barwy podstawowe Cyan, Magenta, Yellow
- K - blac<b>K</b> - poprawia jakość i tnie koszty
### CIE
- CIE - nazwa starej francuskiej komisji która to wszystko wymyśla
- ### XYZ
    - przekształcenia starszego CIE RGB (wada: ujemne wartości) oparte na właściowościach wzroku (eksperymenty)
    - jedna ze skłądowych zawiera informację o jasności
    - barwy poza widzialnym spektrum
- ### LUV
    - organizm koduje kolory jako wykluczające się pary R-G, B-Y
    - te pary koduje się jako składowe U i V
    - Lightness
- ### La\*b\*
- Lightness - jasność
    - nie skupia się na składowych tylko na postrzeganiu
    - środek kreski pomiędzy dwoma kolorami na diagrami to kolor uzyskany po ich wymieszaniu
### problem modeli technicznych - nie wszystkie barwy nasycają się jednakowo
## 15. Poziomy testowania w cyklu życia oprogramowania
### definicje
- defekt/usterka - niepoprawny krok w programie
- błąd - stan lub zachowanie programu odbiegające od oczekiwań
- awaria - brak możliwości wykoanania jakiejś funkcji programu
- debuggowanie - usuwanie defektów

### testy jednostkowe (modułowe)
- testowanie poszczególnych klas (ich funkcji) w obrębie modułu, w separacji (mocking)
- test driven development = pisanie najpierw testów jednostkowych
- przygotowywane przez autora kodu
### testy integracyjne
- integracja pomiędzy modułami (interfejsy, interakcja)
- oparte na projekcie systemu (model V)
- zalecana integracja przyrostowa zamiast skokowej (koszt późnego wykrycia błedu)
### testy systemowe
- działanie całego systemu
- oparte na modelu logicznym (analizie)
- zautomatyzowane lub wykonywane przez wydzielony zespół w warunkach przypominających środowisko docelowe
- biało/czarnoskrzynkowe (znajomość szczegółów implementacyjnych)
### testy akceptacyjne
- oparte na wymaganiach klienta
- testuje się cały proces biznesowy, scenariusze użycia
- odpowiedzialność po stronie użytkowników i interesariuszy
- testy alpha - klient w środowisku wytwórczym
- testy beta - klient w środowisku docelowym
## 16. Klasy języków programowania na wybranych przykładach
### Podział wedle paradygmatów programowania
- programowanie imperatywne - sekwencja rozkazów przetwarzających dane, np C. // nadzbiór nad strukturalnym <br> i proceduralnym
- programowanie deklaratywne - definiuje się cel, nie algorytm - opisuje się dane i żądane wyjście, np. SQL
- programowanie strukturalne - jak imperatywne w sensie wykonywania sekwencji rozkazów, ale są one ustrukturyzowane - zamiast zakazanej instrukcji goto używa się takich konstrukcji jak pętle i if'y
- programowanie proceduralne - używamy procedur (funkcji) - możliwość skoku do funkcji i powrotu
- programowanie funkcyjne - oparte na funkcjach, które powinny dla tych samych parametrów zawsze zwracać tę samą wartość <br> https://www.geeksforgeeks.org/functional-programming-paradigm/
    - przypisywanie wyniku do zmiennej nazywa się efektem ubocznym
    - czyste funkcje nie mają efektów ubocznych ani interakcji I/O
    - funkcje są deterministyczne - można zapamiętywać wyniki dla lepszych rezultatów
    - przykład: Haskell
- programowanie obiektowe: dogmaty: enkapsulacja, dziedziczenie, polimorfizm, abstrakcja
- programowanie w logice - podaje się zestaw twierdzeń logicznych, na podstawie których program przeprowadza wnioskowanie, np. prolog
### kontrola typów
- typowanie statyczne (szybkość) - C, Cpp
- typowanie dynamiczne - python, javascript
### sposób wykonywania
- kompilacja (do kodu maszynowego / pośredniego), np. c, java
- interpretacja, np. python, bash
### przeznaczenie
- skryptowe, ogólnego przeznaczenia, przetwarzanie tekstu (awk)
## 17. Zasady budowy interfejsów użytkownika systemów informatycznych
### modele interfejsów:
- model użytkownika - jak użytkownik widzi program/system; opis powinien być krótki, np. jednozdaniowy
- model programisty - jak interfejs ma działać
- model projektanta - model sugerowany użytkownikowi i zarys jego realizacji <br> łączy model użytkownika z modelem programisty
### ocena interfejsu:
- miary jakości: szybkość wykonywania zadania, łatwość nauki, możliwość cofania błędnych akcji użytkownika
- ocena subiektywna (jak mi się podoba), obiektywna (np. rytm serca <- mierzalne fakty)
- ogólna/całościowa, szczegółowa
- w oparciu o użytkownika, specjalistę lub teorię
### oCeNa hEuRyStYcZnA
- powinien być widoczny stan (loading...) oraz tryb (np. rysowanie w paincie) systemu
- używanie języka użytkownika (mapować -> odwzorować)
- swoboda wykonywania działań: robię rzeczy w takiej kolejności jak chcę i mogę się cofać
- spójność (podobne formatowanie różnych komponentów interfejsu), używanie standardów (ma przypominać inne interfejsy) <br> ^ przykłady: barwa, czcionka, menu, położenie przycisków, informacje zwrotne
- zapobieganie błędom - uniemożliwiamy wprowadzenie błędnych danych - walidacja wejścia
- minimalizacja obciążenia pamięci użytkownika (np. skrótami klawiszowymi, ma być intuicyjnie)
- elastyczność i wydajność - doświadczony użytkownik ma mieć możliwość wykorzystania zaawansowanych opcji dla przyspieszenia pracy
- prostota dialogu - ograniczyć zbędne informacje
- dobre diagnozowanie błędów: w języku zrozumiałym dla użytkownika
- pomoc i dokumentacja: podpowiedzi, podręczniki, support, lupka
## 18. Techniki komunikacji międzyprocesowej
- pliki - wszechobecna ale wolna bo operacje na plikach
- sygnały - powiadamianie procesu o asynchronicznym wydarzeniu (procesy mogą zdefiniować obsługę)
- sockety - komunikacja dwukierunkowa, punkt końcowy komunikacji: adres+port / plik, strumień / ramki
- kolejki wiadomości - kolejka asychronicznych wiadomości (microsoft i java mają swoje implementacje)
- potoki - przekierowywanie wyjścia jednego procesu na wyjście drugiego (typowo standardowe I/O)
    - useful: tee
- nazwane potoki - niezależne od cyklu życia procesu, w unixach są to specjalne pliki
- semafory - określają dostęp do zasobów zapobiegając wyścigom
- pamięć współdzielona - szybsza od potoków / gniazd, ale tylko dla procesów na danej maszynie
- zdalne wywoływanie procedur np. java RMI (Remode Method Invocation) - wywoływanie metody obiektu innego procesu
## 19. Główne techniki zwiększania wydajności współczesnych procesorów
- procesor wykonuje rozkazy, miarą wydajności jest szybkość
### Procesory wielordzeniowe
- każdy rdzeń procesora może wykonywać rozkazy
- rdzenie mogą obsługiwać przerwania w różny sposób, np. tylko jeden rdzeń odświeża czas systemu na przerwanie zegarowe
- oszczędność energii przy tej samej ilości zadań (współdzielenie zasobów)
- współbieżność zawsze spoko wiadomo
- drogie, nagrzewają się, nieskalowalne (koordynacja staje się wąskim gardłem)
### Hyper-Threading
- kilka rdzeni wirtualnych w ramach jednego fizycznego
- dobre dla aplikacji wielowątkowych - każdy rdzeń wirtualny obsługuje w danym czasie jakiś wątek
### pamięć cache
- znacznie zmniejsza czas dostępu do pamięci
- kilkupoziomowa - najwyższy poziom dostepny bezpośrednio z procesora
- zasada lokalności pamięci i rozkazów - np. jak do cache się ładuje cały blok pamięci a program odwołuje się do danych które są obok siebie (rozkazami które są obok siebie), to będzie przeważnie cache hit
- write-through, write-back (dirty)
- układy przewidywania - dane ładuje się do cache z wyprzedzeniem
### potoki
- wykonywane rozkazy rozbija się na etapy (pobranie instrukcji, dekodowanie, wyznaczenie adresów, wykonanie rozkazu, zapis do pamięci)
- procesor w każdym cyklu zegarowym wykonuje jeden etap - inny etap kilku różnych rozkazów jednocześnie
- cpu może kończyć instrukcje w każdym cyklu zegara
- analogia linii produkcyjnej
### very long instruction word
- dzielenie programu (po kompilacji) na ścieżki wykonywane na kilku ALU w razamach jednego procesora
## 20. Charakterystyka modeli przetwarzania w Internecie
### klient - serwer
- serwer obsługuje wielu klientów jednocześnie
- serwer udostępnia usługi na określonych portach, komunikacja przebiega według znanych protokołów
- np. mail -> POP3, IMAP, repozytoria plików -> FTP, www -> HTTP
- klient może w różnym stopniu brać udział w przetwarzaniu danych obciążając/odciążając serwer
### pośrednik
- klient łączy się z pośrednikiem -> dostaje info o serwerze -> łączy się z serwerem
- DNS
### p2p
- peer to peer, równość obu stron komunikacji (obie strony mogą pełnić rolę serwera i klienta)
- porównywalna ilość danych wysyłanych i odbieranych
- wada - brak serwera oznacza brak kopii zapasowych danych
- np. komunikatory
### chmura
- usługi dostarczane przez zewnętrzne organizacje
- nie trzeba mieć oprogramowania ani nawet sprzętu - płaci się za usługę
- wszystkie modele są mega skalowalne
- <b>IaaS</b> - Infrastructure as a Service
    - klient zarządza dostarczonymi zasobami w postaci maszyn wirtualnych, pamięci itd
    - służy do budowania i zarządzania infrastrukturą
    - wymaga najwięcej wiedzy technicznej
- <b>PaaS</b> - Platform as a Service
    - udostępnia środowisko uruchomieniowe i wdrożeniowe dla developerów
    - służy do rozwijania aplikacji
    - wymaga trochę wiedzy technicznej
- <b>SaaS</b> - Software as a Service
    - programy użytkowe dostarczone dla śmiertelników
    - służy do udostępniania i edycji treści, komunikacji, rozrywki itd
    - nie wymaga wiedzy technicznej
## 21. Rodzaje filtrów oraz ich zastosowanie w przetwarzaniu obrazów
### Filtrowanie obrazów - przetwarzanie ich pikseli w celu ukrycia lub uwypuklenia pewnych cech <br> maska - wagi poszczególnych pikseli z sąsiedztwa używane do wyznaczenia nowej wartości danego piksela
### Filtry dolnoprzepustowe
- rozmywanie, wygładzanie
- np. ustawianie pikseli na średnią wartość w masce
- usuwanie szumu (niekoniecznie rozmywanie)
    - filtr Gaussa (funkcja Gaussa w 2D na masce)
    - filtry medianowe
### Filtry górnoprzepustowe
- wyostrzanie, wykrywanie krawędzi
- różnica oryginalnego obrazu i rozmytego -> krawędzie
- suma oryginalnego obrazu i krawędzi -> wyostrzony obraz
- Laplace
    - filtry Laplace'a pozwalają na wykrycie wewnętrznych i zewnętrznych krawędzi (zależnie od znaków w masce) <br> 00 +1 00 <br> +1 -4 +1 <br> 00 +1 00
    - w narożnikach 0, $\Sigma$ = 0
### typowo algorytmy wykrywania krawędzi są wrażliwe na szum -> w pierwszym kroku wykonuje się Gaussa
## 22. Otwarte systemy agentowe: definicja, problemy konstrukcyjne i metody ich rozwiązywania
https://www.tandfonline.com/doi/full/10.1080/22348972.2017.1348890
### system agentowy - system rozproszony złożony z agentów wykonujących różne zadania we wspólnym celu
### agent - jednostka obliczeniowa zdolna do obserwowania i wpływu na swoje środowisko
- autonomiczny - przynajmniej część jego działań jest uwarunkowana jego dotychczasową wiedzą
- inteligentny - autonomiczne i inteligentne decyzje
- percepty rejestrują informacje, efektory wywierają wpływ
### architektury agentów
- oparte na logice formalnej
    - działania agenta oparte na stanie środowiska i zbiorze reguł logicznych
    - agent przeprowadza wnioskowanie i podejmuje decyzje
    - brak gwarancji akcji agenta, trudność opisania wszystkich problemów regułami logicznymi
- reaktywne
    - inteligentne działanie jest wynikiem interakcji z otoczeniem
    - agenty reagują na aktualny stan otoczenia (nie uwzględniają danych historycznych)
- warstwowe
    - dekompozycja procesu decyzyjnego na przynajmniej dwie warstwy
    - warstwa reaktywna - reaguje na stan środowiska i działanie warstwy proaktywnej
    - warstwa proaktywna - triggeruje warstwę reaktywną
    - jedno/dwuprzebiegowe (decyzja z ostatniej/pierwszej warstwy)
### komunikacja agentów - ontologia
- ontologia - sformalizowany opis dziedziny danego problemu
- kodek - wspólny język agentów
- wiadomości trafiają do zcentralizowanej kolejki
    - jeśli odbiorca akurat migruje, wiadomość jest dostarczana po jego deserializacji
- protokoły komunikacji - sformalizowane sekwencje komunikatów - rozwiązują konflikty i koordynują działania
- kooperacja typowo na zasadzie dziel i rządź - dekompozycja problemu na podzadania
- sieć kontaktowa - proponent zgłasza zadanie, oferent je przyjmuje (może rozbić na podzadania i je oddelegować)
    - co jeśli nie ma rozwiązania? np. ponowna propozycja
    - Paxos algorithm: są proponenci, oferenci i uczniowie, organizowane są synody -> agenty zbiegają się do jednej odpowiedzi (zbieżność as in convergence)
    - average consensus algorithm: agenty dążą do konsensusu w swoich sąsiedztwach, obniża to zużycie zasobów na globalne synody jak w Paxos
- systemy tablicowe
    1. na tablicy jest problem i dane wejściowe
    2. gdy któryś agent ma pomysł to może coś dopisać
    3. potem może kolejny na coś wpadnie dzięki tej dodatkowej informacji
    4. konieczność moderacji - nie wszyscy na raz
### zapobieganie błędom
- co jak agent się sypnie?
- OS powinien wspierać odzyskiwanie węzła (agenta) w razie awarii
- należy zapisywać kilka stanów agenta i podczas przywracania wybrać dobrze znany stan
- przywrócony agent (jak również przeniesiony) powinien samodzielnie sprawdzać czy wszystko gra ("rozejrzeć się")
- w celu zapewnienia bezpieczeństwa można korzystać z kluczy
### prawa robotyki z pkt widzenia agenta
1) nie szkodzic misji
2) nie szkodzic uczestnikom misji
3) nie szkodzic sobie
4) racjonalnie progresowac misje
5) trzymac sie konwencji (wzorca zachowan)
6) osiagac wlasne cele
7) dzialac wydajnie
### framework JADE jest popularny bo wszyscy znają jave i jest x-platform
## <b>Pytania profilowe</b>
## 1. Architektura i struktury składowania w systemach zarządzania bazami danych
### Architektura
- poziom użytkownika - schemy, logiczne obiekty bazodanowe (tablice, indeksy, obrazy)
    - schema - logiczny opis organizacji danych i ograniczeń, przypisany użytkownikowi; <br> schema stanowi zbiór innych obiektów bazodanowych, co ułatwia zarządzanie dostępami w złożonych bazach danych
- poziom wewnętrzny (logiczny) - zarządzany przez DBA (admin)
    - DB Block $\in$ extent $\in$ segment $\in$ tablespace $\in$ database
    - schema na poziomie tablespace -> logiczne obiekty bazodanowe na poziomie segmentów (1 obiekt - 1 segment)
    - DB Bloki składają się z bloków dyskowych, mają header (m.in. infrmacje o transakcjach, metadane) i dane, jak się coś nie mieści to jest chaining - podaje się ROWID ciągu dalszego (identyfikator segment->tablespace->db_blobk->wiersz)
- poziom fizyczny
    - datafile (poziom ekstentów, 1 extent = 1 plik w systemie plików)
    - disc block (poziom DB Block) $\in$ datafile
### container vs plugable database
- CDA - fizyczna baza danych, w ramach której przechowywane są logiczne dla ułatwienia organizacji (wspólne zasoby dla wielu baz danych)
- Pluggable (logiczna) - tj właściwa baza danych na której działa użytkownik, wchodzi w skład fizycznej
## 2. Mechanizmy zapewniania bezpieczeństwa i niezawodności w systemach zarządzania bazami danych
- autoryzacja
    - uprawnienia systemowe - operacje na obiektach schema (w ogóle)
    - obiektowe - operacje na konkretnym obiekcie schema (należy do właściciela, który może przyznawać go dalej)
    - administracyjne ($\in$ systemowe), SYSOPER daje duzo mozliwosci (np uruchamianie, wylaczanie, przywracanie), SYSDBA daje jeszcze wiecej (CREATE DB), userzy z uprawnieniami admin. domyslnie maja password file
- role
    - nazwane zestawy uprawnień systemowych i obiektowych ułatwiające zarządzanie dostępami
    - nie sa związane z konkretnymi schemami
    - uruchamianie skryptów PL/SQL wymaga uprawnień obiektowych do danej schemy
- profile
    - zestawy parametrów opisujące użytkowników
    - każdy użytkownik ma profil (jest default)
- quota
    - przyznawana dla użytkownika per baza danych, określa maksymalny rozmiar danych użytkowanika w BD
    - default = 0, nic nie dodasz
- common/local user/rola
    - user/rola, których nazwa zaczyna się od c## są common, czyli działają w każdej pluggable DB w CDB
- uwierzytelnianie hasłem
- audyt
    - monitorowanie systemu, wykrywanie problemów z bezpieczeństwem i złego zarządzania
    - audytuje się schemy, uprawnienia, konkretne zapytania (np. AUDIT INSERT ON table3)
    - wyniki w BD / .txt / .xml / logach
- przywracanie
    - kopie zapasowe
        - fizyczna - kopia fizycznych plików tworzących BD, plików kontrolnych, zarchiwizowanych REDO logów, kopiuje dane automatycznie, jest bezpieczniejsza
            - można skompresować puste bloki w kopii fizycznej -> wolniejsze odzyskiwanie
            - można inkrementować kopię fizyczną
            - synthetic full backup - ostatni pełen backup + inkrementy (zmienione bloki)
            - backup niespójny - wykonany na uruchomionej BD, wymaga media-recovery
        - logiczna - kopie struktur logicznych bazy danych (np. widoki), jest użyteczna przy transferze bazy danych, ale mniej bezpieczna
        - flashback - pozwala na wyświetlanie starej wersji BD bez jej przywracania, cofanie operacji i przywracanie BD
## 3. Sposoby zapewniania wydajności i strojenia w systemach zarządzania bazami danych
### poziomy + zasady optymalizacji wydajności w Oracle
- poziomy
    - poziom zapytań i aplikacji
    - poziom struktury logicznej bazy danych
    - poziom optymalizacji Oracle (struktury danych, instancja, pamiec, procesy, zasoby)
    - poziom środowiska (hardware, software, konfiguracja sieci)
- zasady - optymalizacje powinny dotyczyc wszystkich:
    - zapytan
    - aplikacji
    - uzytkownikow
- optymalizacja akcyjna - w odpowiedzi na zaobserwowane problemy
- optymalizacja proaktywna - zapobieganie problemom z wyprzedzeniem - execution plany, zarzadzanie obciazeniem instancji
### query execution plans
- cel - poprawienie niekorzystnie wykonywanych zapytan, bledow optymalizacji; nie lubimy iloczynów kartezjanskich
- metody
    - nested loop: łączenie rekordów z dwoch tablic, szybkie gdy jedna jest mała
    - soft-merge join: przed połączeniem tablic dane są sortowane, dobra gdy brakuje indeksów
    - hash join: tworzenie pomocnej tablicy z hashami dla większej tablicy, dobra gdy mamy na to miejsce
    - cartesian join: kazdy wiersz z kazdym, bardzo kosztowna
### cost-based, rule-based optimizer
- rule-based: uwzględnia tylko składnię zapytania, nie rozpatruje charakterystyki danych
- cost-based: przygotowuje różne plany i szacuje ich efektywność z uwzględnieniem konfiguracji i charakterystyki danych -> wybiera najlepszy
### indeksy
- stosowanie ma sens gdy stosunek wierszy zwróconych przez zapytanie do wszystkich wierszy w tablicy przekracza pewien próg (selektowność wierszy / bloków)
- stosuje się B-Drzewa, bitmapy, single/multi-column i function-based indeksy
### partycjonowanie
- stosuje się dla bardzo dużych tablic / gdy obsługujemy współbierzne DML
- partycje mają wpisy z tablic na podstawie przedziału / listy wartości / funkcji hash wybranych atrybutów
### klastry
- gdy typowo używa się dwóch tablic razem (operacje JOIN) to się opłaca wprowadzić klaster
- niekorzystny w przypadku zapytań na jedną tablicę
### tuning (strojenie)
- metryki: parametry instancji (np. rozmiary buforów)
- Automatic Workload Repository - miejsce składowania statystyk
- Automatic Diagnostic Database Monitor - wykrywa i raportuje problemy wykryte w AWR, czasem załącza wskazówki rozwiązania problemów
- Oracle Advisors - narzędzia wspomagające zarządzanie instancją (Buffer Cache Adv., Undo Adv., ...)
- Alerty - powiadomienia generowane przez serwer / advisorów, typowo odnoszą się do metryk
### przestrzenie optymalizacji
- optymalizacja pamięci
    - rozmiary pamięci podręcznych, buforów
- optymalizacja struktur danych
    - extenty, defragmentacja segmentów
    - alerty na rozmiar struktur
    - osobne tablespace na OLTP, OLAP
### OLTP vs OLAP
- OLTP
    - Online Transaction Processing
    - małe bloki, współbieżność, dużo buforów, duże użycie REDO logów, ARCHIVELOG, np. bankomaty
- OLAP
    - Online Analytical Processing
    - jak największe DB Bloki, bufory nie mają znaczenia bo pojedyncze transakcje dotyczą bardzo dużych danych, NOARCHIVELOG
## 4. Problem zagadnień przecinających w paradygmacie obiektowym
https://www.linkedin.com/advice/0/how-can-design-patterns-solve-cross-cutting-concerns \
https://peterbeukema.medium.com/top-10-cross-cutting-concerns-4cf30f7ab7fa
- sofware concern - problem wpływający na program komputerowy
- zagadnienia przecinające typowo dotyczą kilku modułów / warstw aplikacji
- zagadnienia przecinające wustępują, gdy moduł systemu jest odpowiedzialny za różne zadania i nie ma przejrzystego (prostego) interfejsu
- utrudnia to zrozumienie, testowanie i ponowne wykorzystanie kodu
- czynności niezwiązane z aktualnie wykonywanym zadaniem (logiką biznesową) (np. logowanie, sprawdzanie uprawnień) zwiększają złożoność kodu, utrudniają jego modyfikację
- można rozwiązać te problemy stosując wzorce projektowe, np. Decorator (dodawanie funkcjonalności), Observer (reagowanie na akcje, np. logowanie ich)
- można skorzystać z programowania aspektowego do wprowadzenia funkcjonalności zwiększających coupling (powiązania pomiędzy komponentami, złożoność kodu), aby kod pozostał przejrzysty i prosty
- przykłady
    - logging
    - monitoring
    - security (autoryzacja)
    - caching (występuje na kilku warstwach aplikacji)
    - data validation
    - exception detection / handling
- dlaczego to jest problem
    - DRY - Don't Repeat Yourself
    - jak się coś zmienia to potem trzeba w wielu miejscach
    - przykładowe rozwiązanie to frameworki do loggowania
    - Separation of Concerns (zasada)
    - Single Responsibility (SOLID)
## 5. Zasady SOLID w projektowaniu obiektowym
- S - single responsibility (jedna klasa - jedna odpowiedzialność, jeden powód do zmiany)
- O - Open for extension / Closed for modification
- L - Liskov Substitution - podstawienie klasy dziedziczącej pod bazową nie powinno nic psuć
- I - Interface segregation - rozbijanie złożonych interfejsów na prostsze, żeby klasy implementowały tylko potrzebne metody
- D - Dependency inversion - moduły wysokopoziomowe powinny polegać na abstrakcji (nie bezpośrednio na niskopoziomowych)
## 6. Pojęcie wzorca projektowego oraz jego rola w procesie projektowania.
- improwizacja (∩^o^)⊃━☆ﾟ.*･｡ﾟ
- klasyfikacja
    - konstrukcyjne (creational) - tworzenie obiektów (np. Factory)
    - strukturalne - struktury powiązanych obiektów (np. Adapter, Facade)
    - czynnościowe - zachowanie i odpowiedzialność współpracujących ze sobą obiektów (np. Observer)
    ---
    - klasowe - statyczne zależności między klasami (np. Adapter)
    - obiektowe - dynamiczne zależności między obiektami (np. Command (serializacja żądań))
## 7. Główne cechy baz danych typu NoSQL ze szczególnym uwzględnieniem założeń dotyczących ich rozproszenia
Relacyjne bazy danych są bardzo powszechne ale słabo skalowanle jak jest bardzo dużo danych.
Problem pojawia się, gdy danych jest tak dużo, że nie jedna maszyna nie jest już w stanie ich całych obsłużyć.
Z tego powodu wprowadzono NoSQL - nierelacyjne bazy danych.
### Skalowalność
- wertykalna - dokupowanie pamięci - jest ograniczona przez to ile pamięci jest w stanie obsłużyć procesor
- horyzontalna - dokupowanie komputerów (na tym skupiają się nierelacyjne bazy danych)
---
Nierelacyjne bazy danych są dobrym wyborem jak struktura danych jest zmienna.
### Replikacja
- kopiowanie danych na kilku węzłach
- umożliwia jednoczesny dostęp do tych danych z kilku węzłów
- peer-to-peer - można pisać do dowolnego węzła, jest połączenie każdy z każdym
- master-slave - zapis tylko do mastera -> propagacja, odczyt z każdego
### Sharding
- podział danych na kilka węzłów według jakiegoś kryterium
- sharded cluster - zbiór shardów zawierających podzbiory danych, wymagający routera przekierowującego (zapytanie) klienta do odpowiedniego sharda
- można połączyć replikację i sharding - np. kilka węzłów głównych ma inne dane, węzły główne mają swoje repliki
### CAP
- Consistency - na każdym węźle są takie same dane
- Availability - cały czas jest dostęp do wszystkich danych
- Partition Tolerance - system działa dalej w przypadku zerwania połączenia pomiędzy węzłami
    - Partition Tolerance jest bardzo ważna bo zawsze coś się może posypać - najpop są systemy CP i AP
    - w razie wypadku wybiera się np. nowego mastera
    - systemy CA nie są ani C ani A jeśli utracą połączenie
### BASE
- Basically Available - gwarancja dostępności w ramach CAPa
- Soft State - stan systemu może się zmieniać w dążeniu do spójności (propagacja zmian)
- Eventual consistency - po jakimś czasie bez inputu system osiągnie spójność
## 8. Rodzaje baz danych typu NoSQL i ich porównanie względem siebie
### key-value
- dobre, gdy nie trzeba przetwarzać wartości
- wartość to czarna skrzynka, nie wyszukujemy niczego po wartości
- dostęp do danych wyłącznie po kluczu
- duża trwałość, wydajność, dostępność, skalowalność
- przykład - redis
### document
- struktura JSON
    - BSON (np. w mongodb) - dodatkowe typy np. ISODate(), oszczędność miejsca (w JSON'ie wszystko jest stringiem)
- dane nie muszą mieć stałej struktury (ale się opłaca xD)
- łatwość zmieniania struktury danych - dodawanie pól itd.
- spójność z formatami danych w warstwie aplikacji - serializowanie do formatu json
- wyszukiwanie po wartości (np. typowo przedziały czasowe)
- dokumenty grupowane w kolekcje
### graph
- w relacyjnych bazach danych JOIN'y są kosztowną operacją
- w bazach grafowych wystarczy trawersować graf
- normalnie czas obsługi zapytania nie jest zależny od ilości danych (chyba że np. agregacje)
- węzły i krawędzie mają swoje etykiety
- możliwość wyszukiwania danych po wartości etykiet
- duża skalowalność
- wszystko jest grafem
    - https://soundcloud.com/daria-titova-549399723/teorie-grafu-3a-6
### inne: kolumnowe, tablicowe, obiektowe
- obiektowe się nie przyjęły bo na co komu polimorfizm w bazie danych lol
## 9. Rola i przykłady silników do odwzorowań obiektowo-relacyjnych (ORM)
https://www.baeldung.com/cs/object-relational-mapping
- najpopularniejszym paradygmatem programowania jest OOP
- relacyjne bazy danych nie wspierają do końca OOP
    - np. jak się coś zmienia w kodzie to potem zmiany w strukturze bazy danych są uciążliwe
- narzędzia ORM pozwalają na mapowanie (tłumaczenie) obiektów z aplikacji na relacyjną bazę danych
- zastosowanie - nie trzeba pisać zapytań SQL w kodzie aplikacji, wystarczy obsłużyć ORM w swoim języku (odwołując się do pól obiektów aplikacji)
- ORM dostarcza klasę bazową dla klas, które powinny być odwzorowane w bazie danych
- ORM umożliwia łatwą migrację do innej bazy danych (abstrakcja backendu bazodanowego)
- ORM wspierają ochronę przed wstrzykiwaniem SQL (SQL injection)
- wada: przy skomplikowanych zapytaniach czysty SQL jest dużo lepszy
- (czasem) wada: nie jest 1:1 -> nie mamy pełnej kontroli
- każda duża platforma ma swój ORM:
    - java -> Hibernate
    - python -> Django (web framework zawierający ORM)
## Pytania prep
https://docs.google.com/spreadsheets/d/1i8rBznVshrAxGnm8QFo3FNSEKWH9MRcWcz-UIzCy64o/edit#gid=0
