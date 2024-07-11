# Single Agent RL

### INTRINSIC MOTIVATION AND AUTOMATIC CURRICULA VIA ASYMMETRIC SELF-PLAY, Sukhbaatar et al. 2017

Alice i Ben walczą między sobą. Alice chce dać jak najtrudniejsze zadanie Benowi takie które Ben jest w stanie wykonać. Zadanie dawane
jest przez Alicje poprzez wykonanie jakiejś sekwencji akcji lądujące w jakimś stanie. Bob ma za zadanie wylądować w tym samym końcowym stanie lub powrót do początkowego stanu.\
Nagroda Boba to $-\gamma t_b$ gdzie $t_b$ to czas wykonania zadania przez Boba. Zatem chcemy zminimalizować czas wykonania zadania.\
Nagroda Alicji to $\gamma \max(0, t_b-t_a)$. Zatem maksymalizujemy różnice czasu wykonania zadania przez Alicję i Boba. 

### Teacher-Student Curriculum Learning, OpenAI 2017

Formalizacja TSLC (Teacher Student Curriculum Learning). Nauczyciel uczy studenta pewnego zadania. Rozwiązujemy to formułując POMDP (Częsciowo obserwowalny MDP).\
Stanem MDP jest pełny stan studenta, nie jest on widzialny dla nauczyciela.\
Akcją MDP jest wybranie przez nauczyciela zadania dla studenta\
Widocznymi obserwacjami w MDP są wyniki zadanych studentowi zadań\
Nagrodami w MDP są różnice pomiędzy wynikiem zadania porównując aktualny czas i moment poprzedniego wykonania akcji

Zaproponowane są 4 algorytmy:
 - Online : Używamy sparametryzowanej oczekiwanej średniej kroczącej ( $Q_t = \gamma r_t + (1- \gamma) Q_t(a)$). Akcja jest wybierana za pomocą strategii epsilon greedy lub samplowania boltzmanna 
 - Naiwny : Używamy tej samej strategii tylko używamy regresji liniowej po ostatnich K wynikach danej akcji
 - Window : Algorytm taki jak naiwny ale wykorzystujemy również czas w których te wyniki zostały osiągnięte
 - Sampling : Trzymamy w buforach nagrody otrzymane ze starych akcji. Samplujemy z każdego bufora a potem wybieramy akcje która ma najwyższy sample.

### Learning Goal Embeddings via Self-Play for Hierarchical Reinforcement Learning, Sukhbattar et al. 2018

Hierarchiczny RL to podejście do RL wykorzystujące wiele polityk w jednym rozwiązaniu tak aby polityki rozwiązywały problemy różnej wielkości. Polityka niższego poziomu rozwiązuje problemy zadane przez politykę wyższego rzędu.\
Rodzajem hierarchicznego RL jest podejście w którym polityka wyższego rzędu dyktuje zadania dla polityki niższego rzędu korzystąc z embeddingów podzadań.
Praca pokazuje sposób uczenia takich embeddingów.

Podejscie utrzymuje trzy polityki Alice, Bena i Charliego. Ben ma w sobie dodatkowo encoder który w pre-treningu jest używany do encodowania zadań w ramach embeddingu

