# Kryptografia w cyberbezpieczeństwie 2024
<i>bez krzywych eliptycznych</i> \
<i>Uwaga: z wyjątkiem pytań o charakterze wyraźnie opisowym należy udzielając odpowiedzi posługiwać się
formalną terminologią, notacją i argumentacją</i>

## 1. Opisz rodzaje potencjalnych intruzów i ich motywacje.
https://www.cs.toronto.edu/~arnold/347/17f/lectures/crypto/
- Eve \
Intruz pasywny, może podsłuchiwać pasmo. Liczy na słabość szyfrowania i inne okoliczności (np. częstotliwość, powtarzalność komunikacji) możliwe do zaobserwowania w ruchu sieciowym Alice <-> Bob, aby zdobyć informacje dające jej korzyść (w najlepszym wypadku samą treść wiadomości)
- Mallory \
Intruz aktywny, może wpływać na treść komunikacji (podmieniać bajty, wysyłać wiadomości, podszywać się). Do jego motywacji należy złamanie klucza szyfrującego, nieautoryzowany dostęp do informacji, zaburzenie poprawności działąnia systemu, ataki Man-in-the-Middle, playback (replay)
## 2. Sklasyfikuj pasywne i aktywne zagrożenia dla bezpieczeństwa informacji
- zagrożenia pasywne
    - podsłuchiwanie - zbieranie informacji z ruchu sieciowego
    - analiza ruchu sieciowego (dane takie jak częstotliwość, powtarzalność wzorców wiadomości)
    - sniffing - szczególny przypadek eavesdroppingu - goły odczyt pakietów sieciowych \
    https://security.stackexchange.com/questions/195276/eavesdropping-vs-sniffing
- zagożenia aktywne
    - Man-in-the-Middle
    - wstrzykiwanie kodu
    - DoS
## 3. Wyjaśnij pojęcia: kryptologia, kryptografia, kryptoanaliza.
wykład, \
https://www.researchpublish.com/upload/book/Cryptology%20Cryptography-7391.pdf
- kryptografia \
nauka i <i>sztuka</i> tworzenia i stosowania szyfrów
- kryptoanaliza \
nauka i <i>sztuka</i> łamania szyfrów - jakiekolwiek działania dążące do podważenia osiągninięć kryptografii
- kryptologia \
kryptografia + kryptoanaliza
## 4. Wymień i krótko omów najważniejsze atrybuty bezpieczeństwa informacji.
https://www.geeksforgeeks.org/what-is-information-security/
### C I A - Confidentiality Integrity Availability
- C jak poufność \
ograniczenie dostępu do informacji uprawnionym i autoryzowanym jednostkom
- I jak integralność \
zachowania poprawności i kompletności danych - uniemożliwienie nieautoryzowanej edycji danych
- A jak dostępność \
zapewnienie autoryzowanego dostępu do danych zawsze, gdy jest to potrzebne
## 5. Co to jest system kryptograficzny (kryptosystem), wymień jego elementy i wyjaśnij, na czym opiera się jego bezpieczeństwo.
https://www.tutorialspoint.com/cryptography/cryptosystems.htm
### Kryptosystem - implementacja technik kryptograficznych osadzonych w toważyszącej im infrastrukturze, w celu zapewnienia bezpieczeństwa informacji
### Elementy kryptosystemu:
- plaintext
- algorytm szyfrujący (encryption alg.)
- szyfrogram
- algorytm deszyfrujący (decryption alg.)
- klucz szyfrujący
- klucz deszyfrujący ($\in$ przestrzeń kluczy)
### Bezpieczeństwo kryptosystemu
<i>Kerckhoff's Principle for Cryptosystem</i> ~ 19th century \
- Bezpieczeństwo systemu nie leży w utrzymaniu w sekrecie jego implementacji, tylko w samym kluczu. \
Tj., nawet jeśli cały kod kryptosystemu będzie publicznie dostępny, jego bezpieczeństwo powinno być <i>praktycznie</i> ($\ne$ matematycznie) niezachwiane.
```
1h
```

