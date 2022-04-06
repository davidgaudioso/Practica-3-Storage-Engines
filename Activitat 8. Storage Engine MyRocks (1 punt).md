### Activitat 8. Storage Engine MyRocks (1 punt)

### A tenir en compte en cas de treballar amb Persona Server 8.x:
### https://www.percona.com/doc/percona-server/8.0/upgrading_guide.html

### •	Documenta i posa exemple de com utilitzar ENGINE MyRocks. Crea una Base de dades amb 2 o 3 taules i inserta-hi contingut.
### •	Cal documentar els passos que has hagut de realitzar per preparar l'exemple: configuracions, instruccions DML, DDL, etc....
### Primer crearem la base de dades, anirem al mysql i la crearem:

![image](https://user-images.githubusercontent.com/99834779/161999409-c9ef34f3-5b7f-4fd0-95b2-4f0c06401183.png)

### Després crearem dos taules dintre de la base de dades:

![image](https://user-images.githubusercontent.com/99834779/161999431-310ab79e-4232-4d54-aa81-c6e75258d631.png)

### I inserim valors a les dos taules creades:

![image](https://user-images.githubusercontent.com/99834779/161999459-c75a4f79-3151-4b72-8fdd-953eefabcc84.png)
![image](https://user-images.githubusercontent.com/99834779/161999472-4d7e31c1-1149-4153-8702-0368e7ddeb98.png)
 
### •	A quin directori es guarden els fitxers de dades? Fes un llistat de a on són els fitxers i què ocupen.
### Es guarden en aquesta ubicació i conté aquests fitxers amb aquesta mida:

![image](https://user-images.githubusercontent.com/99834779/161999519-5329c84e-7169-4b9e-aa16-56ddfffef80f.png)

### •	Quina és la compressió per defecte que utilitza per les taules? Com ho faries per canviar-lo. Per exemple utilitza Zlib o ZSTD o sense compressió.
### Per veure quin té per defecte he fet aquesta consulta dintre del mysql i es el KLZ4:

![image](https://user-images.githubusercontent.com/99834779/161999544-e7fdac5e-ce4b-45e2-8a28-88c2ab9c798e.png)

### Per canviar la compressió serà d’aquesta manera, primer en el fitxer de configuració “my.cnf” afegirem al línia subratllada en vermell i he utilitzat la compressió amb el nom KZSTD:

![image](https://user-images.githubusercontent.com/99834779/161999565-d35d1328-5039-48ff-a87c-c2801aebcfa1.png)

### Després reiniciem el servidor mysql i és amb aquesta comanda:

![image](https://user-images.githubusercontent.com/99834779/161999595-8ee6c36d-0a5d-416e-a667-6a16b741b6d9.png)

### I per últim entrem dintre del mysql amb l’usuari root i fem la mateixa consulta d’abans:

![image](https://user-images.githubusercontent.com/99834779/161999627-70f592ef-687c-4e1f-8d3d-5ee7113f7d26.png)

### Checkpoint: Mostra al professor la configuració que has hagut de realitzar i el seu funcionament.
