# UŻYWALNE ŚRODOWISKA

## [MINIHACK]()

uproszczony [nethack](#nethack), bardziej zasobo oszczędny

## [BOXWORLD](https://arxiv.org/abs/1806.01830)

Mapa 12x12 z kluczami i skrzynkami rozłożonymi w losowych miejscach, klucze otwierają skrzynki, celem jest znalezienie klejnotu który znajduje się w ktorejś skrzynce, ma jakiś potencjał na parametryzacje chociaż imo zbyt łatwo określić kolejność trudności zadań

## [MAZE]

Prosty Labirynt, całkiem dobry sprawdzający env, trochę jednak basic

## MULTICAR RACING

Srodowisko posiadające mapę i narysowaną na niej trasę, celem jest przejechanie trasy jak najszybciej

---
    Trackmania może być pewnym rozszerzeniem tego konceptu szczególnie z dodaniem trzeciego wymiaru i mozliwości tworzenia tras które mają wiele rozgałęzień czy pewne modyfikatory
---

# NIEZBYT UŻYWALNE ŚRODOWISKA / POSIADAJĄCE LEPSZE LUB MNIEJ ZASOBOŻERNE ALTERNATYWY

## [NETHACK](https://arxiv.org/abs/2006.13760) 

Wielopoziomowy proceduralnie generowany dungeon crawler. Bardzo dużo różnorodnych przeciwników, efektów, przedmiotów i statystyk. Celem jest dojście do najniższego poziomu zdobycie amuletu a potem ucieknięcie z dungeonu. Wynikiem może być wiele różnych rzeczy np wewnętrzny wynik gry czy ilość zdobytego złota

## [DEEPMIND LAB](https://github.com/deepmind/lab#upstream-sources)

Srodowisko zbudowane z użyciem silnika quake'a wiele różnych zadań, z interesujących :

-  Proceduralnie generowany labirynt
-  Laser tag - walka z przeciwnikami używając lasera, celem zabicie jak największej ilości wrogów

## Pixel dungeon czy Issac

Może coś takiego, trochę nethack case

## Rouge Legacy

Może też


## [Avalon](https://arxiv.org/pdf/2210.13417.pdf)

Surviwal w 3d z generowaną proceduralnie mapą

## [Procgen Benchmark](https://arxiv.org/pdf/1912.01588.pdf)

Być może interesujące

- StarPilot - side scroller z proceduralnie generowanymi wrogami
- CaveFlyer - bardzo uproszony nethack
- DodgeBall 
 i sporo innych

### Niestety nie ma możliwości ustawiania parametrów więc trzeba byłoby ostro modyfikować

# COMPETETIVE

## Bomberman

Możemy wziąć proceduralnie generowane mapy, z proceduralnie generowanymi przeciwnikami, można dodać jakieś powerupy aby zróznicować rozgrywkę









## [Sokoban, Rubik, INT](https://arxiv.org/pdf/2206.00702.pdf)


## [Home navigation](https://github.com/clvrai/awesome-rl-envs#home-more-navigation)

Całkiem duży wybór, parametryzowanie środowiska chyba odpada, za to można naprawdę mocno customizować zadania, prawdopodobnie bardzo zasobożerne środowisko to uczenia

## [Clusters](https://griddly.readthedocs.io/en/latest/games/Clusters/index.html)

Bardzo podobne do Sokobana jeśli dobrze rozumiem zasady, cięzko to parametryzować

## [Lights Out]
Bardzo proste, chyba trochę zbyt i nie wydaje mi się że nadaje się do parametryzacji

## [24]

Mało możliwości, słaba parametryzacja, cięzko stworzyć rozwiązywalne poziomy, imo out

## [Game of 15]

Mało różnych początkowych pól, bardzo skończona ilość plansz, cięzko testować wyniki, imo out

## [Baba Is You](https://github.com/utilForever/baba-is-auto)

Ciekawy gym, możliwe że trochę zbyt skomplikowany (jednak da się w środku zasymulować maszynę turinga), na jakimś pewnym podzbiorze można próbować parametryzacji ale osobiście bym się w to nie pchał bo całkiem dokładnie trzebaby wydaje się określać problemy i sprowadziłoby to środowisko do innych środowisk dużo mniej skomplikowanych


## [health gym]

Nie za bardzo łapię co mozna wymyśleć z samymi danymi, można próbować tworzyć ręcznie jakiegoś gyma ale ostatecznie nie mamy pewności poprawności wyników

## NP-complete (dominating set, TSP/cykl Hamiltona, vertex cover)

Wydaje się że to niezbyt viable problemy dla rlowych agentów

## [Ice Slider](https://github.com/martius-lab/puzzlegen)

Całkiem dobry env, z tym że nie wydaje się żeby różnił się jakoś strasznie od z [zwykłego labiryntu](#maze) co trochę zmniejsza jego pożyteczność

## Sudoku

Całkiem dobre, może nawet w pewny sposób da się sparametryzować

## Kakuro

Wydaje się że sudoku case

## Rush Hour

Podobne do sokobana czy clusters, fajniejesze jednak o tyle że agent nie może ustawić się z autamatu przegrywalnym state-cie

## [Forest fire](https://github.com/elbecerrasoto/gym-cellular-automata)

Jest jakiś potencjał na parametryzacje, koncepcyjnie proste, z drugiej strony wydaje się że nagrody są bardzo gęsto co trochę mało daje zysków z acl

## [Backpack Problem]

Wydaje się koncepcyjnie podobne do sudoku, sudoku jednak wydaje się ciekawszym problemem

## [Compiler Gym](https://arxiv.org/pdf/2109.08267.pdf)

Wydaje się że bardzo cięzko generować nowe problemy które możnaby optymalizować, ciężko sprawdzać też poprawność wygenerowanego kodu

## [TorchCraft](https://arxiv.org/pdf/1611.00625.pdf)

Trochę rozwinięcie [boxworlda](#boxworld). Pełny rts, trochę 1v1 game co może nie być oczekiwane

## [MazeBase](https://arxiv.org/pdf/1511.07401.pdf)


## [RLLAB : Mountain Car]

## [RLLAB : Swimming Gather]

## Decimal Number Addition

Za proste, mało ciekawe

## [MineCraft Maze](https://github.com/tambetm/gym-minecraft)

Kolejna wersja nethack / maze 

## [Mujoco Ant]

Trochę boxworld z dodaną fizyką

## [Robot arm]

Podobna klasa enva do home navigation z dodaną fizyką,


## [Bipedal Walker]


## Boulder Dash
