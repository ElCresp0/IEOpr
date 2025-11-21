# MGR_OBRONA_PREP

## Teza, motywacja (!!)

- praca wspiera podejście rozpoznawania emocji z dłoni (w szczególności z ich ruchu) w nagraniach wideo

## Motywacja

- zagadnienie rozpoznawania emocji z ruchu dłoni jest dotychczas mało zbadane
- większość badań, w ramach których analizowane jest ustawienie lub ruch dłoni, dotyczy rozpoznawania gestów (Human-Computer Interaction) i języka migowego
- niektóre badania wskazują, że dłonie stanowią samodzielne i dostateczne źródło informacji o emocjach człowieka (nawet gdy twarz pozostaje niewidoczna)
- w obrazie z kamerek laptopów często widoczne są dłonie ich użytkowników

## Wyniki badań

- potwierdziliśmy wartość ruchu dłoni jako nośnika informacji emocjonalnej
- zbadaliśmy skuteczność popularnych algorytmów uczenia maszynowego (SVM, płytkie sieci neuronowe) w klasyfikacji emocji na podstawie dłoni (z wykorzystaniem kilku zbiorów danych)
- przekonaliśmy się, że ruch dłoni (wyrażony jako odpowiednio przetworzona sekwencja klatek w nagraniu) stanowi lepszy format od statycznego ustawienia (klatek pojedynczych)
- PRZY OKAZJI potwierdziliśmy użyteczność zbioru nagrań studentów rozwiązujących zadania programistyczne w problemie rozpoznawania emocji z ruchu dłoni (z użyciem uczenia nienadzorowanego (HDBSCAN) wykryliśmy powtarzające się wzorce ustawienia dłoni, które można interpretować jako manifestacje emocji studentów)

## praktyczne implikacje

- Human-Computer Interaction
- informatyka afektywna

## ograniczenia

- Deep Learning
- ?

## kierunki dalszych badań

- RNNs
- etykietowanie naszego zbioru

## Najważniejsze wnioski

## Wykorzystane metody badawcze

- eksperyment (uzasadnienie)

## Przykłady innych badań, które potwierdzają lub zaprzeczają naszym wynikom

- [14] E. Blythe, L. Garrido, and M. R. Longo, “Emotion is perceived accurately from isolated
body parts, especially hands,” Cognition, vol. 230, p. 105260, Sep. 2022, doi:
10.1016/j.cognition.2022.105260.
- ?

## Badania operacyjne

- Programowanie liniowe (Obszarski)
  - Bardzo elastyczna metoda matematyczna, polegająca na wyznaczaniu optymalnego rozwiązania problemu liniowego. Rozmaite problemy można przedstawić jako zestaw parametrów liczbowych (pierwszego stopnia - stąd liniowość), ograniczeń (dotyczących tych parametrów) i złożonej z nich funkcji celu, która podlega optymalizacji. Tak zdefiniowany problem można rozwiązać algorytmem programowania liniowego. Najprostsze koncepcyjnie jest rozwiązanie geometryczne. Ograniczenia można przedstawić jako proste na wykresie, które razem z osiami układu współrzędnych tworzą wielokąt. Rozwiązanie to punkty na krawędziach tego wielokąta, które znajdują się w najmniejszej lub największej odległości od środka układu współrzędnych (zależnie czy funkcja celu podlega minimalizacji czy maksymalizacji).

- teoria kolejek (Pióro)
  - notacja A/S/c (Arrival, Service, number of servers)
  - symbole M (bezpamięciowy), D (deterministyczny), G (arbitralna dystrybucja), FIFO, LIFO
  - opis naturalny
    mamy kolejkę zadań (klientów) i zbiór serwerów
    parametry to: dystrybucja napływu zleceń, sposób obsługi kolejki, czas obsługi zlecenia, liczba serwerów, pojemność systemu
  - poco a poco
    - modelujemy system żeby wybrać optymalny sposób obsługi

