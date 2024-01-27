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

## 10. Cykle życia oprogramowania (modele wytwarzania oprogramowania)
## 11. Zasady modelowania dla konstrukcji relacyjnych baz danych
## 12. Opis wybranej metodyki wytwarzania oprogramowania
## 13. Budowa systemów plików w systemach operacyjnych
## 14. Modele barw w grafice komputerowej
## 15. Poziomy testowania w cyklu życia oprogramowania
## 16. Klasy języków programowania na wybranych przykładach
## 17. Zasady budowy interfejsów użytkownika systemów informatycznych
## 18. Techniki komunikacji międzyprocesowej
## 19. Główne techniki zwiększania wydajności współczesnych procesorów
## 20. Charakterystyka modeli przetwarzania w Internecie
## 21. Rodzaje filtrów oraz ich zastosowanie w przetwarzaniu obrazów
## 22. Otwarte systemy agentowe: definicja, problemy konstrukcyjne i metody ich rozwiązywania
## <b>Pytania profilowe</b>
## 1. Architektura i struktury składowania w systemach zarządzania bazami d.anych
## 2. Mechanizmy zapewniania bezpieczeństwa i niezawodności w systemach zarządzania bazami danych
## 3. Sposoby zapewniania wydajności i strojenia w systemach zarządzania bazami danych
## 4. Problem zagadnień przecinających w paradygmacie obiektowym
## 5. Zasady SOLID w projektowaniu obiektowym
## 6. Pojęcie wzorca projektowego oraz jego rola w procesie projektowania.
## 7. Główne cechy baz danych typu NoSQL ze szczególnym uwzględnieniem założeń dotyczących ich rozproszenia
## 8. Rodzaje baz danych typu NoSQL i ich porównanie względem siebie
## 9. Rola i przykłady silników do odwzorowań obiektowo-relacyjnych (ORM)

## Pytania prep
https://docs.google.com/spreadsheets/d/1i8rBznVshrAxGnm8QFo3FNSEKWH9MRcWcz-UIzCy64o/edit#gid=0
