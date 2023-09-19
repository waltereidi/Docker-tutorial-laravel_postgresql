<h1> Tutorial Docker windows para Laravel com PostgreSQL </h1>
<strong>utilize o visual studio code e seu terminal para rodar os comandos</strong></br>
<p>Copie apenas o dockerfile e docker-compose.yml deste repositorio </br> 
rode no terminal o comando <strong>docker-compose build</p>strong> </br>
em seguida <strong>docker-compose up</strong></br>
verifique se no seu docker o container foi criado e está rodando com os 2 serviços.</br>
agora entre no terminal de comandos da maquina virtual com o comando </br>
<strong>docker exec -it laravel-docker-postgresql</strong> o nome após o -it é o container_name do arquivo yml</br>
crie um projeto laravel novo <strong>composer create laravel/laravel nomedoprojeto</strong>  </br>
com seu projeto criado digite o comando <strong>ls</strong>strong> e valide se foi criado a pasta com o nome do seu projeto.</br>
entre nesta pasta <strong>cd nomedoprojeto</strong> </br>
rode o comando <strong>php artisan migrate</strong></br>
oque pode dar errado no migrate ? </br>
<h4>acessando o postgres por terminal de comando do docker:</h4>
1 : Arquivo env do laravel mal configurado : veja este exemplo </br>
<img src="https://github.com/waltereidi/Docker-tutorial-laravel_postgresql/assets/6370415/778dc1e8-fcc7-4859-9730-cf71384eac7f"></br>
note que o DB_HOST possui o mesmo nome do arquivo de configuração </br>
<img src="https://github.com/waltereidi/Docker-tutorial-laravel_postgresql/assets/6370415/aad334f0-86b4-428f-baf7-c45c3e24ddae"></br>
valide também as configurações de usuario e senha.</br>
2: Pode ser que o banco de dados descrito no arquivo .yml não tenha sido criado, neste caso você pode </br>
optar por logar no banco criado do postgres em seu terminal com a porta configurada "5499" ou acessar o terminal do postgresql </br>
com o comando <strong>docker exec -it laravel-docker-postgresql-pgsql-1 bash</strong> (lembre-se que o nome descrito é o da configuração e mais o número gerado pelo docker.</br>
você pode encontralo em sua interface grafica : </br>
<img src="https://github.com/waltereidi/Docker-tutorial-laravel_postgresql/assets/6370415/e2871b55-6e29-4e7a-b1ca-2741028a61e2"></br>

em seguida rode o comando para criar um banco de dados manualmente : 
psql -U postgres -c "create database nomedobanco";

<hr>
</br>
Após a migrations ser bem sucedida rode o <strong>php artisan serve --host 0.0.0.0</strong> e acesse seu site no localhost:8000 


