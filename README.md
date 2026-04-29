# PDA_Files
Microservicio de gestión de archivos

# ¿cómo ejecutarlo?

ejecuta la siguiente serie de comandos en la terminal

1. Levantar el docker compose
    docker compose up -d

    Detener o actualizar

    docker compose down

    Reiniciar despues de un cambio

    docker compose up -d --build
2. Generar las access/secret keys

    docker exec -it minio sh

    mc alias set local http://localhost:9000 usuario contraseña

    Formato: mc admin user add <ALIAS> <ACCESS_KEY> <SECRET_KEY>
    
    mc admin user add local mi-access-key mi-secret-key-123

    mc admin policy attach local readwrite --user mi-access-key

3. Las access/secret keys van en el archivo program.cs de /PDA_Files

4. Ejecuta la API con visual studio o con "dotnet run"
5. Ingresa a https://localhost:7116/swagger/index.html para ver los endpoints


# ¿que falta por hacer?
1. Conexión con la base de datos para guardar metadatos y generar urls de MinIO para los endpoints
2. Integrarlo con la parte del Ulises
3. Integrarlo con la parte del Moy
4. revisar el problema del port forwarding para que otras computadoras accedan al recurso de MinIO
5. Hacer que el MinIO funcione de forma distribuida SIN FRAGMENTACION 

