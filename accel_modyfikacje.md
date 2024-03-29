## LLM generujące funkcję mutującą

Co pewien czas LLM generuje funkcje mutującą poziom

## Dodanie Eureki

Generowanie funkcji nagród w zależności od postępów w treningu

## Utrzymywanie bufora anty forgettingowego

Trzymanie bufora starych nie modyfikowanych poziomów wrzucanych do batcha z założeniem przeciwdziałania zapominaniu

## Drugi teacher anty forgettingowy 

Wrzucanie do batcha połowy poziomów od standardowego teachera i połowy wygenerowanych przez drugiego teachera który daje łatwiejsze taski.

## Ulepszenia generatora poziomów

LLM generujący generator co jakiś czas ¯\\_(ツ)_/¯ / może w jakiś sposób da się nauczyć jakiś model tak aby był w stanie sparametryzować generator i potem z czasem generować poziomy z interesującymi nas parametrami (wtedy możemy za to wpaść na [CICS](https://arxiv.org/abs/2207.05219) ale da się to jakoś naprawić)

## Ciekawe Funkcje mutujące

### Merging poziomów

Próba połączenia cech dwóch różnych poziomów tak aby starać zachować się cechy obydwu poziomów

### Proste przekształcenia nie wpływające na rozwiązanie

Np obroty, przesunięcia itp, założenie jest takie aby ustabilnić agenta wiedząc że radzi sobie w pewnych warunkach to żeby nie gubił się przy nieznaczących zmianach

### Trackowanie mutacji

Z ekperymentów minqiego wynika że zero-shot performance spada gdy robimy mutacje maksymalizujące lossa, może można spróbować użyć do tego jakiś bandytów, lub maksymalizować ten loss w jakiś określonych przypadkach


### Mierzenie trudności

To może być bardzo trudne do uzyskania, ale możemy próbować nauczyć jakiś model w określaniu trudności zadań i potem generować poziomy tak aby w miarę pokrywały się z celem (to trochę da się połączyć z LLMami i Eureką, tylko tym więcej dodajemy to tym większy syf)

## Alternatywne lossy

### Rainbow style

Kręcenie się pomiędzy różnymi lossami

### Różne inne kombinacje/nowe lossy jeszcze będe myślał...
