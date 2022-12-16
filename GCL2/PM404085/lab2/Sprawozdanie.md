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

