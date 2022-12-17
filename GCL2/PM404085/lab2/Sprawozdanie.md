# Sprawozdanie Zajęcia 02

### Zestawienie środowiska

1) Zainstaluj Docker w systemie linuksowym

Docker został zainstalowany na potrzeby poprzedniego laboratorium: 

![](../img/16.png)

2) Zarejestruj się w Docker Hub i zapoznaj z sugerowanymi obrazami

Link do profilu: https://hub.docker.com/u/patrykmurzyn

3) Pobierz hello-world, busybox, ubuntu lub fedorę, mysql

Instalujemy wymienione obrazy za pomocą polecenia docker pull <nazwa>

![](./img/0.png)

4) Uruchom busybox

* Pokaż efekt uruchomienia kontenera
* Podłącz się do kontenera interaktywnie i wywołaj numer wersji
	
![](./img/1.png)
	
5) Uruchom "system w kontenerze"

Uruchomiłem system Fedora oraz zainstalowałem pakiet procps z którego skorzystam w kolejnym podpunkcie.

![](./img/2.png)

* Zaprezentuj PID1 w kontenerze i procesy dockera na hoście
	
![](./img/3.png)
	
* Zaktualizuj pakiety
	
Zaktualizowałem pakiety korzystając z polecenia:
```
dnf upgrade
```
	
![](./img/4.png)
	
* Wyjdź
	
![](./img/5.png)
	
6) Pokaż uruchomione ( != "działające" ) kontenery

Pokazanie uruchomionych kontenerów:

![](./img/6.png)

7) Wyczyść obrazy

![](./img/7.png)

### Budowanie programu

1) Znajdź projekt umożliwiający łatwe wywołanie testów jednostkowych

Znalazłem projekt napisany w JS z prostym opisem funkcjonalności: https://github.com/MarcL/js-unit-testing-examples

2) Przeprowadź budowę/konfigurację środowiska

Postępując zgodnie z instrukcją projektu wykonujemy kolejno:
```
git clone git@github.com:MarcL/js-unit-testing-framework.git
npm install
```

Podczas installacji zależności npm napotkałem problem:

![](./img/8.png)

Który został naprawiony poprzez wywołania polecenia:

```
npm install --save --legacy-peer-deps
```

![](./img/9.png)

3) Uruchom testy

Uruchomiłem testy poprzez wywołanie:
```
npm test
```

![](./img/10.png)

4) Ponów ten proces w kontenerze

* Wybierz i uruchom platformę

![](./img/12.png)

* Zaopatrz ją w odpowiednie oprogramowanie wstępne

```
sudo dnf install nodejs
sudo dnf install git
```

![](./img/11.png)

* Sklonuj aplikację

```
git clone https://github.com/MarcL/js-unit-testing-examples.git
```

![](./img/13.png)

* Skonfiguruj środowisko i uruchom build

![](./img/14.png)

* Uruchom testy

![](./img/15.png)

5) Stwórz Dockerfile, który ma to osiągnąć

* Na bazie platformowego obrazu...
* ...doinstaluj wymagania wstępne...
* ...sklonuj repozytorium...
* ...zbuduj kod

6) Zaprezentuj Dockerfile i jego zbudowanie

```
FROM fedora 

RUN dnf upgrade -y
RUN dnf install git -y
RUN dnf install nodejs -y


RUN git clone https://github.com/MarcL/js-unit-testing-examples.git
WORKDIR js-unit-testing-examples
RUN npm install --save --legacy-peer-deps
```

![](./img/17.png)

7) Na bazie obrazu utworzonego poprzednim dockerfilem stwórz kolejny, który będzie uruchamiał testy

* Kontener pierwszy ma przeprowadzać wszystkie kroki aż do builda

* Kontener drugi ma bazować na pierwszym i wykonywać testy

Testy wywołamy poprzez dodanie do Dockerfile:

```
RUN npm test
```

![](./img/18.png)
