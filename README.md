# IRIS - Database and Report Template



![](./assets/logo_blue.png)



## General Information

- DFIR-IRIS uses the **Jinja2** engine to generate reports in DOCX format from XML query. 
- Below, a list of queries and results returned on a current case.
- [General Information Query](./query/Query_General_Information.md)



## Query details

- [Assets query](./query/Query_Template_Assets.md)
- [Case query](./query/Query_Template_Case.md)
- [Evidences query](./query/Query_Template_Evidences.md)
- [IoCs query](./query/Query_Template_IOCS.md)
- [Notes query](./query/Query_Template_Notes.md)
- [Tasks query](./query/Query_Template_Tasks.md)
- [Timeline query](./query/Query_Template_Timeline.md)



# Database

### Export 

- List the current running docker containers :

  - ```bash
    docker container list
    ```

- Spot the IRIS DB container name or ID, and execute the backup :

  - ```bash
    docker exec <container> pg_dump -U postgres iris_db | gzip > ./iris_db_backup.gz
    ```

- Ensure the backup was successful by looking at the gz file :

  - ```bash
    zcat ./iris_db_backup.gz | less
    
    Note : 'q' for exit
    ```



### Import

- Stop IRIS and start only database container :

  - ```bash
    └─# docker ps -a             
    CONTAINER ID   IMAGE                          COMMAND                  CREATED         STATUS                        PORTS                      NAMES
    ad3d54a013a2   iriswebapp_nginx:v2.4.7        "/entrypoint.sh"         6 minutes ago   Exited (0) 47 seconds ago                                iriswebapp_nginx
    3dbe4db8e8ea   iriswebapp_app:v2.4.7          "./wait-for-irisweba…"   6 minutes ago   Exited (137) 37 seconds ago                              iriswebapp_worker
    7779a2a2269e   iriswebapp_app:v2.4.7          "nohup ./iris-entryp…"   6 minutes ago   Exited (137) 27 seconds ago                              iriswebapp_app
    b4d3aa84a22d   rabbitmq:3-management-alpine   "docker-entrypoint.s…"   6 minutes ago   Exited (0) 26 seconds ago                                iriswebapp_rabbitmq
    1d6b45acef1f   iriswebapp_db:v2.4.7           "docker-entrypoint.s…"   6 minutes ago   Up 7 seconds                  127.0.0.1:5432->5432/tcp   iriswebapp_db
    ```

- Delete the current database :

  - ```bash
    echo "DROP DATABASE IF EXISTS iris_db;" | docker exec -i 1d6b45acef1f psql -U postgres
    ```

- Create the new database : 

  - ```bash
    echo "CREATE DATABASE iris_db;" | docker exec -i 1d6b45acef1f psql -U postgres
    ```

- Restore database date :

  - ```bash
    zcat ../iris_db_backup.gz | docker exec -i 1d6b45acef1f psql -U postgres -d iris_db
    ```

- Start IRIS :

  - ```bash
    docker-compose up
    ```
