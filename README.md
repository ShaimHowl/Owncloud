## 2

![text alternatiu](12.png).
![text alternatiu](13.png).


# 3 Instal·lació i configuració de aplicacions web
Avui us ensenyare a descargar una aplicació, pero fent que funcioni amb tots els codis següents, necessitarem
codis del terminal perque funcioni l'aplicació
Primer instalarem làplicació al directori

## Instal·lació d'apache2, mysql i algunes llibreries al contenidor

1. Primer actualitzem la maquina.
```console
sudo apt update
```
![text alternatiu](1.png).
```console
sudo apt upgrade
```
![text alternatiu](2.png).

2. Segon instalem el servidor web `apache2`.
```console
sudo apt install -y apache2
```
![text alternatiu](3.png).


3. Tercer instalem la base de dates al servidor `mysql-server`.
```console
sudo apt install -y mysql-server
```
![text alternatiu](4.png).

4. Instalem les llibreries de `php`, i el llenguatge de les aplicacions.
```console
sudo apt install -y php libapache2-mod-php
```
```console
sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl
```Captura de pantalla de 2024-11-12 08-27-46.png
![text alternatiu](5.png).

5. Ara reiniciem el servidor apache2 i seguim amb les comandes en el terminal
```console
sudo systemctl restart apache2 
```
```console
sudo mysql
```
![text alternatiu](6.png).

## Configuració de MySQL
### Creació base de dates
Dins de el MySQL tens que posar aquestes comandes de creació de dates, de usuaris i sortim de la base.
```console
CREATE DATABASE bbdd;
```
```console
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
```console
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
```
```console
exit
```

![text alternatiu](7.png).

## Descarrega de fitxers de l'aplicacoó web

Anem al directori `/var/www/html` i mirem el nombre del fitxer que acaben de descarregar i substituim per `app-web.zip` per el nom del nostre fitxer que hem descarregat amb l'aplicació web. Si esta en castella dons seria Descargas no Baixades i posem usuari

```console
sudo cp ~/Baixades/app-web.zip /var/www/html
```
![text alternatiu](8.png).

Ara anem al directori `/var/www/html` i descomprimim el fitxer que hem baixat
```console
cd /var/www/html
```

![text alternatiu](9.png).


Copiem els fitxers a la carpeta `/var/www/html`, i canviem `app-web` pel el nom del nostre directori, despres eliminimen la carpeta que hem creat de l'unzip
```console
sudo cp -R app-web/. /var/www/html
```
```console
sudo rm -rf app-web/
```


![text alternatiu](10.png).

## Eliminem el nostre fitxer `index.html` de l'`apache2`
```console
sudo rm -rf /var/www/html/index.html
```

![text alternatiu](11.png).

## Aplicació de permisos a les nostres aplicacions web
Despres de comprimir els fitxers de l'aplicació de la web `/var/www/html`, apliquem altres permisos ver que funcionin`/var/www/html`

```console
cd /var/www/html
```
```console
sudo chmod -R 775 .
```
```console
sudo chown -R usuario:www-data .
```

## Ja podem veure si l'aplicació funciona
Poseu la direcció http://localhost al navegador web i configureu la cloud.

# Aqui estan les claus que es necessiten

* **usuari:** usuario
* **contrasenya:** password
* **base de dades:** bbdd
* **domini:** localhost

## 4
### Aqui he pujat un arxiu
![text alternatiu](14.png).
![text alternatiu](15.png).

### He creat una carpeta que es diu Futboleros
![text alternatiu](16.png).
### Tambe puc compartir nomes que no tinc ningun grup encara
![text alternatiu](17.png).

## 5

### He creat 3 usuaris (admin, editor y visualizador)
#### Primer he creat un grup per ficar dintre els usuaris, el primer a segut l'editor
![image](18.png)
![image](19.png)
#### En aquest cas despres de posar el email i el nom he clicat en la opció de editor
![image](20.png)
#### I aixi quedaria
![image](21.png)