- szeregowanie zadań (Giaro)
  - mamy zdefiniowane zadania o różnym czasie wykonania i kilka procesorów
  - planujemy kolejność wykonania zadań na procesorach tak, aby cały system działał optymalnie
  - parametry zadań
    - p - czas wykonania
    - r - czas przybycia (release - najwcześniejszy czas kiedy można zacząć wykonywać zadanie i)
    - d - czas zakończenia (delivery - od tego momentu nalicza się opóźnienie, które podlega minimalizacji)
    - w - waga zadania
    - podzielność zadania
  - kryteria kosztu harmonogramu: moment zakończenia, czas przepływu, opóźnienie
  - ogólna strategia: sortujemy zadania i układamy od najdłuższego na kolejnych procesorach (List Scheduling)
  - minimalizacja średniego czasu przepływu - szeregowanie SPT (shortest Processing Time), żeby upchnąć jak najwięcej krótkich zadań z przodu
  - minimalizacja maksymalnego opóźnienia - algorytm Liu (wybieramy zadania o najmniejszym wymaganym d)

## Biblioteki cyfrowe

- cyfrowe zbiory informacyjne
- dane cyfrowe: skany, zdjęcia 360, audio, ...
- digitalizacja i udostępnianie zbiorów muzealnych
- interfejs użytkownika: dostęp do treści, możliwość interakcji, publikowania własnych treści, wyszukiwanie
- format DJVU (deżawu) - kompresja stratna dokumentów (docelowo skanowanych), przechowuje obraz jako warstwy (tło, pisanina)
- biblioteka cyfrowa - wyselekcjonowany i uporządkowany zbiór informacji cyfrowej

## Grafika trójwymiarowa

- [merge](E:\C_Users_kubak\MGR_SEM1\GT\merge.pdf)
- [fishky](../../source/repos/fishky/Debug/GT052024.txt)
- rendering - proces generacji obrazu na podstawie modelu
- **potok renderingu** <!-- TODO: verify with Systemy Graficzne -->
  - modelowanie, rzutowanie
  - określanie widoczności
  - konwersja w piksele
  - cieniowanie
- fixed / programmable pipeline - ustalony ciąg sparametryzowanych procesów / programy cieniujące (shadery)
- teselacja - podział ścian na mniejsze kawałki
- reprezentacja brzegowa modelu - wierzchołki + krawędzie + ściany (V, E, F)
  - złożone struktury np. pasek trójkątów
  - reguła Eulera
    V - E + F - H = 2(C - G) // H - dziury, G - otwory, C (Count) - rozłączne elementy
- rasteryzacja - rzutowanie, upraszczanie, obcinanie -> konwersja na piksele
- wytłaczanie (extrusion) - reprezentacja bryły jako figury przesuniętej wzdłuż trajektorii (think koło garncarskie)
- kwarteniony - uogolnienie liczb zespolonych, jednostki urojone i,j,k -> pozwalaja na opis obrotu za pomoca 4 liczb zamiast macierzy 3*3
- ray tracing (śledzimy promienie wpadające do oka w kierunku oko -> pierwszy napotkany obiekt)
  - promienie pierwotne, promienie wtórne (odbicia, cienie)

## Rzeczywistość wirtualna

- klasyfikacja
  - Rzeczywistosc Rzeczywista
  - Rzeczywistosc Rozszerzona
  - Wirtualnosc Rozszerzona
  - Rzeczywistosc Wirtualna
- Autostereoskopia
  - obraz stereoskopowy (z głębią) bez sprzętu VR
  - bariera paralaksy - zasłonięcie ekranu przesłoną ze szczelinami
  - soczewki - pokrycie ekranu warstwą soczewek powodujących emisję innego obrazu do oka lewego i prawego
- Ambisonia
  - dźwięk w 360 - format opisujący położenie każdego ze źródeł dźwięku
- dużo szczegółów biologicznych

## Multimedialne systemy interaktywne

- modele emocji (patrz: praca dyplomowa prep)
- sygnały fizjologiczne: opóźnione (np. zmiana tętna po 5s), zależne od osobnika
- ERF - Emotion Recognition Framework
  - in: wejście i/o (obraz, dźwięk, sygnały fizjo.), zachowanie w systemie
  - out: oszacowany stan emocjonalny użytkownika