Podejście wykonywane jest w dwóch fazach :
 - Pretrenowanie : W tej fazie uczymy Bena który jest polityką niższego rzędu wykonywania jakichkolwiek zadan. Używamy metody z 
 [Alice i Benem](#intrinsic-motivation) gdzie Alice zadaje Benowi coraz trudniejsze rozwiązywalne zadania z pewnymi różnicami, 
 nagrody to 0/1, czas wykonania zadań nie jest dynamiczny tylko ustawiony na stały, dodatkowo aby powiększyć eksploracje czas wykonania
  podzielony jest na parę segmentów (nie resetujemy po każdym tasku do stanu początkowego) tak aby Charlie miał łatwiej 
 - Uczenie Charliego :  Przepuszczamy stan przez politykę Charliego która tworzy embedduje zadanie, potem przepuszczamy przez politykę Bena w 
 stanach z różnych timelineów

### Emergent Complexity and Zero-shot Transfer via Unsupervised Environment Design. Dennis et al. 2020

Wprowadzenie PAIRED opartego na UPOMDP (underspecified partially observable MDP) pozwalającym na definiowanie problemów które mogą mieć wiele róznych 
zbiorów stanów. Podejście wykorzystuje trzech agentów adwersarza, protagonistę i antagonistę. Adwersarz generuje środowisko używając minmax regret gdzie
gdzie liczenie regretu jest przybliżone przez różnice nagród zdobytych przez antagonisty i protagonisty w jakimś środowisku. Potem w tym wygeneronanym
środowisku wykonujemy akcje przez protagonistę i antagoniste. Na koniec poprawiamy protagonistę używając $r = -REGRET$ i antagoniste i adwersarza używając 
$r = REGRET$\

### ASYMMETRIC SELF - PLAY FOR AUTOMATIC GOAL DISCOVERY IN ROBOTIC MANIPULATION, OpenAI 2021

Dodanie do konceptów z prac Sukhbattara [2017](#intrinsic-motivation) [2018](#learning-goal-embeddings) klonowania behawioralnego. Klonowanie behawioralne jest wykonywane w momencie w którym Benowi nie uda się wykonać zadania zadanego przez Alice (Alice może dojść do celu tylko przypadkiem zatem jeśli Bob nie jest zdecydowanie gorszy to uczenie go z wykorzystaniem Alice nie ma sensu). Dodatkowo loss związany z klonowaniem behawioralnym jest clipowany w stylu PPO ponieważ duże odległości od Alice wpływały na niestabilność w uczeniu

### [Replay-Guided Adversarial Environment Design](https://arxiv.org/pdf/2110.02439.pdf), Jiang et al. 2021

Rozwinięcie konceptu PAIRED o PLR używanego również w MAESTRO

### [Evolving Curricula with Regret-Based Environment Design](https://arxiv.org/pdf/2203.01302.pdf), Holder et al. 2022

Prioritized level replay z dodaniem mutowania starych środowisk od dużym regret

### [EUREKA: HUMAN-LEVEL REWARD DESIGN VIA CODING LARGE LANGUAGE MODELS](https://arxiv.org/pdf/2310.12931.pdf)

Używanie LLMów do generowania struktury nagród. Podajemy kod środowiska i opis zadania do LLMa. LLm proponuje funkcje nagrody sprawdzana jest w środowisku, potem sprawdzane jest jak dobra ta nagroda została dobrana i znów wrzucane jest wszystko do llma

### [STABILIZING UNSUPERVISED ENVIRONMENT DESIGN WITH A LEARNED ADVERSARY](https://arxiv.org/pdf/2308.10797)
Łatwe upgrade'y do PAIRED, może do czegoś innego da się to wykorzystać, behavioural cloning z KL regularyzacją, Paired połączone trochę z accel i dodanie jakiegoś współczynnika entropii do PAIRED (To już zaimplementowane w minimaxie)

## Może interesujące Do wczytania się jeszcze

### https://proceedings.neurips.cc/paper_files/paper/2022/file/f649556471416b35e60ae0de7c1e3619-Paper-Conference.pdf

Może da się wykorzystać tą metodę do generowania środowisk, ale to do głębszego wczytania się

### [CLUTR: Curriculum Learning via Unsupervised Task Representation Learning](https://arxiv.org/pdf/2210.10243.pdf), Azad et al. 2022

### [Japońskie alternatyne liczenie regretu w Paired](https://www.jstage.jst.go.jp/article/pjsai/JSAI2023/0/JSAI2023_3E1GS201/_pdf)

### FEASIBLE ADVERSARIAL ROBUST REINFORCEMENT LEARNING FOR UNDERSPECIFIED ENVIRONMENT https://arxiv.org/pdf/2207.09597.pdf


### Proximal Curriculum for Reinforcement Learning Agents https://arxiv.org/pdf/2304.12877.pdf

Wydaje się że to jakaś inna ściezka ale trzebaby się wczytać, wygląda na dziwne porównania wydajności, bardzo dużo prac w related work, można na podstawie tego rozwijać research


### Paired Open-Ended Trailblazer (POET): Endlessly Generating Increasingly Complex and Diverse Learning Environments and Their Solutions https://arxiv.org/abs/1901.01753.pdf

### [Refining Minimax Regret for Unsupervised Environment Design](https://arxiv.org/pdf/2402.12284)


### To read
https://arxiv.org/pdf/2003.04664.pdf\
https://arxiv.org/pdf/2010.13166.pdf\
https://arxiv.org/pdf/2306.08647.pdf\
https://arxiv.org/pdf/2312.03126.pdf\
https://sites.google.com/view/ucb-drac\
https://arxiv.org/pdf/2207.05219.pdf\
https://arxiv.org/pdf/2303.06689.pdf\
https://arxiv.org/pdf/2201.08896.pdf

# Multiagent RL

## MAESTRO: OPEN-ENDED ENVIRONMENT DESIGN FOR MULTI-AGENT REINFORCEMENT LEARNING, Samvelyan et al. 2023

Praca wprowadza wzięcie pod uwagę środowiska z większa niż 1 ilością agentów, z tego powodu zaproponowany jest formalizm UPOSG (Underspcified Partially Observable Stochastic Game). Dodatkowo używany jest prioritized learning buffer (PLR) który trzyma bufor środowisk o największym potencjale na uczenie. Ostatnim wykorzystywanym mechanizmem jest Prioritized fictius self-play (PFSP) który dobiera przeciwnika dla agenta z prawdopodobieństwem względnym od wartości $f(A beats C)$ gdzie A to nasz gracz którego uczymy a C to kandydat.\
Algorytm iteruje się po epizodach. W każdym epizodzie wybieramy drugiego gracza i wybieramy czy chcemy użyć środowiska z bufora czy losowo wygenerowanego.
Jesli wybraliśmy bufor ze środowiska to po symulacji naprawiamy naszego gracza. W obu przypadkach na koniec liczymy regret danego środowiska i drugiego gracza a potem na podstawie tego aktualizujemy bufor. Co parę epizodów 

### To Read

https://arxiv.org/pdf/2202.10608.pdf


# Kontrukcje LLM-owe

### To Read
tree of thoughts: https://openreview.net/attachment?id=5Xc1ecxO1h&name=pdf\
graph of thoughts: https://arxiv.org/pdf/2308.09687.pdf

# Inne

### To read
https://arxiv.org/pdf/2306.09205v2