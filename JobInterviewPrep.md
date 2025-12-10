# Job Interview

## Java

[GFG](https://www.geeksforgeeks.org/java/java-interview-questions/)

- kompilowana do języka pośredniego (pliki .class), niezależnego od środowiska ale wymagającego JVM (środowiska uruchomieniowego Javy)
  - język interpretowany, kompilowany (.java -> kompilacja -> .class -> interpretacja do pliku wykonywalnego)
- wspiera obiektowość, współbieżność, ma dużo bibliotek i frameworków (np. Spring, Kafka)
- garbage collection, error-handling
- bezpieczeństwo - możliwość udostępnienia aplikacji bez kodu, BRAK POINTERÓW
- JIT - Just In Time compilation - kompilowanie kodu pośredniego do instrukcji procesora na bieżąco podczas runtime'u
- pamięć
  - pamięć klas (pola, metody)
  - kopiec (heap) - obiekty programu w czasie run time
  - sterta (stack) - dane i wyniki tymczasowe podczas wykonywania programu
  - kod metod natywne
- JRE (Java Runtime Environment) dynamicznie ładuje klasy i interfejsy do JVM
- JVM: interpreter, JRE: środowisko uruchomieniowe, JDK: java development kit (najczęściej z JRE w pakiecie)
- Java jest typowo do pisania aplikacji użytkownika a C++ do aplikacji systemowych
- Java nie ma pointerów tylko referencje
- w Javie wszystko dziedziczy po klasie Object
- public - dostęp spoza kontekstu klasy, static - dostęp bez instancji klasy
- String Pool - miejsce w kopcu z wszystkimi stringami zdefiniowanymi w programie (zmienne idą już normalnie na stertę)
- niestatyczna funkcja main NIE będzie traktowana jako punkt wejściowy programu
- pakiety to forma grupowania kodu i organizacji przestrzeni nazw
- prymitywne typy danych: boolean, byte, char, short, int, long, float, double
  - Wrappery - Boolean, Byte, ... (zawierają podstawowe metody) -> autoboxing i unboxing to konwersja primitive <-> Wrapper
- nieprymitywne typy danych: String, Array, Class, Object, Interface
- wartości domyślne są zerowe, lub puste (null)
- class variable === static variable of a class
- instance variable === non-static (per instance) variable of an object
- Input/OutputStream (ByteStream) operują na bajtach, Reader/Writer (CharacterStream) na ciągach znaków
- FileInputStream, FileOutputStream
- BufferedInput/OutputStream - ogranicza ilość interakcji z systemem (komunikacja większymi porcjami danych - buforem)
- print - zwykłe pisanie, println - pisanie z nową linią, printf - pisanie z formatowaniem
- shiftowanie >>, >>>
- transient keyword - JVM nie serializuje wartości pól transient tylko wartości domyślne
- Sleep() / Wait() - Sleep() nie zwalnia blokady
- StringBuffer jest mutowalny w przeciwieństwie do String i jest Thread-safe
- płytkie vs głębokie kopie (głębokie - kopiuje wszystkie pola i elementy)
- abstrakcja, enkapsulacja, dziedziczenie, polimorfizm
- kompozycja vs agregacja - samochód jest SKOMPONOWANY z części, szkoła agreguje nauczycieli i uczniów
- HashSet - podstawowa implementacja, LinkedHashSet - zachowuje kolejność dodawania, TreeSet - porządkuje dane
- SortedMap, TreeMap, HashMap, LinkedHashMap - dane key:value jak dict() w pythonie
- Iterator zawiera funkcje hasNext() oraz next()
- ArrayList jest 1D, mutowalna (dynamiczna)
- LinkedList jest dwukierunkowa i rozproszona w pamięci niż ArrayList, więc jest szybsza w dodawaniu i usuwaniu, ale wolniejsza w przeszukiwaniu
- Vector jest synchronizowany w przeciwieństwie do ArrayList
- Java nie wspiera dziedziczenia z kilku klas naraz (ale można dziedziczyć z kilku interfejsów)

## .Net

[GFG](https://www.geeksforgeeks.org/c-sharp/c-sharp-interview-questions/)

- JIT, język pośredni
- Common Language Runtime (środowisko wykonawcze)
- Common Type System
- C#, F#, inne
- Garbage Collector
- domyślnie nie używa się wskaźników
- jest dziedziczenie z kilku klas
- enum do tworzenia wyliczeń magicznych wartości
- properties: get/set
- można używać kilku Catch bloków jak odnoszą się do różnych typów wyjątków
- 1 is int -> true, 1 as double -> true, "aaa" as double -> false (as - konwersja)
- są Tuple! ale mogą mieć tylko 8 elementów
- są Interfejsy do multiple inheritance (dziedziczenia z kilku interfejsów)
- klasy abstrakcyjne mogą mieć pola (dane)
- extension methods - dopisywanie metod do istniejących klas
- partial class: rozpisywanie JEDNEJ klasy na KILKA plików
- LINQ (Language Integrated Query) - zapytania bazodanowe w języku programowania
- delegate - ~wskaźnik na funkcję z pewną listą parametrów
- sealed class - coś jak final - nie można z niej dziedziczyć
- event, delegate, handler (taka tam architektura)
- boxing unboxing - value type <-> reference type (object)

## docker

[GFG](https://www.geeksforgeeks.org/devops/docker-interview-questions/)

- kontener to środowisko wykonawcze dla aplikacji i programów, przenośne i niezależne od systemu, dające powtarzalność, automatyzację i bezpieczeństwo
- docker engine - program wykonujący kontenery
- obrazy, kontenery wiadomo
- docker compose - narzędzie do uruchamiania aplikacji złożonych z kilku komponentów w osobnych kontenerach
- hypervisor - oprogramowanie wirtualizacji umożliwiające uruchamianie różnych systemów gości na jednym hoście
- VMki to wirtualne instancje całego systemu, kontenery współdzielą jądro systemu (kernel) więc są lżejsze
- docker save -o zapisuje obraz jako archiwum -> docker load -i
- docker rm, docker ps, docker start, docker stop
- CMD to instrukcja i parametry na początek kontenera, które można nadpisać w parametrach docker start
- ENTRYPOINT to to samo ale sprawia, że kontener zachowuje się trochę bardziej jak zwykły program

## windows system administration

- AD (active directory)
  - serwis służący do zarządzania kontami użytkownika i systemowymi oraz dostępami w domenie windows (w sieci domenowej)
  - AD kontrolery używają replikacji żeby się nie sypło
- co jak jest mało miejsca na maszynie windowsowej?
  - Task Manager, Process Explorer (sysinternals, pozwala np na wyszukiwanie który proces trzyma handle na dany plik lub .dll)
  - du (disk usage - sysinternals) jak na linuxach wypisuje rozmiar per directory

    ```bash
    du $MYDIR | grep -e "$MYDIR/[^/]*\$"
    ```
  
  - df (disc free) dostępny na linuxowych nakładkach (np. git bash, cygwin)
  - aktualizacje (i wg wszystkie zmiany) najpierw na środowisku testowym/deweloperskim, dopiero potem na produkcji
  - PowerShell z ograniczeniami dla normalnych userów, lepszy dla adminów ale z zasady dla każdego NIEZBĘDNE MINIMUM
  - ScheduledTask - jak chron na linuxach - można automatyzować regularne uruchamianie skryptów i programów np. do monitoringu
  - opcją są też zautomatyzowane playbooki
  - `regedit` pozwala na ustawianie rzeczy (np. zmiennych środowiskowych) per serwis
  - ogólnie zaleca się regularne rebootowanie
  - patchowanie (aktualizacje/updates)
    - Windows Server Update Services (WSUS)
    - testowanie w piaskownicy
    - wyłączanie z puli na czas patchingu
    - plan awaryjny: kopia zapasowa
    - automatyzacja patchowania (security patche z priorytetem) (minimalizacja błędu ludzkiego)
  - w razie ataku: izolacja z sieci, analiza logów, szukanie znanych wirusów, backup
  - bezpieczeństwo
    - polityka haseł (długość, znaki, częstotliwość zmiany)
    - ograniczanie działających serwisów do minimum
    - ograniczanie uprawnień użytkowników
    - automatyzacja deploymentu maszyn żeby wszędzie było tak samo
  - inwestygacje
    - Event log systemu i aplikacji
    - Process Monitor (sysinternals)
    - korelacja crashów z backupami, antywirusem i innymi cyklicznymi zadaniami
    - repro w środowisku deweloperskim
  - defragmentacja dysku to rzecz
  - logowanie z Powershella do pliku to rzecz
  - konfigurowanie dysku do używania RAID (redundancja, typowo używa się RAID5 - minimum 3 dyski, na których splituje się bloki danych z blokiem parity)
  - dokumentowanie zmian, wspominanie na spotkaniach

## Powershell

- Get-Help metoda
- if-else, switch, while, for
- powershell jest obiektowy w takim sensie że output to obiekt, który ma swoje pola i metody
  - w bashu output jest tekstowy
  - obiektowość wynika z oparcia na platformie .NET
- walkthrough po wersjach
  - PS1 - podstawa
  - PS2 - zdalne wykonywanie komend, background jobs
  - PS3 - code competion, resumable sessions
  - PS5 - pisanie własnych klas, bezpieczeństwo (można blokować starsze wersje)
  - PS6 - open source, cross-platform (.NET Core)
- moduły - biblioteki, można pisać własne
  - PSReadLine (historia itd)
  - są moduły do obsługi narzędzi Office
  - AD

    ```powershell
    import-module ActiveDirectory
    ```

## Linux

- free, open source, Unix, monolityczny kernel
- Ubuntu, Fedora, Mint, Debian, RedHat
- kernel łączy hardware z softwarem, powłoka łączy użytkownika z kernelem
- root = admin
- `ln` - tworzenie linków symbolicznych
- i/o: stdin, stdout, stderr
- `mount` mountuje partycję dyskową
- `ifconfig`, `ip route`, `/etc/resolv.conf` (DNS), `iptables` (firewall) do sprawdzania konfiguracji sieciowej
- `ps`, `chmod`, `df`, `du`, `useradd $USER`, `passwd $USER *****`, `crontab -e`
- proces ma własną pamięć i jest niezależnym programem, wątek współdzieli pamięć z innymi, należy do procesu
- `find` szuka plików po nazwie
- RAID - patrz windows
- `systemctl`, `journalctl`
- `sed`, `awk`, ...
- `sudo` - służy do wydawania poleceń z uprawnieniami systemowymi (superuser)

## vue.js

- reactivity - Vue inteligentnie renderuje tylko to co się zmieniło
- sposób działania - templatki html z zaznaczonymi miejscami gdzie pod spodem ma wejść Vue
- ALBO czysty javascript
- dyrektywy (w atrybutach HTML)
  - `v-html="rawHtml"`
  - `v-bind:id="dynamicId"` === `:id="dynamicId"`
    - funkcje w bindach nie powinny mieć efektów ubocznych bo będą wołane za każdym odświeżeniem komponentu
    - wartości atrybutów-dyrektyw powinny być pojedynczymi wyrażeniami .js
    - rolą dyrektywy jest wywołać odświeżenie komponentu gdy wartość wyrażenia się zmienia
    - po dwukropku jest argument wyrażenia
  - `v-on:click="doSomething"` === `@click="doSomething"` słucha wydarzeń
  - `<a v-bind:[attr]="url"></a>` - `attr` w kwadratowych nawiasach to dynamiczny atrybut (wyrażenie .js którego wynikiem jest string albo null)
  - `@submit.prevent="onSubmit"` - po kropce jest modyfikator
- `ref` to wrapper na zmienną, któy umożliwia śledzenie, które zmienne były odczytane przy danym renderze, i które od tego czasu się zmieniły (reaktywność)
  - default: deep ref, optional: shallow ref (jak płytka i głęboka kopia)
  - alternatywa: `const state = reactive({key: value}); reactive.key++;`
- `await nextTick()` pozwala na zaczekanie na update zawartości

## cyberbezpieczeństwo

- PKI - Private Key Infrastructure
- hashe - skróty wiadomości, np szyfrowane kluczem prywatnym -> odbiorca odszyfrowuje hash kluczem publicznym i potwierdza treść wiadomości
  - nawet mała zmiana treści wiadomości wywołuje znaczną zmianę hasha
  - współcześnie używa się m.in. algorytmu SHA-256
  - hashe służą też do przechowywania haseł
- CA - certification authority, root CA
  - CA wydaje certyfikat zawierający klucz publiczny i podpisuje go swoim zaszyfrowanym hashem - weryfikacja certyfikatu kluczem publicznym CA
- szyfrowanie asymetryczne: para kluczy, symetryczne: jeden klucz (trudność: bezpieczne udostępnienie klucza)
- SSL, TLS - szyfrowane połączenie przeglądarka-serwer
  - handshake - weryfikacja certyfikatu (z kluczem publicznym) serwera, klient szyfruje kluczem publicznym serwera klucz symetryczny i wysyła go z powrotem
  - HTTPS = HTTP + TLS
- SSH - secure shell w warstwie aplikacji - tworzy szyfrowany (parą kluczy) tunel pomiędzy klientem a serwerem
  - wymiana plików, wykonywanie poleceń linii komend
- VPN - virtual private network - tworzy tunel W WARSTWIE SIECIOWEJ - szyfruje cały ruch sieciowy z urządzenia
  - tunel łączy urządzenie i serwer VPN, sprawiając że ruch wygląda jakby wychodził z serwera (ukrywanie lokalizacji i IP użytkownika)
  - korporacyjny VPN łączy zdalnych pracowników z wewnętrzną siecią korporacji, chroniąc (szyfrując) ruch przechodzący przez sieć publiczną
  - VPN jako sieć prywatna umożliwia korporacjom stawianie własnych serwisów (bez ograniczenia publicznej puli adresów IP)
- AES, RSA
  - RSA polega na znalezieniu i wymnożeniu dwóch dużych liczb pierwszych, których iloczyn jest ciężki do rozbicia na czynniki
    - powolniejszy ale bezpieczniejszy, słaby do dużych danych, ważny w PKI
    - wymaga dużo większych kluczy by był bezpieczny (conajmniej 2k bitów)
  - AES - szybki i elastyczny alg. symetryczny - trudność w udostępnieniu klucza

## testy

- zasady pisania testó
  - poprawne i niepoprawne wejście
  - perspektywa użytkownika końcowego
  - dokumentacja, prostota
  - priorytetyzacja testów i błędów
- white box - znamy kod i piszemy test pod niego
- black box - nie znamy kodu (testy jednostkowe, integracyjne, systemowe, akceptacyjne)
- ene-to-end - całościowy test systemu od deski do deski

## metodyki

- model kaskadowy (wszystkie wymagania z góry, ograniczona komunikacja)
  1. planowanie
  2. analiza
  3. projektowanie
  4. implementacja
  5. testowanie i walidacja
  6. utrzymanie
- model V = model kaskadowy PLUS TESTY
  1. testy akceptacyjne (środowisko użytkownika)
  2. testy systemowe (walidacja systemu)
  3. testy integracyjne (moduły systemu)
  4. testy jednostkowe
- model przyrostowy, iteracyjny, spiralny
- model zwinny
  - 1 iteracja = 1 przyrost
  - małe dynamicznie planowane iteracje
  - małe zespoły i intensywna komunikacja (wewn zespołu, z klientem)
  - scrum - sprinty + daily, scrum master + product owner
  - kanban - tablica stanów zadań (TODO, WIP, CLOSED, ...)
  - extreme programming - programowanie w parach
    - Test Driven Development (pisanie unit testów przed kodem)
    - programowanie w parach (zmiany w parach dla lepszej wymiany wiedzy)
    - prostota (minimal viable solution) w małych przyrostach

## zasady SOLID

- S - single responsibility (jedna klasa - jedna odpowiedzialność, jeden powód do zmiany)
- O - Open for extension / Closed for modification
- L - Liskov Substitution - podstawienie klasy dziedziczącej pod bazową nie powinno nic psuć
- I - Interface segregation - rozbijanie złożonych interfejsów na prostsze, żeby klasy implementowały tylko potrzebne metody
- D - Dependency inversion - moduły wysokopoziomowe powinny polegać na abstrakcji (nie bezpośrednio na niskopoziomowych)

## JP 100%

- kompilowane - do kodu maszynowego np. C++, Go
- interpretowane - wykonywane przez interpreter instrukcja po instrukcji (wolniejsze ale przenośniejsze)
- z językiem pośrednim (java, C#) - kompilowane do języka pośredniego, który jest kompilowany Just-In-Time
- imperatywne (proceduralne) - programy wykonywane instrukcja po instrukcji, często zorganizowane w funkcje np. C
- OOP - abstrakcja, enkapsulacja, dziedziczenie, polimorfizm np. C++, Java, python
- deklaratywne - opisują oczekiwany wynik a nie instrukcje które do niego prowadzą, np. SQL, Prolog
- funkcyjne - wykorzystują czyste funkcje (powtarzalne, bez efektów ubocznych), na kształt funkcji matematycznych, np. Haskell, F#

## NoSQL

- replikacja
- sharding (podział danych na różne węzły w klastrze)
- skalowalność