- sensory głębi (!)
  - pasywne (analizujemy obraz)
    - triangulacja
    - cienie
  - aktywne (świecimy podczerwienią i rejestrujemy)
    - time delay
      - interferometria
      - time-of-flight
    - triangulacja
      - structured light pattern (kinect)
      - single spot (z dwóch źródeł światła)
- LiDAR - kilka źródeł światła o różnych częstotliwościach do skanowania ukształtowania terenu, powstają modele 3D
- conieco o Kinekcie (SKIP)
- skeleton tracking - X joint pointów opisujących układ ludzika
- microsoft hololens - super oksy dla żołnieży, w których w sumie jest ograniczone pole widzenia i masz nudności xd
- optical see-through / video see-through - projekcje na rzeczywistym obrazie vs transmisja przetworzonego obrazu
- klasyfikacja wirtualności
  - augumented reality - wzbogacamy świat o elementy wirtualne
  - mixed reality - możliwość interakcji z wirtualnymi elementami
  - augumented virtuality - wirtualne odwzorowanie świata rzeczywistego z zachowaniem pewnych elementów
  - virtual reality - w pełni wirtualna rzeczywistość
- śledzenie pozycji i gestów
  - inside-in - na użytkowniku, dotyczą jego (np rękawiczki)
  - inside-out - na użytkowniku, dotyczą wirtualnych elementów (np gogle AR)
  - outside-in - zewnętrzny sprzęt wykorzystujący markery/kontrolery użytkownika
- środowisko wytwórcze - Unity XR w zgodzie ze standardem Khronos OpenXR

## Systemy graficzne

- grafika rastrowa vs wektorowa (wektorowa nie degraduje przy przekształceniach)
- w unity sceny w 2d są tak na prawdę odpowiednio zrzutowanym środowiskiem 3d
- scena = zbiór modeli obiektów (geometrie, reprezentacje - siatki poligonów) -> renderowanie grafiki z modelu sceny
- globalne algorytmy renderowania uwzględniają światło ze źródła i światło odbite
- karta graficzna
  - przystosowana do intensywnych współbieżnych obliczeń (AI, grafika komputerowa)
  - składa się z wielu jednowątkowych rdzeni graficznych, które wykonują to samo zadanie na różnych danych (Single Instruction, Multiple Threads principle)
  - rdzenie graficzne mogą wykonywać programy cieniujące (shadery)
  - rdzenie graficzne są zorganizowane hierarchicznie (w bloki), podobnie jak pamięć z której korzystają - każdy ma prywatną szybką pamięć oraz dostęp do pamięci bloku i pamięci globalnej GPU

- potok renderingu (!)
  1. Cieniowanie wierzchołków (vertex: {position, normal, color})
      1. Pobranie, cieniowanie krawędzi \
        -> kolory w 3D, rozmiar punktu
      2. Teselacja // dzielenie wielokątów 3D (prymitytów) na np. trójkąty
      3. Cieniowanie geometrii
      4. Tworzenie prymitywów // łączenie wierzchołków
  2. Rasteryzacja prymitywów // -> fragmenty
      - **Interpolacja**
  3. Cieniowanie fragmentów
      1. Test głębokości (bufor Z)
      2. Cieniowanie (przetwarzanie) fragmentów (tekstury, kolory)
      3. Alpha blending (przezroczystość)
      4. Operacje na buforze klatki (frame buffer) \
        -> piksele (kolor)

- programy cieniujące
  - GPU / CPU
  - przetwarzanie współbieżne
  - VS -> FS
    - vertex (krawędzie) -> fragment (fragmenty) shader
    - VS pracuje na współrzędnych wierzchołków, przeprowadza teselację i tworzy prymitywy do _rasteryzacji_
    - FS działa per piksel na interpolowanych pikselach (interpolacja następuje de facto pomiędzy)
  - tesselation control - shader odpowiadający za teselację, może służyć do kontroli szczegółowości (np. podczas oddalania się kamery od obiektu)

- atrybuty jednorodne (uniforms) są dostępne dla obu shaderów (VS, FS) i przechowują dane, które są stałe w danym przebiegu programu

- funkcja odbicia
  - światło odbite = światło wpadające * funkcja odbicia
  - komponenty funkcji odbicia: ambient, diffuse, specular (światło podstawowe, rozproszone światło odbite, skupione światło odbite - połysk)

