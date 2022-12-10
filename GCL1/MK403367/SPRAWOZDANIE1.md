# Sprawozdanie 1
Michał Kutaj
403367

Wykorzystany został natywny system Ubuntu 22, do którego łączę się z sieci lokalnej z macbooka zwanego dalej - "jabuszkiem"



1. Instalacja serwera ssh na serwerze oraz konfiguracja zapory
```
sudo apt update
sudo apt install ssh-server
sudo afw allow ssh
sudo systemctl status ssh
```
![image description](01-status-serwera-ssh.png)

Serwerowi został przdzielony adres w sieci lokalnej, mozna go zweryfikować przy pomocy polecenia:
```
ip a
```
![image description](02-adres-serwera.png)

Test połączenia z komputera znajdującego się w sieci lokalnej
![image description](polaczenie-przez-ssh.png)

Test przesyłania plików. Na serwerze w katalogu domowym znajduje się plik `test.txt` zostanie on pobrany przy pomocy komendy:
```
scp maikel@10.0.1.240:~/test.txt ./test.txt
```
![image description](transfer-plikow.png)

2. Polecenia `git` oraz `ssh-keygen` są dostępne w systemie
![image description](git-ssh-keygen.png)

Repo przedmiotu zostało sklonowane przez https
```
git clone https://github.com/InzynieriaOprogramowaniaAGH/MDO2023
```
![image description](clone-https.png)

Zostały utworzone dwa klucze ssh, wykorzystano algortym `ecdsa`
```
ssh-keygen -t ecdsa
```
![image description](klucze-ssh.png)

Przy próbie pobrania repozytorium przedmiotu przez ssh widać brak uprawnień
![image description](clone-ssh-brak-per.png)

Dodano klucz do agenta oraz do konta GitHub
```
ssh-add ~/.ssh/devops_no_pass
```
![image description](ssh-add.png)
![image description](github-klucze.png)

Teraz mozna pobrać repo przez SSH przy uyciu polecenia
```
git clone git@github.com:InzynieriaOprogramowaniaAGH/MDO2023
```
![image description](clone-ssh.png)

Przełączenie się na branch grupy
```
git checkout -b GCL1
```
![image description](git-checkout.png)

Utworzenie nowego brancha z brancha grupowego
```
git checkout -b MK403367 GCL1
```
![image description](git-checkout-nowy-br.png)

Utworzenie katalogu w katalogu grupy i dodanie plików sprawozdania i zrzutów ekranu. Dla wygody edycji sprawozdanie było przygotowane na jabuszku więc pliki zostały przesłane na serwer przed `scp`
![image description](scp-sprawko-img.png)
Widok katalogu na serwerze po przesłaniu plików
![image description](ls-katalogu.png)
