### Activitat 3. INNODB part II. REALITZA ELS SEGÜENTS APARTATS (obligatòria)  (1 punt)

### •	Partint de l'esquema anterior configura el Percona Server perquè cada taula generi el seu propi tablespace en una carpeta anomenada tspaces (aquesta pot estar situada a on vulgueu).
### •	Indica quins són els canvis de configuració que has realitzat.
### Per fer aquest exercici primer he hagut de configurar el fitxer de configuració amb el nom “my.cnf” i he comentat aquesta la línia subratllada en vermell perquè les taules generin el seu propi tablespace:

![image](https://user-images.githubusercontent.com/99834779/161994980-ecdd4b31-f2bf-4184-98cf-76e119de818f.png)

### Després he reiniciat el servidor mysql i he fet la comprovació per veure s’ havia canviat:
 
![image](https://user-images.githubusercontent.com/99834779/161995014-57e5a596-6094-43a9-9100-157b7408dccd.png)
![image](https://user-images.githubusercontent.com/99834779/161995056-0022042c-9636-425b-96f2-cb4209199851.png)

### Ara crearem la carpeta amb el nom tspaces:	

![image](https://user-images.githubusercontent.com/99834779/161995072-19741ac8-91ed-436f-9413-f347b38360df.png)

### Li canviarem de propietari a la carpeta per l’usuari mysql:

![image](https://user-images.githubusercontent.com/99834779/161995087-e2d23b24-b500-4c58-b0e3-e5fd69328202.png)

### Després de crear la carpeta i canviar el propietari aturare el servei mysql:

![image](https://user-images.githubusercontent.com/99834779/161995128-4e60b1b5-f9bb-44d9-a0d5-a05c5084bbe8.png)

### Quant esta aturat el servei mysql copiarem tot el que està a l’ ubicació /var/li/mysql a la carpeta nova:

![image](https://user-images.githubusercontent.com/99834779/161995162-95a037af-34b5-4449-bcd0-43c0f6856cfb.png)

### I perquè es canvi l’ ubicació del directori fem aquestes dos comandes:

![image](https://user-images.githubusercontent.com/99834779/161995200-8f58d3f1-d08d-4cb4-af52-b292bf72df65.png)
![image](https://user-images.githubusercontent.com/99834779/161995210-eb2a0c67-a367-4e5c-8e79-0d141bccc93a.png)

### Ara anirem un altre cop el fitxer amb el nom my.cnf y posarem aquesta configuració:
 
![image](https://user-images.githubusercontent.com/99834779/161995240-a924ef22-83fe-4a50-b003-755c10e0e3cb.png)

### Per últim iniciarem el servei mysql i faig la comprovació que s’ha canviat el datadir:

![image](https://user-images.githubusercontent.com/99834779/161995284-7140076a-ccc5-43b3-b148-c798f7b9e624.png)