## 6. Podaj klasyfikację algorytmów kryptograficznych wraz z krótkim opisem poszczególnych klas.
https://www.edureka.co/blog/what-is-cryptography/
- Kryptografia klucza symetrycznego // nadawca i odbiorca współdzielą klucz do E(.), D(.)
    - Kryptografia klasyczna
        - transpozycja (permutacje) // plaintext -> pailnxett
        - substitution // plaintext -> bi41m73h7
        - Typowo łączy się te dwie rzeczy (np. DES)
    - Współczesna kryptografia
        - Strumieniowa \
        szyfruje bit/bajt strumienia naraz, szyfrowanie tego samego bitu/bajtu nie jest powtarzalne
        - Blokowa \
        szyfruje całe bloki plaintextu
            - ECB (Electronic CodeBook) // +zrównoleglenie -chosen plaintext attack
            - OFB (OutputFeedBack) // IV -> klucz zmienia się w czasie
            - CBC (Cipher Block Chaining) // K = IV + poprzedni Ciphertext
- Kryptografia klucza asymetrycznego // wykorzystuje parę klucz prywatny - klucz publiczny
    - np. RSA
## 7. Opisz rodzaje ataków na systemy kryptograficzne, porównaj wymagane zdolności intruza.
<span style="color:#aaaaff">wykład<span>
- spoofing \
Mallory podszywa się pod Alice i wysyła własne wiadomości
- man-in-the-middle \
Mallory odbiera wiadomości od Alice jako Bob, po czym wysyła własne do Boba jako Alice
- playback (replay) \
Mallory wysyła ponownie zarejestrowaną wcześniej, zaszyfrowaną wiadomość // timestamp
- random ciphertext \
Mallory wysyła do Boba losowy text, Bob traktuje go jak Ciphertext // formatowanie, checksumy
- key guessing \
Mallory i Eve mogą próbować odgadnąć klucz do ciphertextu - jeśli zdeszyfrowany kluczem zacznie przypominać wiadomość, są duże szanse że klucz jest właściwy
- eavesdropping \
podsłuchiwanie przez Eve, przypadek specjalny: sniffing
## 8. Jak ocenia się bezpieczeństwo algorytmów kryptograficznych wg Knudsena?
ask Leo aka AI-generated answer
- Wg Knudsena, "If it’s provably secure, it probably isn’t.", czyli nie wystarczy oceniać bezpieczeństwa alg. kryptograficznych w kontekście specyficznych form ataku, bo zawsze znajdzie się jakaś nowa strategia intruzów.
- Wszystkie klucze powinny być tak samo bezpieczne -> każdy bit klucza powinien w równym stopniu wpływać na wyjściowy szyfrogram
## 9. Jaka jest różnica między szyfrem a kodem?
- Kod polega na podmienianiu słów/wyrażeń na inne słowa na podstawie zbioru odwzorowań (codebook)
- Szyfr polega na algorytmach i operuje na znakach
## 10. Jakie oprócz kryptograficznych metody ochrony informacji można zastosować przeciwko intruzowi typu Eve?
- kryptosystem powinien być prosty w obsłudze aby ograniczyć ryzyko błędu ludzkiego
- klucze powinny być odpowiednio zarządzane i zmieniane, aby utrudnić ataki typu key guessing
- kryptosystem powinien polegać na sprawdzonych systemach i serwisach
- zarządzanie dostępami
## 11. Opisz podstawowe typy szyfrów opartych na komponentach S-box i P-box, scharakteryzuj ich bezpieczeństwo.
- substitution cipher
    - ciphertext-only - podmienianie znaków nie ukrywa częstotliwości ich występowania
- transposition cipher
    - chosen-plaintext -> porównujemy z ciphertextem ez
    - known-plaintext
