## Pipeline, Jenkins, izolacja etapów

### Przygotowanie
* Upewnij się, że na pewno działają kontenery budujące i testujące, stworzone na poprzednich zajęciach
* Zapoznaj się z instrukcją instalacji Jenkinsa: https://www.jenkins.io/doc/book/installing/docker/
  * Uruchom obraz Dockera który eksponuje środowisko zagnieżdżone
    ![](./ss/jenkins1.1.png)
  * Przygotuj obraz blueocean na podstawie obrazu Jenkinsa (czym się różnią?)
    Obraz stworzony wg poniższego Dockerfile uzupełnia środowisko Jenkinsa o pluginy Blueocean i Docker
    ```
    FROM jenkins/jenkins:2.375.2
    USER root
    RUN apt-get update && apt-get install -y lsb-release
    RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
    https://download.docker.com/linux/debian/gpg
    RUN echo "deb [arch=$(dpkg --print-architecture) \
    signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
    https://download.docker.com/linux/debian \
    $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
    RUN apt-get update && apt-get install -y docker-ce-cli
    USER jenkins
    RUN jenkins-plugin-cli --plugins "blueocean docker-workflow"
    ``` Workflow
    ![](./ss/jenkins1.2.png)\
    ![](./ss/jenkins1.3.png)
  * Uruchom Blueocean
    ![](./ss/jenkins1.4.png)\
    ![](./ss/jenkins1.5.png)\
    ![](./ss/jenkins1.6.png)
  * Zaloguj się i skonfiguruj Jenkins
    ![](./ss/jenkins1.7.png)\
    ![](./ss/jenkins1.8.png) \
    Do instalacji dodane zostały pluginy dashboard view i configuration as code.\
    ![](./ss/jenkins1.9.png)\
    ![](./ss/jenkins1.10.png)
  * Zadbaj o archiwizację i zabezpieczenie logów
  
### Uruchomienie 
* Konfiguracja wstępna i pierwsze uruchomienie
  * Utwórz projekt, który wyświetla uname
    ![](./ss/jenkins2.1.png)\
    ![](./ss/jenkins2.2.png)\
    ![](./ss/jenkins2.3.png)\
    ![](./ss/jenkins2.4.png)\
    ![](./ss/jenkins2.5.png)
  * Utwórz projekt, który zwraca błąd, gdy... godzina jest nieparzysta
    ![](./ss/jenkins2.6.png)\
    ![](./ss/jenkins2.7.png)\
    ![](./ss/jenkins2.8.png)
* Utwórz "prawdziwy" projekt, który:
  * klonuje nasze repozytorium
  * przechodzi na osobistą gałąź
  * buduje obrazy z dockerfiles i/lub komponuje via docker-compose
  
### Pipeline
* Definiuj pipeline korzystający z kontenerów celem realizacji kroków `build -> test`
* Może, ale nie musi, budować się na dedykowanym DIND, ale może się to dziać od razu na kontenerze CI. Należy udokumentować funkcjonalną różnicę między niniejszymi podejściami
* Docelowo, Jenkinsfile definiujący pipeline powinien być umieszczony w repozytorium. Optymalnie: w sforkowanym repozytorium wybranego oprogramowania
![](./ss/jenkins3.1.png)\
![](./ss/jenkins3.2.png)\
![](./ss/jenkins3.3.png)\
![](./ss/jenkins3.4.png)
