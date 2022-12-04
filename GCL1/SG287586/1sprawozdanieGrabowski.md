1.	Połączenie przez SSH i SCP- ssh i scp za pomocą programu MobaXterm 

2.	Zainstalowany git, generator kluczy ssh- git version oraz sprawdzenie generując klucz

3.	Git clone HTTPS- git clone i link do strony z repozytorium

4.	2 rodzaje kluczy zabezpieczone hasłem- polecenie ssh-keygen. Klucz ecdsa i dsa 


		Skonfigurowany dostęp za pomocą klucza- w ustawieniach github
		Klonowanie przy SSH- z repozytorium z github przy odpowiedniej opcji

5.	Gałąź mojej grupy- polecenie git branch --all, git checkout GCL1, git fetch 

6.	Utworzenie mojej gałęzi- git branch SG287586

7.	Utworzenie mojego katalogu- git checkout SG287586, cd GCL1, mkdir SG287586

		Dodanie pliku ze sprawozdaniem- vi 1sprawozdanieGrabowski.md
		SS przesłane za pomocą SCP- scp
		Dodanie SS do katalogu 1SS
		Wysłanie zmian do zdalnego źródła git add ./ ; git commit -m "First step commit to remote repository- screenshots and statement" ;
			git push --set-upstream origin SG287586
		Wciągniecie mojej gałęzi do gałęzi grupowej: git checkout GCL1, git merge SG287586 
		Oznaczenie tagiem ostatni commit: git tag SGTAG HEAD, git log (do sprawdzenia), git push --tags		
		Utworzenia hooka: hook tworzę w katalogu /home/sebastian/MDO2023/.git/hooks o nazwie commit-msg, zmieniam
			uprawnienia chmod 700 commit-msg. Zawartość pliku:


					#!/bin/bash

					commitMessage=$1
					firstWord=`head -n1 $commitMessage | cut -d ' ' -f1`


					if [[ "$firstWord" =~ "devops" ]]; then
       						 echo "Prawidlowa commit message"
					else
        					echo "Niepoprawny message- pierwsze slowo powinno zawierac devops"
        				exit 1;
					fi

			Definiuję środowisko bash. Wiadomość z commit przypisuje do zmiennej commitMessage. Do zmiennej 
			firstWord przypisuję 1 wiersz i pipe pierwsza kolumna do napotkania znaku spacji- czyli pierwsze 
			słowo w commit message. W if sprawdzam czy to słowo w ~ równa się devops (nie zwraca uwagę na 
			wielkośc liter). Jeśli tak to ok, jeśli nie to wyświetlam napis i anuluję operację. 