- mix (DES)
    - krótki klucz -> brute force
    - side channel -> np. porównywanie czasu deszyfrowania
    - -> DES3
## 12. Omów bezpieczeństwo szyfru typu simple XOR przy szyfrowaniu tekstów w językach naturalnych.
- Bezpieczeństwo szyfru simple XOR przy szyfrowaniu tekstów w językach naturalnych jest zapewnione, jeśli klucz jest dłuższy od plaintextu, odpowiednio losowy, i nie jest ponownie używany (pseudorandomowe liczby o baaardzo długim cyklu -> szyfr strumieniowy).
- Przy powtarzalnym kluczu o mniejszej długości niż tekst, cyphertext-only:
    - szyfrogram należy xorować ze samym sobą przesuniętym o 1, 2, ... aż ilość nakładających się na siebie znaków będzie odpowiednio wysoka (cecha języków naturalnych) -> shift - długość klucza
    - znając długość klucza, wystarczy odgadywać słowa aż się odgadnie klucz (dictionary attack)
## 13. Opisz zalety i wady podstawowej wersji DES. 
Data Encryption Standard - zalety i wady
### zalety
- łączy substitution i transposition cipher
- łatwy w implementacji
- szybki, możliwe wsparcie sprzętowe
### wady
- krótki klucz, niektóre klucze są słabsze -> podatność na ataki brute-force
- był zaprojektowany na hardware, gorzej sobie radzi w warstwie sofware
## 14. Jak ilościowo ocenia się bezpieczeństwo ("siłę") kluczy kryptograficznych? 
- długość klucza - im większa (dla danego algorytmu), tym klucz trudniejszy jest do złamania
- losowość klucza - im lepszy generator liczb pseudolosowych (i użyte ziarno) tym lepiej
- te i inne parametry mogą być zależne od parametru bezpieczeństwa (security parameter $\lambda$)
- zapewnienie tej samej odporności na brute force wymaga dużo większej długości klucza publicznego niż symetrycznego
## 15. Co rozumiemy przez zarządzanie kluczami, jakie problemy i rozwiązania związane są z odświeżaniem kluczy?
https://www.splunk.com/en_us/blog/learn/key-management.html
- zarządzanie kluczami to wszystkie aktywności związane z kluczami w ich cyklu życia, w tym generowanie, przechowywanie, używanie, odświeżanie, wycofywanie (revoke)
- odświeżanie kluczy - czas życia klucza: maksymalna ilość danych , któe można bezpiecznie zaszyfrować danym kluczem
    - problem: generowanie następnego klucza na podstawie poprzedniego \
    rozwiązanie: tworzenie nowych kluczy od zera
    - problem: key recovery attacks \
    rozwiązanie: korzystanie z protokołów
    - problem: błędy transmisji podczas przesyłania klucza \
    rozwiązanie: checksuma
    - problem: podsłuchiwanie transmisji klucza przez Eve \
    rozwiązanie: rozbicie klucza na części przesyłane różnymi ścieżkami
    - problem: uwierzytelnienie Alice nadającej klucz \
    rozwiązanie: Trent, symetryczne funkcje jednokierunkowe (f_e_b(d_a))=f_f_g(d_b)(d_a)
## 16. Jakie dodatkowe zagrożenia stwarza intruz typu Mallory w porównaniu z Eve i jakie stosuje się przeciw niemu środki zaradcze?
<span style="color:#aaaaff"><u>z głowy</u></span> \
Mallory jest intruzem aktywnym, zna infrastrukturę i może na nią oddziaływać, tj odczytywać ale też wysyłać wiadomości, oraz podszywać się pod inne tożsamości.
- modyfikacja wiadomości -> checksumy
- ataki replay -> timestamp
- podszywanie się, ataki Man-in-the-middle -> uwierzytelnianie (klucze, podpisy)
- DoS -> monitorowanie i blokowanie podejrzanego ruchu

