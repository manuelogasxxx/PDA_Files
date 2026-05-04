# MinIO

Contiene la implementación para el MinIO Distribuido.
Ejecuta los siguientes comandos para poder probarlo.

1. Ejecuta el contenedor con
```
    docker compose up -d
```
2. Genera las access/secret keys
    ```
    docker exec -it minio sh

    mc alias set local http://localhost:9000 usuario contraseña

    //Formato: mc admin user add <ALIAS> <ACCESS_KEY> <SECRET_KEY>
    
    mc admin user add local mi-access-key mi-secret-key-123

    mc admin policy attach local readwrite --user mi-access-key
    ```
    Una ves que tengas las access/secret Keys copialas en este fragmento del Program.cs del repositorio PDD_Archivos
    ```
    string accessKey = "R5CJVLB6RN0VYHKDDQNO";
    string secretKey = "pnGR2I7flEJT7v8bUhynke3v9X1lKsHG8MqloS1I";
    ```
3. Accede a la GUI con la siguiente dirección: https://localhost:9001 y crea un contenedor llamado "pdfs"