- języki cieniowania
  - CPU: C, Cpp, Java, specjalne
  - GPU: assembler, Cg (C for graphics), kompilowane języki wysokopoziomowe
  - GLSL - OpenGL Shading Language (oparty na Cpp)

- przyspieszanie shaderów
  - zapamiętywanie pewnych rzeczy które się nie zmieniają: np. ustawienie obiektów
  - Renderowanie kafelkowe (myśl: SOWW) - podział pola widzenia na kafelki (przetwarzanie współbieżne) -> obiekty obecne na kilku kafelkach są przetwarzane nadmiarowo

- doooooobra styknie

## Metody badawcze w informatyce

- SLR - wybór repozytoriów, opracowanie zapytania, kryteria włączenia i wyłączenia, selekcja po tytule i abstrakcie, usunięcie duplikatów, selekcja po pełnym tekście, snowballing, ekstrakcja (synteza) wiedzy
- planowanie eksperymentu
  - zmienna niezależna (badana, np. rozmiar sieci, dane)
  - zmienna zależna (coś zależnego od modyfikacji zmiennej niezależnej, np. skuteczność klasyfikacji modelu)
  - operacjonalizacja zmiennych (nazwa, typ, zakres)
- ankiety
  - indywidualne (pytania otwarte, plan na przebieg rozmowy, w rozmowie może wyjść coś więcej)
  - focus group (drużyna pierścienia, kilku badaczy i kilku więcej uczestników (interesariuszy, problem-driven, trochę jak burza mózgów, najpierw indywidualne dłubanie, potem dyskusja))
  - kwestionariusze (ankiety online dla wieelu uczestników, google forms)
- badanie pilotażowe
  - wstępne badanie mające na celu weryfikację wstępnego zrozumienia badanego zjawiska oraz potwierdzenie przydatności wybranych metod i narzędzi badawczych
- studium przypadku
  - badanie zjawiska w naturalnym kontekście, bez manipulacji zmiennymi jak w przypadku eksperymentu, polega na wielu źródłach dowodów
- action research - projekt w korporacji, bazujący na dotychczasowej wiedzy i mający na celu rozwiązanie jakiegoś problemu

## Podstawy analizy rynków kapitałowych

SKIP

## Projekt badawczy

- rozpoznawanie tonu w języku mandaryńskim
- teza: algorytmy uczenia maszynowego mogą osiągnąć sprawność w rozpoznawaniu tonu w języku mandaryńskim zbliżoną do oceny eksperckiej
- dane: nagrania audio studentów PG wypowiadających chińskie słowa
- algorytmy: CNN, Transformer
- zmienna: algorytm

## Systemy obliczeniowe wysokiej wydajności

[prep](E:\C_Users_kubak\MGR_SEM1\SOWW\prep\opr.pdf)

- kiedy używać MPI (Message Passing Interface)?
  - każdy proces ma dostęp tylko do swojej pamięci, typowo dane przesyłane są komunikatami pomiędzy węzłami master - slave
  - MPI daje większą kontrolę nad wykonywaniem programu, w tym: dystrybucją danych, równoważeniem obciążenia (OpenMP automatycznie przypisuje pracę do wątków)
- kiedy używać OpenMP?
  - kiedy pożądana jest pamięć współdzielona (każdy wątek ma dostęp do ogółu danych)
  - kiedy zadanie nie ma zbyt dużej złożoności, wystarcza prostsze rozwiązanie (MPI daje większą kontrolę nad działaniem programu, jest elastyczniejszy i bardziej skalowalny)
- architektura CUDA (Compute Unified Device Architecture)?
  - platforma przetwarzania współbieżnego wykorzystująca jednostki GPU opracowana przez NVIDIA
  - GPU składa się z bloków wątków
  - w każdym bloku wątki pracują wspólnie i posiadają wspólną pamięć, jest też pamięć globalna
  - typowy przepływ działania programu to: przesyłanie danych wejściowych na GPU -> uruchomienie obliczeń na GPU -> przesłanie wyników na CPU
