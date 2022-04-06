### Activitat 1. REALITZA I/O RESPON ELS SEGÜENTS APARTATS (obligatòria) (1 punts)

### •	Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra al comanda utilitzada i el resultat d’aquesta.
### Per veure els motors d’emmagatzematge que puc utilitzar es amb aquesta comanda i l’ he executat dintre del mysql:

![image](https://user-images.githubusercontent.com/99834779/161992219-a30f7517-04af-4206-9472-61ad45f79e96.png)

### •	Com puc saber quin és el motor d’emmagatzematge per defecte? Mostra com canviar aquest paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor MyISAM?
### Per saber el motor que està per defecte, fem aquesta comanda:

![image](https://user-images.githubusercontent.com/99834779/161992302-ae039099-2e0a-4698-b6d4-8449a0aa0559.png)

### I per canviar el motor seria entrant en aquest fitxer de configuració i afegir la línia que està subratllada:

![image](https://user-images.githubusercontent.com/99834779/161992335-dab834e4-d2ca-437e-8da4-3ee00a945aea.png)

### Després reiniciem el servei de mysql:

![image](https://user-images.githubusercontent.com/99834779/161992362-0293d910-1bf9-4292-8a67-a46c28c38a63.png)

### I ho comprovem entrant al mysql:
 
![image](https://user-images.githubusercontent.com/99834779/161992393-af4df20a-1f8b-4f54-92fb-adb3626f77f4.png)

### Ara fet una prova, he utilitzat el programa Workbench per crear una taula i la he creat d’aquesta manera:

![image](https://user-images.githubusercontent.com/99834779/161992439-e600448c-9942-496e-9c14-4a143a8decba.png)

### I després he fet aquesta consulta dintre del mysql i es veu quin motor està utilitzant:

![image](https://user-images.githubusercontent.com/99834779/161992481-04a1976a-74a1-47aa-8457-638a08f57ad0.png)

### •	Explica els passos per instal•lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor). Aquest tipus d’emmagatzematge està optimitzat per ser molt eficient en les escriptures amb lectures acceptables.
### Farem aquesta comanda per fer l’instal•lció:
 
![image](https://user-images.githubusercontent.com/99834779/161992503-574fcc08-e702-49ef-b0b3-56bd4768c703.png)

### Ara activarem el MyRocks amb aquesta comanda: 

![image](https://user-images.githubusercontent.com/99834779/161992563-ee14ad54-a918-4691-8bb5-d0c1f612e317.png)

### Ara mirarem si esta en la taula d’ engines:
 
![image](https://user-images.githubusercontent.com/99834779/161992583-726caa99-e365-499c-97a8-46820a18568e.png)

### •	Importa la BD Sakila com a taules MyISAM. Fes els canvis necessaris per importar la BD Sakila perquè totes les taules siguin de tipus MyISAM. 
### Per importar la BD Sakila haurem de crear un  fitxer i fer unes modificacions. Les modificacions són que a cada “Create Table” modificar la  part “ENGINE=InnoDB” per “ENGINE=MyISAM”, faig això perquè  encara que el motor el tinc com MyISAM hem posarà el que esta marcat en aquesta part:
### Per exemple per defecte està així el create table:
 
![image](https://user-images.githubusercontent.com/99834779/161992619-8e5eac21-007f-406a-813a-d23e8ac33d5b.png)

### I quedarà d’aquesta manera:

![image](https://user-images.githubusercontent.com/99834779/161992653-bcb9d71b-72c8-413c-b584-052bf3922a35.png)

### I totes les taules quedaran com aquestes dos:

![image](https://user-images.githubusercontent.com/99834779/161992700-291b714a-c6a4-45e6-bc4e-24fc89ba0cc5.png)

### Després de fer els canvis l’executem amb un Source a la base de dades:

![image](https://user-images.githubusercontent.com/99834779/161992737-b6bea2f1-95ff-4b2e-a901-8e5e6593acbf.png)

### Ara comprovem que s’han creat las taules amb aquest motor i en el meu cas ho comprovo amb el programa Workbench:
 
![image](https://user-images.githubusercontent.com/99834779/161992760-3571e279-4cea-4b18-a58b-17dbe30cc41d.png)

### Mira quins són els fitxers físics que ha creat, quan ocupen i quines són les seves extensions. Mostra'n una captura de pantalla i indica què conté cada fitxer.
### El fitxer físics que ha creat estan aquesta ubicació i son aquests:
 
![image](https://user-images.githubusercontent.com/99834779/161992785-943122ec-d0bc-41f1-af27-831bb5817ac8.png)
![image](https://user-images.githubusercontent.com/99834779/161992799-914dee12-3271-488b-8e19-5ea64c581ebb.png)

### En aquesta ubicació els fitxers tenen les extensions:
### .MYD:  aquest fitxer emmagatzema les dades de cada taula.
### .MYI: aquest fitxer conté els índexs de la taula.
### .TRN: són un tipus de SQL Server Transaction Log Backup File.
### .frm: és un fitxer de format de base de dades que conté informació sobre l'estructura i el format de la base de dades compatible amb una base de dades MySQL.
### .TRG: aquest fitxer conté els disparadors associats a una taula.
### Un cop fet això torna a deixar el motor InnoDB per defecte.
### Per fer això he comentat la línia de “default-storage-engine” en el fitxer de configuració amb el nom my.cnf:

![image](https://user-images.githubusercontent.com/99834779/161992835-19730969-19bb-4a73-b479-48bfce66a6b0.png)

### Després he reiniciat el servei mysql i he fet aquesta consulta:
 
![image](https://user-images.githubusercontent.com/99834779/161992861-bbe9751f-495f-42e9-9149-29b9266fbf49.png)
![image](https://user-images.githubusercontent.com/99834779/161992880-b587d1da-9a50-41c5-9975-3ae2fd54e2e1.png)

### •	A partir de MySQL apareixen els schemas de metadades i informació guardats amb InnoDB. Busca informació d'aquests schemas. Indica quin és l'objectiu de cadascun d'ells i posa'n un exemple d'ús.
### Els schemas son els següents:
### INNODB_SYS_DATAFILES: proporciona informació de ruta de fitxers de dades per a fitxers InnoDB per taula i espais de taula generals.                
### INNODB_SYS_TABLESTATS: proporciona una vista de l’ informació d'estat de baix nivell sobre les taules InnoDB que es deriva d'estructures de dades a la memòria. 
### INNODB_SYS_FOREIGN: proporciona metadades sobre claus forasteres definides a les taules InnoDB.                        
### INNODB_SYS_COLUMNS: proporciona metadades sobre les columnes de la taula InnoDB.                        
### INNODB_SYS_INDEXES: proporciona metadades sobre índexs InnoDB.                        
### INNODB_SYS_FIELDS: proporciona metadades sobre les columnes clau dels índexs InnoDB.                         
### INNODB_SYS_TABLESPACES:  proporciona metadades sobre fitxers per taula d'InnoDB i espais de taula generals.                   
### INNODB_SYS_FOREIGN_COLS: proporciona metadades sobre les columnes de claus estranyes que es defineixen a les taules InnoDB.                   
### INNODB_SYS_TABLES: proporciona metadades sobre les taules InnoDB.

### •	Posa un exemple que produeix un DEADLOCK i mostra-ho al professor.

### El DEADLOCK a MySQL passa quan dues o més transaccions es mantenen mútuament i sol•liciten bloquejos, creant un cicle de dependències. 
### En el meu cas he fet aquest exemple i es fer un login en dos terminals diferents amb dos usuaris i  en el primer terminal, que és de l’usuari root faig aquestes comandes:

![image](https://user-images.githubusercontent.com/99834779/161993126-5e3eb0c5-3aad-4fdb-98c3-46c239b81fbf.png)

### I el mateix temps en el segon terminal, que és de l’usuari asix aquestes altres i sortirà el Deadlock:
 
![image](https://user-images.githubusercontent.com/99834779/161993144-62cb7013-a791-4840-8c90-1f5bb9320ee9.png)

### Checkpoint: Mostra al professor que està instal•lat i posa un exemple de com funciona.

