FROM ubuntu:22.04

# Ustawiamy strefę czasową, inaczej niektóre komendy mogą działać niepoprawnie
RUN echo "Europe/Warsaw" > /etc/timezone && ln -fns /usr/share/zoneinfo/Europe/Warsaw /etc/localtime

# Aktualizacja repozytorium i pakietów
RUN export DEBIAN_FRONTEND=noninteractive && apt-get update && apt-get upgrade -y

# ???
RUN export DEBIAN_FRONTEND=noninteractive && apt-get install -y --no-install-recommends apt-utils && apt-get install -y --no-install-recommends tzdata curl

# Instalujemy git, GCC i make
RUN export DEBIAN_FRONTEND=noninteractive && apt-get install -y git build-essential

WORKDIR /root

# Klonujemy repozytorium projektu
RUN git clone https://github.com/derf/feh

WORKDIR /root/feh

# Instalujemy zależności
RUN export DEBIAN_FRONTEND=noninteractive && apt-get install -y libc6 libcurl4 libexif12 libimlib2 libpng16-16 libx11-6 libxinerama1 yudit-common libjpeg-progs libx11-dev libxt-dev libimlib2-dev libxinerama-dev debhelper-compat perl libtest-command-perl libcurl4-openssl-dev libexif-dev

# Budujemy program
RUN make

WORKDIR /