- kiedy używać połączeń powyższych?
  - typowe jest połączenie MPI i OpenMP - węzły w klastrze bez wspólnej pamięci współpracują wg MPI, a każdy samodzielny węzęł wspiera wielowątkowość i wykorzystuje OpenMP
  - na podobnej zasadzie łączy się również MPI i CUDA
  - można połączyć wszystkie 3 - OpenMP odpowiada za zrównoleglenie wykonania na wątki, z których każdy ma przypisaną oddzielną GPU
- kiedy warto stosować GPU?
  - gdy wykonanie algorytmów na dużym zbiorze danych można zrównoleglić rozbijając go na paczki
  - gdy ilość wykonywanych przez proces operacji jest stosunkowo duża względem natężenia komunikacji CPU-GPU
  - gdy operacje dają się podzielić na niezależne działania
  - algorytmy w grafice komputerowej (np. operacje na macierzach, przesuwanie tekstur)
- kiedy lepiej stosować CPU?
  - gdy operacje są sekwencyjne i nie podlegają zrównolegleniu
  - gdy algorytm wykonuje sporo operacji I/O
  - gdy dane nie mają zbyt dużej objętości
- podstawowe operacje MPI
  - sprawdzanie id procesu i liczby procesów (id == 0 ? MASTER : SLAVE)
  - MPI_SEND - blokujący send - zwraca gdy druga strona odbierze dane
  - MPI_RECV - blokujący receive - zwraca gdy dane zostaną odebrane
  - MPI_ISEND - nieblokujący send - zwraca po rozpoczęciu przesyłania danych
  - MPI_IRECV - nieblokujący receive - zwraca po rozpoczęciu odbierania danych
  - MPI_WAIT - oczekiwanie na zakończenie operacji nieblokującej
  - geometric parallelism - geometryczny podział problemu "w kratkę" - procesy zajmują się przypisanymi kafelkami
- podstawowe operacje OpenMP
  - wykorzystuje się dyrektywy `#pragma` w cpp oraz współdzielone dane, co eliminuje potrzebę ręcznego definiowania komunikacji pomiędzy wątkami jak w MPI
  - aby zabezpieczyć się przed wyścigami definiuje się sekcje krytyczne (zmienne lub całe fragmenty kodu, do których w jednej chwili ma dostęp tylko jeden wątek)
  - `#pragma omp for` przydziela kolejne iteracje wybranym wątkom

## Technologie przetwarzania danych przestrzennych

- GIS - Geographic Information System
  - skanowanie map
  - GPS, LiDAR
  - zdjęcia lotnicze
  - obrazy satelitarne

- modele topologiczne
  - domyślny (spaghetti, operacje topologiczne ad hoc, brak walidacji)
  - jawny (dane topologiczne w osobnej bazie danych, hierarchia obiektów)

- operacje topologiczne
  - touches
  - contains
  - crosses
  - overlaps
  - operatory z teorii zbiorów
  - buffer - wszystko w promieniu r
  - dissolve (gminy -> powiaty)
  - clip

- indeksowanie
  - quadtree - drzewo czwórkowe do indeksowania w 2D
  - octtree - drzewo ósemkowe do indeksowania w 3D
  - R-Tree - nieregularna dekompozycja, liście to indeksowane obiekty bez redundancji

- rozdzielczość
  - przestrzenna - odległość między środkami dwóch pikseli
  - czasowa - czas rewizyty (do ponownego wykonania zdjęcia w tym samym miejscu)

## Systemy uczące się

- rodzaje uczenia się
  - nadzorowane (klasyfikacja, regresja/aproksymacja)
  - nienadzorowane (grupowanie)
  - ze wzmocnieniem (środowisko-akcja-kara-nagroda)
  - na podstawie zapytań (?)
- drzewa decyzyjne
  - szybkie, czytelne, złożone problemy, różnorodne cechy
  - szybki wzrost drzewa przy większej liczbie klas
  - wybierając atrybut podziału węzła na podstawie współczynnika przyrostu, lub chi-square
  - kryterium stopu
  - przycinanie (w przypadku nadmiernego dopasowania)
    - oddzielny zbiór przycinania lub oryginalny zbiór
    - można przycinać od liści i od korzenia
