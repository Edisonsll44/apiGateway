cd /mnt
ls
cd c 
ls
cd Users
cd esanchez
lscd Desktop
lstouch archivo txt
nano archivo.txt
	ctrl+x
	Enter
----validar version wsl

wsl --list --verbose

 ---- Instalar entorno grafico como escritorio remoto --------
 sudo apt-get purge xrdp
 sudo apt install -y xrdp
 sudo apt install -y xfce4
 sudo apt install -y xfce4-goodies
 sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
 sudo sed -i 's/ 3389/3390 / g' /etc/xrdp/xrdp.ini
 sudo sed -i 's/ max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
 sudo sed -i 's/ xserverbpp=24/#xserverbpp=242\nxserverbpp=1288/g' /etc/xrdp/xrdp.ini
 echo xfce4-session> ~/.xsession
 sudo nano /etc/xrdp/startwm.sh
	Ctrl + x
	Press Y => Enter
 sudo /etc/init.d/xrdp start
	user: esanchez
	clave: AmadoDios87*

----ejecutar docker
docker ps
mkdir prueba
cd prueba
touch Dockerfile
nano Dockerfile
	ctrl + x
docker build . -t prueba
docker run prueba

-------compilar net core
dotnet restore
dotnet publish -c Release -o out
docker build -t dotnetcoreapp .


-------Instalar linux mysql
sudo apt update
sudo apt install mysql-server
mysql --version
sudo service mysql start
sudo service mysql status
--sudo mysql_secure_installation
sudo mysql
show databases;
--sudo service mysql stop

--create database CRUDNODEJS;
USE CRUDNODEJS
 show tables;
 RENAME TABLE CRUDNODEJS.productos to CRUDNODEJS.Products;
 CREATE TABLE productos (productId int NOT NULL, 
						 productName varchar(255) NOT NULL, 
						 quantity int NOT NULL, 
						 price decimal(5,2),
						 PRIMARY KEY(productId));
  show tables;
 mysqladmin -u root -p status
 ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'insert_password';
 mysql -u root -p
 
 
 
 ----NodeJs
 npm init -y
 npm i nodemon eslint eslint-config-prettier eslint-plugin-prettier pritter -D
 npm i express
 npm i cors
  -- data fake => npm i faker
 -- errores => npm i @hapi/boom
 -- validar esquemas => npm i joi
npm install pg
npm i dotenv
   ---ORM
    npm install --save sequelize
	npm install --save pg-hstore

 pkill -f node
 
--- Git

sudo apt-get install git
git config --global user.name
git config --global user.email

git init
git remote add origin https://github.com/username/Project.git
git push origin master


--docker--
docker-compose up -d "nombre_contenedor"
docker ps -a 		=> lista los contenedores 
docker-compose down
 docker-compose exec postgres bash
 docker ps
 docker inspect => Id = 90523982f481
 
 ---entrar a Postgress
 docker-compose exec postgres bash
psql -h localhost -d my_store -U nico
\d+
  
CREATE TABLE task (
	id serial PRIMARY KEY,
	title VARCHAR ( 250 ) NOT NULL,
	completed boolean DEFAULT false
);



---RPA
https://cloud.uipath.com