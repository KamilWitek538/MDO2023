# Sprawozdanie 1 - Wprowadzenie, Git, Gałęzie, SSH

### Weryfikacja sprawności środowiska UNIX

1) Wykaż możliwość komunikacji ze środowiskiem linuksowym (powłoka oraz przesyłanie plików)

Zdecydowałem się na wykorzystanie WSL2 oraz dystrybucji Ubuntu do wykonania laboratorium. Połączyłem się z WSLem za pomocą ssh oraz sftp.

![](./img/0.png)

![](./img/1.png)

![](./img/2.png)

2) Zainstaluj klienta Git i obsługę kluczy SSH

![](./img/3.png)

3) Sklonuj repozytorium https://github.com/InzynieriaOprogramowaniaAGH/MDO2023 za pomocą HTTPS

![](./img/4.png)

4) Upewnij się w kwestii dostępu do repozytorium jako uczestnik i sklonuj je za pomocą utworzonego klucza SSH

    * Utwórz dwa klucze SSH, inne niż RSA, w tym co najmniej jeden zabezpieczony hasłem
	
	![](./img/5.png)
	
    * Skonfiguruj klucz SSH jako metodę dostępu
	
	![](./img/6.png)
	
    * Sklonuj repozytorium z wykorzystaniem protokołu SSH
	
	![](./img/7.png)
    
5) Przełącz się na gałąź swojej grupy
6) Utwórz gałąź o nazwie "inicjały & nr indeksu" np. KD232144

![](./img/8.png)

7) Rozpocznij pracę na nowej gałęzi
    * W katalogu właściwym dla grupy utwórz nowy katalog, także o nazwie "inicjały & nr indeksu" np. KD232144
    * W nowym katalogu dodaj plik ze sprawozdaniem
	
	![](./img/9.png)
	
    * Dodaj zrzuty ekranu
	
	![](./img/10.png)
	
    * Wyślij zmiany do zdalnego źródła
	
	![](./img/11.png)
	
	* Spróbuj wciągnąć swoją gałąź do gałęzi grupowej
	
	* Zaktualizuj sprawozdanie i zrzuty o ten krok i wyślij aktualizację do zdalnego źródła (na swojej gałęzi)

	![](./img/12.png)