- lasy losowe
  - wiele drzew decyzyjnych uczonych na różnych danych lub w różny sposób
  - dzielenie skomplikowanych problemów na prostsze podproblemy
  - wynik demokratyczny
  - dobre jak jest bardzo dużo danych lub bardzo dużo cech
- brakujące atrybuty
  - pomijanie
  - wypełnianie (losowe na przykładzie pozostałych przykładów)
  - traktowanie wartości nieznanej jako dopuszczalnego wariantu
- dyskretyzacja
  - atrybut w dziedzinie ciągłej na dyskretną
  - można prymitywnie, ale można np. uwzględnić rozkład wartości w zbiorze danych
  - dyskretyzacja zstępująca, wstępująca (łączenie przedziałów)
- sieci bayesowskie
  - czytelne
  - wiedza o zależnościach przyczynowych
  - uczenie struktury sieci i wartości parametrów (prawdopodobieństw warunkowych) => wnioskowanie
  - dwie sieci są równoważne jeśli mają te same krawędzie (niezależnie od kierunku) i takie same połączenia typu X->Y<-Z
  - ze względu na powyższe, lepiej nie szukać konkretnej sieci tylko wzorca
- grupowanie
  - cel: wykrywanie skupisk (klastrów)
  - uczenie nienadzorowane (bez nauczyciela)
  - podobieństwo przykładów w grupie wg wybranej miary odległości (np. euklidesowa)
  - k-means - wybieramy centra grup, przypisujemy do nich najbliższe punkty, aktualizujemy centra jako średnie poszczególnych grup, loop
    - sztywna liczba skupisk, lokalne minimum, brak odporności na zaszumienie
    - można przeprowadzić dla różnych liczb skupisk i wybrać optimum
  - k-medoids - zamiast średniej wartości, za centrum przyjmuje się wybrane przykłady
  - CLARA - polega na podziałach na podgrupy i scalaniu wyników
  - mieszaniny gaussowskie
    - wiemy że dane stanowią L skupisk o rozkładach normalnych
    - wyznaczamy najbardziej prawdopodobne rozkłady i przypisujemy przykłady do skupisk
    - EM - estimatization maximalization - wyznaczamy przynależność na podstawie parametrów rozkładów <-> nadpisujemy parametry rozkładów
  - grupowanie hierarchiczne
    - wstępujące (aglomeracyjne) - tworzenie grup jednoprzykładowych i łączenie ich w coraz większe skupiska (łączenie najbliższych grup)
      - powstaje drzewo
    - zstępujące - dzielenie całego zbiory na mniejsze podzbiory (wybiera się liść do podziału na podstawie określonego kryterium)
  - grupowanie gęstościowe (DBSCAN)
    - brak ograniczeń dot. liczby i kształtu skupisk
    - wybieranie regionów na podstawie zagęszczenia przykładów -> łączenie regionów
    - epsilon - promień sąsiedztwa
    - MinPts - liczba sąsiadów w promieniu epsilon
      - punkt centralny (zawiera conajmniej MinPts sąsiadów), punkt graniczny (zawiera mniej niż MinPts)
    - buduje się graf z punktów centralnych, które połączone są krawędziami jeśli są w odległości mniejszej niż epsilon
    - trudność doboru parametrów
    - punkty odstające (nienależące do żadnej grupy -> odporność na szum)
    - HDBSCAN (Hierarchical Density-Based Spatial Clustering of Applications with Noise)
      - radzi sobie ze skupiskami o różnej gęstości
      - automatycznie dobiera parametry (brak czułości na epsilon i MinPts to zaleta)
      - po utworzeniu hierarchii klastrów
      - parametr - MinClusterSize
      - tworzony jest graf ważony na podstawie odległości między punktami, następnie wybrane (długie) krawędzie są usuwane (tworzymy minimalne drzewo spinające)
      - na podstawie minimalnego drzewa spinającego powstaje hierarchia (patrz: grupowanie hierarchiczne)
      - skupiska w hierarchii rozbija się z uwzględnieniem parametru MinClusterSize

## Widzenie komputerowe

- reprezentacja obrazu
  - histogramy
  - stopień wypełnienia pól
  - cechy prostokątowe
  - surowe
