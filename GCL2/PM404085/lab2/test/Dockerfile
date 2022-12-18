FROM fedora 

RUN dnf upgrade -y
RUN dnf install git -y
RUN dnf install nodejs -y

RUN git clone https://github.com/MarcL/js-unit-testing-examples.git
WORKDIR js-unit-testing-examples
RUN npm install --save --legacy-peer-deps
CMD ["npm", "test"]