port: 5432
volume: /var/lib/postgresql/data

docker run --rm -it -e POSTGRES_PASSWORD=postgres -d postgres:16.2

docker volume ls 
shows local volume that stores all files of the container

docker inspect 7594a01061af
shows sth like `mounts` that informs us about volume that is mapped with local containers file system 

docker-compose up -d
ls -la

docker-compose exec db psql -U postgres
w serwisie db uruchamiamy komende psql

select 1;
create table test (id int);
insert into test values (1), (2), (3);

--
utworzymy sobie docker-compose dev yml
umiescimy tam nowy serwis za pomoca ktorego bedizemy mogli jedna komenda wejsc na linie polecen
juz nie przekazujc minus U itd

docker-compose -f docker-compose.yml -f docker-compose-dev.yml run cli
za pomoca tej komendy kazda osoba bedize w stanie wejsc do tej loalnej instancji postgresql
za pomoca interaktywnego shell postgres do wykonywania zapyan na bazie

docker-compose -f docker-compose.yml -f docker-compose-dev.yml run dump
za pomoca tej komendy otrzymamy zawartosc bazy danych 
?? ale co dalej z tym dumpem?

adminer
docker-compose -f docker-compose.yml -f docker-compose-dev.yml up -d adminer
uruchamiamy w tle w trybie demona serwis adminer 

curl ifconfig.co
185.241.199.196
