## Różnica w rewardach

Zamiast brania pod uwagę regretu to jeśli samplowane jest środowisko z bufora wybieramy z prawdopodobieństwem proporcjonalnym do jakiejś funkcji zależnej od różnicy w rewardach w danym środowisku

## Estymowanie możliwego potencjału postępów agenta 

Próbujemy estymować jaki potencjał nauki ma agent i dobieramy drugiego gracza tak aby jak najbardziej wykorzystać potencjał ale nie przekraczać go zbytnio.

## Wybieranie środowkiski o największej różnorodności nagród

Wybieramy takie środowiska aby agenci w buforze mieli jak najbardziej zróżnicowane bufory (gdzie patrzymy na zróżnicowanie w całej grupie bufora)

## LLM + Accel

Generowanie początkowych poziomów przez llmy na podstawie wyników wybranych przez llm poziomów, potem ileś rund accela aż do momentu w którym potrzebny jest nowy poziom

## Eureka + Accel

Accel z dodaniem generowania nagród przez llmy

## Generowanie Funkcji Mutacji

Co jakiś czas pozwalamy llmowi wygenerować funkcję(lub zbiór funkcji ) generującą mutacje poziomów 
