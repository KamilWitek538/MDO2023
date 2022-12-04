Sprawozdanie Zajęcia lab 01
2022-11-26
Szymon Michoń 404665

Setup:
Komputer lokalny: MacOS
Serwer zdalny: Ubuntu 22.04, natywny, w tej samej sieci lokalnej
Sposób połączenia: Terminal (ZSH)

NIEKTÓRE SCREENSHOTY SĄ POUCINANE W CELU ZASŁONIENIA DANYCH PRYWATNYCH JAK NP. WARTOŚCI KLUCZY

Weryfikacja sprawności środowiska UNIX
1.	Wykaż możliwość komunikacji ze środowiskiem linuksowym
SSH:
 ![image description](images/lab1_zdj1.png)
SFTP:
 ![image description](images/lab1_zdj2.png)

2.	Zainstaluj klienta Git

 ![image description](images/lab1_zdj3.png)


3.	Sklonuj repozytorium za pomocą HTTPS
![image description](images/lab1_zdj4.png)
 
4.	Stworzenie kluczy innych niż RSA (definiowane za pomocą -t), zabezpieczone hasłami, dodane do GitHuba, sklonowanie za pomocą ssh
 ![image description](images/lab1_zdj5.png)
 ![image description](images/lab1_zdj6.png)
 ![image description](images/lab1_zdj7.png) 
 

5.	Przyłączyłem się do swojej grupy, stworzyłem gałąż SM404665
 ![image description](images/lab1_zdj8.png)
 ![image description](images/lab1_zdj9.png)
 
6.	Utworzyłem katalog SM404665 w którym umieszczę te sprawozdanie
 ![image description](images/lab1_zdj10.png)
7. Dodaje zdjęcie commita i dodaje kolejnego commita jak w instrukcji
 ![image description](images/lab1_zdj13.png)
 
 Dodałem hooki

![image description](images/hooks.png)

Weryfikacja działania środowiska konteneryzacji
1.	Mam dostęp po SSH, jak wykazałem powyżej jest to serwer z zainstalowanym natywnie ubuntu w tej samej sieci lokalnej do którego łączę się terminalem, zainstalowałem na nim dockera
 ![image description](images/lab1_zdj11.png)

2.	Środowiska dockerowe działa, pobrałem obraz fedora w wersji latest
 ![image description](images/lab1_zdj12.png)

3.	Zalogowałem się do posiadanego konta na Docker Hub link do profilu https://hub.docker.com/u/michonszy

