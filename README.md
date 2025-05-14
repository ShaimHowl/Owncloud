## 2

![text alternatiu](12.png).
![text alternatiu](13.png).


# 3 

# Instal·lació i configuració de aplicacions web
Avui us ensenyare a descargar una aplicació, pero fent que funcioni amb tots els codis següents, necessitarem
codis del terminal perque funcioni l'aplicació
Primer instalarem làplicació al director.
## Instalarem la versio 7.4 de Php a UBuntu

#### Aquest son els requisits previs de PPA
```bash
sudo apt install software-properties-common -y
```
#### Despres instalem les eines per treballar en els arxius personals
```bash
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
```
#### Ara descarregarem la llibreria de Php de la versió 7.4
```bash
sudo apt install php7.4 -y
```
```bash
sudo apt install -y php libapache2-mod-php7.4
```

```bash
sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl
```
Seleccionem la versió que en aquest cas es la 2
```bash
sudo update-alternatives --config php
```

Activem el modul d'apache:
```bash
sudo a2enmod proxy_fcgi setenvif
```
```bash
sudo a2enconf php7.4-fpm
```
I per ultim reiniciem l'apache2:
```bash
sudo service apache2 restart
```

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
#### I he fet el mateix amb el visualizador, en aquest cas es diu Roberto
![image](22.png)
![image](23.png)
#### Al final ens quedaria aixi els tres tipus
![image](24.png)
## 6
#### El admin pot controlar tot, pot compartir amb altres persones pot eliminar tots els usuaris que estiguin dintre, despres els editors no tenen permis pero tocar els altres comptes ja que allo nomes ho pot fer l'administrador, els editors el que fan es que poden tocar els PDF, els arxius, les carpetes y modificarles i per ultim els visualizador no poden fer mes que mirar tot el que hi ha, com el PDF mateix ho pott obrir i mirar, tampoc poden configurar les carpetes

## 7

#### He organitzat un carpeta que he creat que es diu "moure", que al he ficat dintre de photos
![image](25.png)
#### I aqui esta dintre
![image](26.png)
#### Configuració dels enllaços
#### He escollit el Pdf de futboleros, i com no tenia un enllaç he creat un
![image](27.png)
![image](28.png)
#### Aqui esta les dades
![image](29.png)
#### Ara si vui configurar la caducitat tinc que clicar el signe de configuració "setting"
![image](30.png)
#### I ja abaix puc canviar la caducitat
![image](31.png)

## 8





