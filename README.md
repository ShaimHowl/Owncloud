# Instal·lació i configuració de aplicacions web
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
