Activitat 6. Implementar BD Distribuïdes. (1,5 punts)

Com s'ha vist a classe MySQL proporciona el motor d'emmagatzemament FEDERATED que té com a funció permetre l'accés remot a bases de dades MySQL en un servidor local sense utilitzar tècniques de replicació ni clustering.

•	Prepara un Servidor Percona Server amb la BD de Sakila
•	Prepara un segon servidor Percona Server a on hi hauran un conjunt de taules FEDERADES al primer servdor.
•	Per realitzar aquest link entre les dues BD podem fer-ho de dues maneres:
•	Opció1: especificar TOTA la cadena de connexió a CONNECTION 
•	Opció2: especifficar una connexió a un server a CONNECTION que prèviament s'ha creat mitjançant CREATE SERVER
•	Posa un exemple de 2 taules de cada opció. 
Tingues en compte els permisos a nivell de BD i de SO així com temes de seguretat com firewalls, etc...
•	Detalla quines són els passos i comandes que has hagut de realitzar en cada màquina.

Checkpoint: Mostra al professor la configuració que has hagut de realitzar i el seu funcionament.