## 17. Jak przeciwdziałać atakom typu random ciphertext?
<span style="color:#aaaaff"><u>wykład</u><span>
- nadmiarowość - sensowne wiadomości powinny być małą cześcią wszystkich możliwych
- ustalone formatowanie
- checksumy

## 18. Co to jest nadmiarowość kodu i jak się ją wyraża, podaj przykład.
<span style="color:#aaaaff"><u>wykład</u><span>
Nadmiarowość kodu (inaczej redundancja informacyjna) zmienia entropię. Polega na dodawaniu bitów do wiadomości, aby zabezpieczyć się przed błędami nieintencjonalnymi

## 19. Opisz podstawowe tryby szyfrowania blokowego, omów ich zalety i wady z punktu widzenia zagrożeń stwarzanych przez intruza typu Mallory.
<span style="color:#aaaaff"><u>wykład</u><span>

### ECB

### OFB

### CBC

## 20. Opisz możliwe ataki przeciwko szyfrom strumieniowym w wykonaniu intruza typu Mallory.
<span style="color:#aaaaff"><u>wykład</u><span>

### atak known plaintext // nie działa
### atak replay/known-ciphertext
np. Mallory wie, że w wiadomości będzie "$1000" -> przechwytuje wiadomość, XORuje w tym miejscu bajty z ("$1000" xor "$2000") -> wynik: (C xor "$1000") XOR ("$1000" xor "$2000") = (C xor "$2000")
### atak chosen-IV
strzelanie w wartości IV w celu wykrycia nierandomowych wzorców w szyfrogramie

## 21. Co to jest funkcja skrótu, wymień jej cztery pożądane właściwości?
Fukcje skrótu w kryptografii to przekształcenia plaintextu na wyjście niezrozumiałe dla człowieka, o określonej długości. Pozwalają m.in. na potwierdzenie, że wiadomość nie została zmodyfikowana przez trzecią stronę w czasie transferu. Istnieje ryzyko, że kilka różnych plaintextów zwróci identyczny skrót.
- jednostronność \
łatwo wykonać operację y = H(x) \
ciężko wyznaczyć x znając H, y
- odporność na kolizje \
jak najmniejsza ilość wiadomości o jendakowym haszu \
ciężko znaleźć input który dałby dany output
- odporność na brute-force \
duużo hashy do posprawdzania
- deterministyczna \
ten sam input -> ten sam output
- szybkość \
typowo funkcje skrótu są szybsze od szyfrowania symetrycznego
- propagowanie zmian \
mała zmiana na wejściu powinna mocno zmienić wyjście
## 22. Dlaczego atak metodą dnia urodzin jest łatwiejszy niż atak z zadanym przeciwobrazem (pre-image), podaj przykład odpowiednich obliczeń.
- Birthday attack nie wymaga klucza - wystarczy kolizja. Atakujący szuka pary różnych wiadomości dających taki sam hash (brute-force).
- pre-image attack polega na szukaniu plaintextu dającego taki sam hash jak jakiś zaobserwowany.
## 23. Jak systematycznie konstruować funkcje skrótu dla dowolnie długich wiadomości?
Jedną metodą jest hashowanie blokowe (SHA - Secure Hash Alorithm) \
wiadomość dzieli się na bloki określonej długości startując od wektora IV, haszuje się kolejne bloki wykorzystując w miejsce IV kolejne pośrednie hashe. \
\*zmiana jednego bitu w M wpływa na ~50% bitów hasha\*
## 24. Jak wyrażamy odporność funkcji skrótu na kolizje? \
Odporność funkcji skrótu na kolizje można wyrazić jako trudność w odnalezieniu dwóch różnych wejść dających taki sam hash. Historia pokazuje, że nie jest to metryka bezwzględna, ponieważ wraz z rozwojem technologii niektóre funkcje skrótu były obalane. \
Collision resistance można mierzyć w bitach (długość hasha) - 2^N to ilość permutacji do sprawdzenia w ataku brute-force.
## 25. Na czym polega zasada kompresji łańcuchowej w konstrukcji funkcji skrótu? 
Funkcję skrótu realizuje się na kolejnych blokach plaintextu, wykorzystując jako parametr (czynnik) część poprzedniego wyniku, począwszy od danego wektora IV. W ten sposób wynikowy skrót ma określoną wielkość, niezależną od wejścia. Przykład: SHA.
## 26. W jaki sposób funkcje skrótu stosuje się do uwierzytelniania, omów metody oparte na współdzieleniu haseł i kluczy symetrycznych oraz ich odporność na intruza typu Mallory.
\*HMAC - Hash-based Message Authentication Code\*
- hash wiadomości zaszyfrowany z wykorzystaniem klucza symetrycznego
    ```diff
    - Mallory musi złamać klucz
    - albo zorganizować birthday attack (znaleźć kolizję)
    ```