- czyszczenie danych
  - usuwanie niespójności, duplikatów, przykładów odstających
    - przykłady odstające wykrywa się np na podstawie znanego rozkładu danych (parametr rozkładu -> metoda parametryczna)
    - metoda odległościowa - odległość punktu od sąsiadów (grupowanie)
    - autokoder - blok kodujący i dekodujący, który ma zwrócić to samo (MSE)
    - usuwanie, wypełnianie, normalizacja
- cechy
  - ilościowe ciągłe/dyskretne
  - kategoryczne
  - wektory cech
  - przydatność cech (znalezienie optymalnego podzbioru cech jest NP-zupełne)
- selekcja cech
  - branch and bound
    - jeśli kryterium oceny zestawu cech jest MONOTONICZNE, można podzbiory cech uporządkować w drzewo i przeszukać tylko jego część, żeby znaleźć optimum
  - sekwencyjne dodawanie cechy (r cech), która najbardziej zwiększy kryterium
  - analogicznie sekwencyjne usuwanie cech
  - dodaj l, odejmij r
  - przeszukiwanie wiązkowe: mamy K jednoelementowych podzbiorów cech, które powiększamy stosując kryterium
- ocena cech
  - współczynniki korelacji
  - wzajemna informacja
  - chi-kwadrat (zależność między cechą a klasą)
  - drzewo decyzyjne, LASSO (regresja)
- wariancja / obciążenie - nadmierne dopasowanie / niedopasowanie
- ekstrakcja cech
  - odwzorowanie do przestrzeni o mniejszej wymiarowości
  - z nauczycielem - uwzględnia się wiedzę o przynależności obiektów do klas
  - analiza głównych składowych
    - nowe cechy są liniową kombinacją nieskorelowanych cech pierwotnych, która zapewnia maksymalną wariancję
    - metoda sprowadza się do znalezienia kilku wektorów współczynników (wektorów własnych macierzy kowariancji), tworzących macierz transformacji, przez którą przemnaża się wektor cech pierwotnych
    - macierz kowariancji -> wektory własne maksymalizujące wariancję -> macierz transformacji -> wyjściowy wektor cech
  - liniowa analiza dyskryminacyjna
    - szukanie współczynników funkcji dyskryminacyjnej
  - autokoder
- systemy wielu klasyfikatorów
  - ten sam klasyfikator, różne podzbiory danych (bagging)
  - ten sam zbiór danych, różne klasyfikatory
  - ten sam zbiór danych, ten sam klasyfikator, różne parametry algorytmu uczenia
  - boosting - przypisywanie wagi przykładom ze zbioru uczącego -> tworzenie NASTĘPNEGO klasyfikatora -> zwiększanie wag błędnie sklasyfikowanych przykładów (otrzymujemy sekwencję klasyfikatorów, wynik to suma ważona)

## Współczesne aplikacje programowania funkcyjnego

- wszystko jest funkcją
- nie edytujemy zmiennych -> rekursja
- czysta funkcja - brak wpływu na środowisko, idealna powtarzalność (deterministyczność, jak funkcje matematyczne)
- tail recursion - rekursywne wywołanie jest ostatnią operacją funkcji -> program wykonuje się bez ryzyka Stack Overflow
- operacje na listach - sort, filter, map, fold (accumulate, reduce)
- konstrukcje match-case
- railway programming (two-track model, error handling)
- DDD (domain-driven design) - wytwarzanie oprogramowania pod domenę, na podstawie języka i zależności biznesowych a nie architektonicznych bloczków (baza danych, interfejsy)
- języki: F#, python, javascript, elm (kompilowany do html + js + css)
- MONADY
  konstruktor abstrakcyjnego typu danych; kontener opakuwujący wartość zapewniając SEKWENCYJNOŚĆ i obsługę kontekstów wyjątkowych, takich jak błędy i wartości puste

## Modelowanie i symulacja systemów

Finite Difference Method, Finite Element Methods, Monte Carlo Methods, Physics Informed Neural Networks

