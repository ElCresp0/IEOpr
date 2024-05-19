# MSI PREP
## Informatyka afektywna -> *modele emocji
### affective - podstawowe założenie, affect-aware - dodatkowa funkcjonalność
### model emocji Ekmana
- uniwersalna mimika dla niektórych emocji
### model emocji Plutchika
- wykres intensywności i podobieństwa emocji
- emocje przeciwne na przeciwległych krańcach
### model emocji dwuwymiarowy
- wartość (pozytwna-negatywna)
- pobudzenie
### model emocji trójwymiarwy (PAD)
- pleasure, arousal, dominance
### model emocji Langa (VAL)
- wartość, arousal, dominance
### AU - action unit
- jednostka przy FACS - Facial Action Coding System
- atomowa cecha wyrazu twarzy - np. uniesiona brew
- można automatycznie etykietować
## problemy z sygnałami fizjologicznymi
- opóźnienie - np. zmiana pulsu po 5s
- zależność od osobnika - różne organizmy mogą różnie reagować
- są różne sygnały fizjo - przewodnictwo skóry (pot), temperatura, tętno, częstość oddechu
## ERF - Emotion Recognition Framework
- rozgraniczenie rozpoznawania emocji od samej mechaniki gry
- na wejściu ERF dane z czujników - obraz, głębia, dźwięk, sensory fizjologiczne, zachowanie w grze
- na wyjściu szacowany stan emocjonalny gracza
- dobrze jest wykorzystywać pomiary z kilku kanałów
## sensory głębi
- pasywne
    - Triangulacja
    - cienie, tekstura itd.
- aktywne
    - time delay
        - interferometria
        - time-of-flight (pulse wave / continuous wave)
        - e.g. LiDAR
    - triangulation
        - structured light pattern (Kinect)
        - single spot projection
        - ^ generalnie wyświetla się jakieś punkciki np z dwóch źródeł i coś je rejestruje
## bonus: LiDAR vs 3d ToF Sensors
- LiDAR wykorzystuje kilka źródeł światła (laserów) o różnych częstotliwościach
## pomiary głębi
- lasery emitują wzorzec w podczerwieni
- kamery rejestrują obraz w podczerwieni
- kalibracja na podstawie <i>wzorca referencyjnego</i> na płaszczyźnie w znajej odległości
- pomiary na podstawie porównywania z wzorcem referencyjnym z pamięci
## Kinect
- skład
    - kamera RGB
    - sensor głębi (podczerwień) + emiter
    - mikrofony
    - sensor akcelerometrii (orientacja)
    - Kinect for windows ma Tilt motor (napęd do przechylania)
    - światełko LED
- zastosowania
    - NUI - Natural User Interface
    - Kinect for XBox
    - Kinect for PC
- Kinect for windows > Kinnct for XBox
- nowy Kinect 2.0 jest mniejszy, cięższy, ładniejszy, ma nową technologię Time-of-flight, lepsze SDK
## Skeleton tracking
- dwa tryby
    - seated: 10 joint pointów
    - default: kolejne 10
## microsoft hololens
- te super okularki dla armii
- Kinect v3, Kinect v4 = Azure Kinect
- head tracking, eye tracking, depth, akcelerometr, żyroskop
## intel RealSense
- sensory RGB-D(epth)
- małe, wbudowany procesor
- hand tracking - 22 points jak skeleton tracking
## Augumented vs Mixed Reality
- AR - wzbogacanie świata o wirtualne informacje/elementy
- MR - AR + możliwość interakcji z wirtualnymi elementami
- Augumented Virtuality - wirtualne odwzorowanie świata rzeczywistego z zachowaniem pewnych elementów
- Virtual Reality - w pełni wirtualne odwzorowanie świata rzeczywistego
## klasyfikacja AR
- wyświetlacz
    - optical see-through - widzimy obraz na żywo + wyświetlane projekcje
        - np. head-up display, head mounted projection display
    - video/camera see-through - widzimy obraz rejestrowany przez kamerę z dodanymi elementami
        - np. camera pass-through, head mounted display
- miejsce użycia
    - internal
    - outside
- śledzenie użytkownika / otoczenia, obiektów
- lokalizacja - bezwzględna (GPS), względna (otoczenie)
## śledzenie pozycji i gestów
- inside-in - sensory na użytkowniku np. rękawiczki VR
- inside-out - sensory na użytkowniku, oparte o zewnętrzne obiekty, np okulary AR
- outside-in - zewnętrzne użytkowniku wykorzystujące markery/kontrolery użytkownika
## środowiska wytwórcze do AR
- Unity XR, Unreal Engine
- Google ARCore (na androidy)
- Apple ARKit (na ios, iPadOS)
- Windows Mixed Reality (na nagłowne wyświetlacze)
- biblioteki
    - ARToolKit - otwarta, wieloplatformowa
    - Vuforia - SDK dla urządzeń mobilnych, wieloplatformowa (android, ios, windows)
    - OpenCV
- standard Khronos OpenXR (respektowany nawet przez facebooka, microsoft)