- hash na podstawie plaintextu z dolepionym hasłem znanym przez Alice i Boba
    ```diff
    + tanie bo nie wymaga szyfrowania
    - Mallory jeśli nie zna hasła, musiałby je wydobyć odwracając funkcję skrótu (gl)
    - ataki słownikowe na hasło
    ```
    - obrona przed atakiem słownikowym: collision-rich hash \
    wysyła się M, q=H(M||P), h=H(M||q) // P - hasło \
    jeśli u Boba coś się nie zgadza to Mallory jest wykryty
## 27. Scharakteryzuj cel, cechy i rodzaje protokołów kryptograficznych.
Protokoły kryptograficzne to programy złożone z podstawowych narzędzi kryptograficznych, takich jak algorytmy szyfrowania i deszyfowania, funkcje skrótu czy podpisy. Służą ustandaryzowaniu dobrych i sprawdzonych rozwiązań kryptograficznych. Umożliwia to ich użycie wszystkim stronom komunikacji, co ułatwia przeprowadzanie jej w granicach bezpieczeństwa.
- protokoły z arbitrem (Trent rozsądza spory)
- protokoły autoryzacji: Kerberos, SSL/TLS
    - challenge-response
- protokoły szyfrowania: RSA
- protokoły podpisu cyfrowego
- protokoły wymiany klucza: Diffie-Hellman
## 28. Opisz protokół bezpiecznego dostępu do bazy danych oparty na łańcuchu skrótów i scharakteryzuj jego wymagania.
- autoryzacja np. S/Key - każdy hash w łańcuchu jest jednorazowym kluczem, serwer sobie haszuje klucz i sprawdza czy się zgadza z następnym w łańcuchu
- autoryzacja sesji / autoryzacja transakcji
- wymagany jest wspólny wektor IV klienta i serwera
## 29. Przeciwko schematowi HMAC chronionemu hasłem intruz typu Mallory może wykonać atak słownikowy offline – w jaki sposób zmusić go do ataku online?
- silne hasła ofc
- <u>salting</u> - dodawanie unikalnej "soli" do haseł przed haszowaniem \
-> to samo hasło dla różnych użytkowników po posoleniu da inny hasz
- <b>obrona przed atakiem słownikowym: collision-rich hash \
    wysyła się M, q=H(M||P), h=H(M||q) // P - hasło \
    jeśli u Boba coś się nie zgadza to Mallory jest wykryty</b>
