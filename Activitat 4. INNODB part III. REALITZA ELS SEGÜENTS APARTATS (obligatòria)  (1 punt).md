### Activitat 4. INNODB part III. REALITZA ELS SEGÜENTS APARTATS (obligatòria)  (1 punt)

### •	Crea un tablespace anomenat 'ts1' situat a /discs-mysql/disc1/ i col•loca les taules actor, address i category de la BD Sakila.
### Primer entrarem el mysql amb l’usuari root i crearé el tablespace amb el nom ts1 i que es guardi a aquesta ubicació:

![image](https://user-images.githubusercontent.com/99834779/161995579-b048682a-d5ed-4a67-b15f-54f5b3b647da.png)

### Després farem aquesta comanda per poder col•locar les taules de la base de dades sakila:

![image](https://user-images.githubusercontent.com/99834779/161995602-c6b7d14d-75cd-44d5-a916-62e7ba8a2fa8.png)

### I per les taules que diu aquest apartat les posarem el tablespace ts1:
 
![image](https://user-images.githubusercontent.com/99834779/161995616-5cea1e55-fa47-4aca-8e47-3ed71f1be3c6.png)

### •	Crea un altre tablespace anomenat 'ts2' situat a /discs-mysql/disc2/ i col•loca-hi la resta de taules.
### Igual que en l’apartat anterior primer crearem el tablespace i el posarem en aquesta ubicació:
 
![image](https://user-images.githubusercontent.com/99834779/161995627-6ac8432b-5938-4259-8318-5796e7dffb82.png)

### I entrarem a la base de dades sakila i posarem les taules que ens diu l’apartat el tablespace ts2:
 
![image](https://user-images.githubusercontent.com/99834779/161995647-e9a65891-11bd-435d-a02a-3e80dd39e398.png)

![image](https://user-images.githubusercontent.com/99834779/161995664-fabb5177-7b8b-4f3c-b53f-726610e3b933.png)
 
### Per veure que els dos tablespace estan a la ruta indicada he fet aquesta consulta:

![image](https://user-images.githubusercontent.com/99834779/161995731-759d18b7-d996-4160-bcf6-d41e77179620.png)

### •	Comprova que pots realitzar operacions DML a les taules dels dos tablespaces.
### Inserit els camps a la taula actor que està el tablespaces ts1:

![image](https://user-images.githubusercontent.com/99834779/161995779-7e59bc7e-c47e-47c3-b898-78526d7833f2.png)

### Ara mirem si estan les dades i en el meu cas he utilitzat el programa Workbench:

![image](https://user-images.githubusercontent.com/99834779/161995794-a762200a-6717-405b-bcbd-1ed9433492cf.png)

### Afegeixo els  camps a la taula film_text que està el tablespaces ts2:

![image](https://user-images.githubusercontent.com/99834779/161995816-e6ced93b-b0b7-45cc-89fa-cf46630d412b.png)

### Ara mirem les dades i he utilitzat el programa Workbench:
 
![image](https://user-images.githubusercontent.com/99834779/161995844-1973504c-4cb0-4320-bc08-81474a917238.png)

### •	Quines comandes i configuracions has realitzat per fer els dos apartats anteriors?
### He utilitzat aquestes comandes:
### CREATE TABLESPACE -> per crear els tablespaces.
### ALTER TABLE -> per canviar a la taula el seu tablespaces.
### També he modificat el fitxer de configuració amb el nom my.cnf i ha quedat d’aquesta manera, després de posar aquesta configuració fet les comandes de canviar  de directori, aturar i iniciar el servei mysql:
 
![image](https://user-images.githubusercontent.com/99834779/161995886-1c347ba1-c286-4d70-97aa-b3ad9c838c73.png)

### Checkpoint: Mostra al professor els canvis realitzats i que la BD continua funcionant
