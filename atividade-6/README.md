----------------------------------------------------------
Atividade 6 - Execução
----------------------------------------------------------

- instalar npm
sudo apt install npm

- artillery
sudo npm install -g artillery

https://artillery.io/

- escalar manualmente os backends

- Isso iniciará 10 usuários virtuais que farão 20 solicitações cada, para o URL especificado:
artillery quick -c 1000 -n 10 http://localhost:8095/events/100

- Por exemplo, o comando a seguir executará o teste durante 10s, com 2 novos usuários chegando a cada segundo, resultando em cerca de 20 solicitações no total:
artillery quick https://httpbin.org/get -r 2 -d 10

- Referencia:
https://dev.to/brpaz/load-testing-your-applications-with-artillery-4m1p