- FEM to technika interpolacyjna, bardziej elastyczna niż FD bo wykorzystuje funkcje ciągłe zamiast regularnej kratki
- efekt Runge'go
- próbkowanie przeciwstawne w MC - redukcja wariancji poprzez zastosowanie par przeciwstawnych zmiennych losowych

## Licencjonowanie oprogramowania

- Open source vs Free Software Foundation
  - OS - dostęp do kodu źródłowego
  - FSF - własność intelektualna jest nieetyczna i hamuje rozwój
    - 4 wolności
      - uruchamianie
      - analiza i dostosowywanie
      - redystrybucja
      - ulepszanie i rozpowszechnianie poprawek
    - GPL - General Public License
- Licencje
  - MIT - możesz wszystko tylko nie przypisywać sobie autorstwo
  - BSD - zakaz reklamowania się autorem, wzmianka w dokumentacji
  - Apache 2.0 - zezwala na używanie zamkniętego kodu w trakcie wytwarzania swojego produktu (nie jest "copyleft")
  - GPL - licencyjny wirus - wszystko czego dotknie ma być też GPL
- DRM - Digital Right Management
  - zapobieganie nieautoryzowanemu dostępowi do danych chronionych, kopiowaniu i redystrybucji
  - basically uzyskanie dostępu nie daje produktu (np. muzyczki) na własność
  - np. ograniczanie ilości urządzeń na których jest dostęp
  - np. ściągnięta muzyczka może mieć w metadanych info o urządzeniu na którym można ją odtworzyć
  - np. do samego odszyfrowania treści trzeba zaakceptować licencję
  - GPLv3 walczy z DRM

## Technologie społeczeństwa informacyjnego

- globalna infrastruktura informacyjna - wszystkie instytucje i całość infrastruktury IT na świecie
- społeczeństwo informacyjne
  - społeczeństwo w którym kluczową wartość stanowi wiedza i jej przepływ
  - szeroki dostęp do informacji
  - digitalizacja mediów i usług
  - globalna komunikacja
  - ehandel, epraca, eedukacja, eadministracja
- QoS - quality of service - techniczne aspekty jakości serwisu, takie jak dostępność, jakość połączenia, opóźnienie, przepustowość
- QoE - quality of entertainment - subiektywna jakość serwisu, satysfakcja użytkownika, mierzona poprzez ankietyzację, oceny i feedback
- NGN - next generation network - sieci telekomunikacyjne oparte na protokole IP, któe mają zastąpić tradycyjne sieci telefoniczne
  - realizowane np. połączeniem telefonu, telewizji i internetu kablem światłowodowym do domu
  - wirtualizacja
    - wykorzystanie hypervisor'a do utworzenia warstwy wirtualnej, uniezależnionej od hardware'u i lokalnego środowiska
    - efektywne wykorzystanie hardware'u, skalowalność, zarządzanie
    - bazowa technologia za platformami chmurowymi (MS azure, AWS, google cloud)

## Zarządzanie produktem w branży IT

- Metody kreowania produktów IT i analizy rynku
  - analiza SWOT
  - analiza wymagań użytkowników
  - definiowanie grup odbiorczych, kontrahentów, dostawców
  - opracowywanie strategii tworzenia prototypu, produktu końcowego, marketingu i wdrażania
  - MVP - minimal viable product -> start-up
  - mini-maxi (strategia konkurencyjna) - minimalizacja słabych stron, maksymalizacja wykorzystania szans
  - maxi-mini (strategi konserwatywna) - minimalizacja zagrożeń, maksymalizacja mocnych stron
  - maxi-maxi (strategia agresywna) - maksymalne wykorzystanie szans i mocnych stron
  - mini-mini (strategia defensywna) - słabość firmy i niekorzystne otoczenie

- zwinność
  - kontakt z klientem
  - turbo komunikacja wewnątrz zespołu (daily, sprinty)
  - rozdzielenie kierownika projektu i scrum mastera (pilnuje zgodności z przyjętą metodyką, utrzymuje kontakt z product owner'em)

## Elementy bioinformatyki

- drzewo filogenetyczne - drzewko sekwencji genetycznych, w którym każdy węzeł odpowiada sekwencji danego gatunku, a węzły wychodzące wprowadzają nowe cechy
