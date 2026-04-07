# https://github.com/cursodsousa/curso-spring-boot-especialista/tree/168fa48d8559630de60f505b8899f418081d7857

# ** Check port: **
## netstat -aof | findstr 5432

# ** Create Network [Primeiro cria a network e depois as imagens para ligar à rede] **
## sudo docker network create library-network

# ** Rodar container Postgres na versão 16.3 **
## sudo docker run --name librarydb -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres -e POSTGRES_DB=library -p 5432:5432 -d --network library-network postgres:16.3

# ** Rodar Pgadmin 4 **
## sudo docker run --name pgadmin4 -e PGADMIN_DEFAULT_EMAIL=admin@admin.com -e PGADMIN_DEFAULT_PASSWORD=admin -p 15432:80 -d --network library-network dpage/pgadmin4:8.9

# ** Configurações de acesso do client/pgadmin4 **
## name: librarydb
## host name: librarydb
## port (Usar a interna do container): 5432
## database: library
## Username: postgres
## Password: postgres

# ** Parando um container **
## sudo docker stop NOME ou ID
## sudo docker stop pgadmin4
## sudo docker stop librarydb

# ** Iniciando um container **
## sudo docker start NOME ou ID
## sudo docker start pgadmin4
## sudo docker start librarydb

# ** Removendo um container **
## sudo docker container rm NOME ou ID
## sudo docker container rm pgadmin4
## sudo docker container rm librarydb