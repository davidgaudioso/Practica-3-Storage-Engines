Activitat 2. INNODB part I. REALITZA ELS SEGÜENTS APARTATS (obligatòria)  (2 punts)

•	Desactiva l’opció que ve per defecte de innodb_file_per_table
Per fer aquest apartat en el fitxer de configuració amb el nom my.cnf he afegit la ultima línia:

![image](https://user-images.githubusercontent.com/99834779/161993485-f8ec34e2-65bc-4f24-83ce-fd2292f05556.png)

Ara reinicio el servei mysql:

![image](https://user-images.githubusercontent.com/99834779/161993511-1edfd395-a9a8-45cb-b877-48fbbc45b18e.png)

Després entro dintre del mysql amb l’usuari root i faig aquesta consulta:
 
![image](https://user-images.githubusercontent.com/99834779/161993533-253d6253-97e7-48f5-bd02-63d0de7304e4.png)

•	Importa la BD Sakila com a taules InnoDB. 
Per fer aquest apartat he generat un altre cop el fitxer de Sakila i li he deixat com està per defecte perquè en l’apartat de l’ engine ja bé escrit el InnoDB. Quant està creat el fitxer he entrat dintre del mysql com usuari root i importo la base de dades amb aquesta comanda:

![image](https://user-images.githubusercontent.com/99834779/161993584-7677ca51-a049-4366-887e-f6ac09e0837a.png)

Ara comprovem que s’han creat las taules amb aquest motor i en el meu cas ho comprovo en el programa Workbench:

![image](https://user-images.githubusercontent.com/99834779/161993613-1a8ca28f-c81c-4643-9481-659e439ae383.png)

•	Quin/quins són els fitxers de dades? A on es troben i quin és la seva mida?

Quant esta desactivat aquesta opció les dades es guarden en aquest fitxer i està en aquesta ubicació:
/var/lib/mysql/ibdata1
Però si estigues activat aquesta opció es guardarien en aquesta ubicació, però com està desactivada no surten els fitxers de les taules solament surten aquestes extensions:

![image](https://user-images.githubusercontent.com/99834779/161993834-1721e1a1-20cc-4fb0-829d-da0edb204438.png)

•	Canvia la configuració del MySQL per:
•	Canviar la localització dels fitxers del tablespace de sistema per defecte a /discs-mysql/
Primer crem la carpeta /discs-mysql:

![image](https://user-images.githubusercontent.com/99834779/161993896-08142115-ba3a-40b3-8f00-363e3e0dfc2c.png)

I li canviem el propietari i li posem l’ usuari  mysql:

![image](https://user-images.githubusercontent.com/99834779/161993930-f581b604-5667-417d-978c-4de6e69c10fb.png)

Ara aturem el servei mysql:
 
![image](https://user-images.githubusercontent.com/99834779/161993966-7841461a-3768-43f6-99af-7248ed817889.png)

I copiem les dades de la carpeta /var/lib/mysql a la de disc-mysql:

![image](https://user-images.githubusercontent.com/99834779/161994042-3c36c42a-8a2d-48fd-9e32-5f0ad57410ce.png)

I ara anem el fitxer de configuració i canviem el data dir i afegim una línia:

![image](https://user-images.githubusercontent.com/99834779/161994067-ca623730-53bb-43b4-8e06-4087e196f749.png)

Ara haurem d’ instal•lar aquest paquet que és per canviar les polítiques de Linux perquè ens deixi canviar el datadir:

![image](https://user-images.githubusercontent.com/99834779/161994108-6f4a0283-6d38-445a-b096-9e003d599338.png)

I per canviar l’ubicació del directori fem aquestes dos comandes:
 
![image](https://user-images.githubusercontent.com/99834779/161994215-3487a7ca-82a3-418b-b60b-50e96362ba25.png)
![image](https://user-images.githubusercontent.com/99834779/161994223-c9da7eca-9f09-4db0-a1b2-c0db4c21b690.png)

I tornem activar el servei de mysql:
 
![image](https://user-images.githubusercontent.com/99834779/161994265-5064cd91-9118-4840-afac-c246c6836013.png)

I ara entrem dintre del mysql per veure si ha canviat el datadir:

![image](https://user-images.githubusercontent.com/99834779/161994302-ae769e22-ba0e-427f-8a60-9546ce41ce89.png)

•	Tinguem dos fitxers corresponents al tablespace de sistema.
•	Tots dos han de tenir la mateixa mida inicial (10MB) 
•	El tablespace ha de créixer de 5MB en 5MB.
•	Situa aquests fitxers (de manera relativa a la localització per defecte) en una nova localització simulant el següent:
•	/discs-mysql/disk1/primer fitxer de dades → simularà un disc dur
•	/discs-mysql/disk2/segon fitxer de dades → simularà un segon disc dur.
Primer creo les dos carpetes a l’ ubicació /discs-mysql/:

![image](https://user-images.githubusercontent.com/99834779/161994378-baff1ad0-90ea-4624-b7fb-2d7a2e307741.png)
![image](https://user-images.githubusercontent.com/99834779/161994397-1531ec0e-dd63-4a8c-9863-f6d3019581c3.png)

Ara els canvio el propietari a les dos carpetes per l’usuari mysql:

![image](https://user-images.githubusercontent.com/99834779/161994431-354e0c0e-7f26-4493-a5ac-4cf1108d9e38.png)

Ara comprovem que s’han creat:
 
![image](https://user-images.githubusercontent.com/99834779/161994462-201a56ba-1752-4661-9576-995d60b06527.png)

Després esborro aquets arxius que estan en l’ubicació /discs-mysql/

![image](https://user-images.githubusercontent.com/99834779/161994494-e0be6a53-5791-43ca-b2d5-83adfc4a219b.png)

Ara aturo el servei de mysql:

![image](https://user-images.githubusercontent.com/99834779/161994543-ffba3d13-8d6b-49e9-9112-134440c27baf.png)

Després d’ aturar el sistema modifiquem el fitxer my.cnf:

![image](https://user-images.githubusercontent.com/99834779/161994577-1614c40e-f830-49ec-a623-3b865f48fa4b.png)

I iniciem un altre cop el servei mysql i fem aquestes comprovacions per veure si s’ha canviat. Primer, dintre del mysql comprovem aquesta variable:
 
![image](https://user-images.githubusercontent.com/99834779/161994595-f8ee9ba1-e339-4ad3-9531-89045de66574.png)

I l’altre comprovació que he fet es anant a cada carpeta de disk i mirant si ha creat els ibdata:

![image](https://user-images.githubusercontent.com/99834779/161994618-52ea4bfb-f89c-46e4-8386-4dc439103526.png)

Checkpoint: Mostra al professor els canvis realitzats i que la BD continua funcionant.
