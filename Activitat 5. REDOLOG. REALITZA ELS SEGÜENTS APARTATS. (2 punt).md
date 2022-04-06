### Activitat 5. REDOLOG. REALITZA ELS SEGÜENTS APARTATS. (2 punt)

### •	Com podem comprovar (Innodb Log Checkpointing):
### Per comprovar els Innodb Log Checkpointing, he hagut d’ entrar al mysql i posar aquesta comanda:

![image](https://user-images.githubusercontent.com/99834779/161996176-d161f213-70c6-410c-a197-a9d522f3a67e.png)

### •	LSN (Log Sequence Number)
### Aquest apartat es pot veure amb la comanda que hem fet abans per consultar i els LSN és aquest:
 
![image](https://user-images.githubusercontent.com/99834779/161996197-75f0dd52-a595-4aad-af5f-b624602417a8.png)

### •	L'últim LSN actualitzat a disc
### Aquest apartat es pot veure amb la comanda que hem fet abans per consultar i l’ últim LSN actualitzat  és aquest:

![image](https://user-images.githubusercontent.com/99834779/161996234-b23e168a-3747-4729-98c3-87cf029fa67d.png)

### •	Quin és l'últim LSN que se li ha fet Checkpoint
### Aquest apartat es pot veure amb la comanda que hem fet abans per consultar i l’ últim LSN que se li ha fet Checkpoint és aquest:

![image](https://user-images.githubusercontent.com/99834779/161996255-539b216c-8303-4d50-8b97-b9b0946df204.png)

### •	Proposa un exemple a on es vegi l'ús del redolog
### L’exemple serà modificar la mida dels redo logs d’ Innodb i per fer això, primer aturarem el servei mysql:
 
![image](https://user-images.githubusercontent.com/99834779/161996275-a315d0f6-b06f-45af-9291-15e0be55113e.png)

### Després aniré a l’ ubicació /var/lib/mysql i esborrarem els fitxers ib_logfiles, també podem veure quina mida tenen els fitxers:

![image](https://user-images.githubusercontent.com/99834779/161996304-3563b5b8-d19d-4363-9a8b-7464b4ca9067.png)

### Esborrarem els dos fitxers:

![image](https://user-images.githubusercontent.com/99834779/161996325-aacb01d7-41ec-4dcd-9740-7452f36b4018.png)

### Ara anem al fitxer de configuració que té el nom de my.cnf i posem les línies subratllades en vermell:
### innodb_log_file_size=64M, aquesta línia es la mida que tindrà els fitxers
### innodb_log_files_in_group=8, aquesta línia es per determinar quants fitxers vull crear.
 
![image](https://user-images.githubusercontent.com/99834779/161996374-02da0680-62cc-4ac6-a74f-a0648ffbf6a0.png)

### Ara inicio el servei mysql:

![image](https://user-images.githubusercontent.com/99834779/161996418-3b9ecbc8-2832-4532-953b-8b1dfdd6c26c.png)

### I faig la comprovació dels fitxers creats:

![image](https://user-images.githubusercontent.com/99834779/161996443-4100c92e-6bca-4081-ba33-b15f7ffb92db.png)

### •	Com podem mirar el número de pàgines modificades (dirty pages)? I el número total de pàgines?
### Es amb la mateixa comanda d’abans:

![image](https://user-images.githubusercontent.com/99834779/161996472-90787071-93ab-48ba-b463-60ced5fa5cb8.png)

### I el que està subratllat en vermell son les pàgines modificades i el nombre total de les pàgines:

![image](https://user-images.githubusercontent.com/99834779/161996514-cce2a42e-c0e1-448f-9f0c-078c2a66448b.png)

### Checkpoint: Mostra al professor els canvis realitzats i que la BD continua funcionant.