## 30. Opisz zasadę protokołów typu challenge-response.
Strona weryfikująca wysyła stronie weryfikowanej (proponentowi?) challenge - pewną wartość, którą strona weryfikowana musi przetworzyć z użyciem narzędzia kryptograficznego - np. zaszyfrować swoim kluczem / zahashować, aby udowodnić swoją tożsamość
## 31. Na czym polega protokół zobowiązania bitowego, podaj przykład i zastosowanie.
\*protokół karta-stół\* \
Protokół ten umożliwia jednej stronie zobowiązanie się do pewnej wartości bez całkowitego ujawniania jej. Druga strona ma możliwość zweryfikowania tego po ujawnieniu i wykrycia ewentualnej modyfikacji. \
### przykład
A <--- R <--------------- B // R - blob \
A ---> C = E_K(R, b) ---> B // K - klucz Alice, b - tajemniczy bit \
// czas ... \
A ---> K ---------------> B // dosłanie klucza dla odkrycia b
### zastosowanie
Przykładowym zastosowaniem są e-głosowania - zapewnia to tajność głosu obywatela
## 32. Do czego służy protokół Neumana-Stubblebine, opisz jego działanie i zalety.
Protokół Neumana-Stubblebine służy do autoryzacji stron komunikacji w niebezpiecznej sieci (internecie). Polega on na wygenerowaniu wspólnego klucza (K_AB) z pośrednictwem zaufanej trzeciej strony.
1. Alice wysyła do Boba Nonce (N_A) w plaintext
2. Bob wysyła na serwer swoją N_B, N_A i timestamp
3. serwer wysyła do Alice K_AB (w wersji zaszyfrowanej K_AS i K_BS) do dalszej komunikacji, N_A i timestamp do upewnienia, oraz N_B
4. Alice wysyła do Boba K_AB zaszyfrowany K_BS oraz N_B zaszyfrowane K_AB

Zalety:
```diff
+ A i B nie muszą mieć wcześniejszych relacji
+ wzajemna autoryzacja
+ nie wymaga synchronizacji zegarów
```
## 33. Jakie są motywacje rozważania problemu Private Set Intersection, podaj przykład odpowiedniego protokołu i scharakteryzuj jego wymagania.
https://fc14.ifca.ai/papers/fc14_submission_52.pdf \
Private Set intersection to technika, która pozwala dwóm stronom wyznaczyć część wspólną swoich zbiorów bez zdradzania pozostałych ich elementów. Przykładem protokołu wykorzystującego do tego zadania zewnętrzny serwer jest VD-PSI (verifyable delegated).
- Strony protokołu wysyłają na serwer zaszyfrowane dane (serwer nie musi być zaufany)
- serwer zwiększa skalę o całe rzędy wielkości
- działanie:
    1. K1 - klucz A,B; K2 - klucz B,T; S_A, S_B - sety
    2. A -> F_K1(S_A) -> T
    3. T -> losowa permutacja(F_K2(F_K1(S_A))) -> A
    4. B -> F_K2(F_K1(S_B)) -> A
    5. A wyznacza część wspólną podwójnie zaszyfrowanych S_A, S_B  // szyfrowanie homomorficzne
    6. A -> podwójnie zaszyfrowana część wspólna -> B // B zna oba klucze
    7. B pinguje serwer, żeby ten podał A tamtą permutację
    8. teraz A wie, na jakich pozycjach w jego zbiorze były elementy częsci wspólnej
- przykłady użycia:
    - znajdowanie wspólnych znajomych
    - porównywanie rekordów medycznych przez placówki
    - powiązania z ideą szyfru homomorficznego - przetwarzanie danych bez ich ujawniania
## 34. Porównaj kryptografię symetryczną i asymetryczną pod względem zapewniania różnych atrybutów bezpieczeństwa informacji.
- C jak poufność \
dane szyfrowane są kluczem, w przypadku kryptografii asym. można je następnie odszyfrować jedynie odpowiadającym mu kluczem prywatnym
- I jak integralność (integrity - spójność?) // czy dane zostały zmodyfikowane \
sym: wykorzystuje się funkcje skrótu \
asym: wykorzystuje się podpisy cyfrowe (podpisywanie kluczem prywatnym)
- A jak autoryzacja \
podobnie jak integralność - hashe / podpisy
- niezaprzeczalność \
sym: ciężka bo każdy z kluczem symetrycznym mógł wysłać wiadomość, wykorzystuje się odrębne protokoły, Trenta \
asym: nie można się wyprzeć wiadomości podpisanej cyfrowo kluczem prywatnym
## 35. Na czym polega i czemu służy postulowana własność symetrii funkcji jednokierunkowej?
<span style="color:#aaaaff"><u>wykład</u><span>
- służy do utworzenia klucza symetrycznego na podstawie kluczy <u>prywatnych</u> obu stron
- jednokierunkowa - y = f_g(x) łatwo; given y, x= ? trudno // g - (typowo) publiczny parametr
- symetryczna f_f_g(x)(x') = f_f_g(x')(x) // to odróżnia tę funkcję od hasha
- przebieg // d_A, d_B - klucze prywatne stron A,B \
A: e_A = f_g(d_A) ---> B \
B: e_B = f_g(d_B) ---> A \
A: K = f_e_B(d_A) = f_f_g(d_B)(d_A) \
B: K = f_e_A(d_B) = f_f_g(d_A)(d_B) \
w ten sposób A i B mają wspólny symetryczny klucz K
- nie ma tu autoryzacji, Mallory może podstawić e_M

## 36. W jaki sposób kryptografia asymetryczna rozwiązuje problem wymiany tajnego klucza? 
za pomocą symetrycznej funkji jednokierunkowej \
opis powyżej

## 37. Podaj przykład ataku kontekstowej modyfikacji wiadomości z podstawieniem klucza publicznego; jaki atrybut bezpieczeństwa informacji go uniemożliwia? 

## 38. Jak realizowane są podpisy cyfrowe w technice kryptografii asymetrycznej? 

## 39. Uzasadnij, że podpisany szyfrogram zapewnia wszystkie istotne atrybuty bezpieczeństwa informacji. 

## 40. Jaki problem i w jaki sposób rozwiązuje usługa etykiet czasowych? 

## 41. Dlaczego informacyjne sprzężenie zwrotne (echo odebranej wiadomości) może rodzić niepożądane skutki w obecności intruza typu Mallory?

## 42. Wyjaśnij pojęcia: faktoryzacja, kongruencja, reszta kwadratowa, modularna odwrotność, ciało skończone. 
## 43. Jakie operacje i pod jakimi warunkami można wykonywać na kongruencjach? 
## 44. Co stanowi Chińskie Twierdzenie o Resztach i jak można je wykorzystać przy bezpiecznym rozgłaszaniu grupowym? 
## 45. Objaśnij cel i zasadę działania schematu Shamira dzielenia sekretu w ciałach skończonych. 
## 46. Wyjaśnij pojęcia: grupa multiplikatywna, generator grupy, funkcja Φ Eulera, twierdzenie Fermata-Eulera. 
## 47. Jaka funkcja w ciałach skończonych ma własności jednokierunkowości i symetrii? 
## 48. Scharakteryzuj problem logarytmu dyskretnego i objaśnij jego przydatność w kryptografii. 
## 49. Opisz protokół Diffie-Hellmana wymiany klucza tajnego przez publiczny kanał komunikacyjny; jakie zapewnia on atrybuty bezpieczeństwa informacji? 
## 50. Jak funkcja wykładnicza w ciałach skończonych pomaga w wykonywaniu obliczeń na danych zaszyfrowanych? 
## 51. Uzasadnij, dlaczego funkcja potęgowa w ciałach skończonych jest przydatna w kryptografii asymetrycznej opartej na RSA. 
## 52. Opisz zasadę kryptoanalizy RSA z wykorzystaniem "tylnych drzwi". 
## 53. Opisz zasadę certyfikacji kluczy publicznych RSA. 
## 54. Opisz ideę i sposób realizacji ślepych podpisów cyfrowych z wykorzystaniem RSA. 
## 55. Dlaczego wybór tego samego modułu przez różnych użytkowników RSA może być niebezpieczny?