# Pasos para la ejecución
1. Tener instalado docker y mongosh
2. Ejecuta el contenedor con 
    ```
    docker compose up -d
    ```
3. Verifica la conexión con
    ```
    docker exec -it bd-archivos mongosh --eval "rs.initiate()"
    ```
4. Ingresa a la terminal de mongosh
    ```
    docker exec -it bd-archivos mongosh
    ```
5. Dentro de la terminal de mogosh ejecuta este comando
    ```
    var config = rs.conf();
    ... config.members[0].host = "localhost:27017";
    ... rs.reconfig(config, {force: true});
    ```
    Sirve para que la BD se acceda desde el nombre de localhost.
6. No es necesario realizar cambios en la proyecto de PDD_Archivos







# Estos son los comandos antiguos (guardados por si acaso xd)
2. Ejecuta el comando docker pull mongodb/mongodb-community-server:latest
3. Ejecuta el servidor como: 
docker run --name bd-archivos -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password123 -d mongodb/mongodb-community-server:latest 

3. Ejecuta el .yaml  (docker compose up -d)
docker exec -it bd-archivos mongosh -u admin -p password123 --eval "rs.initiate()"

4. La cadena de conexión es: mongodb://admin:password123@localhost:27017/?authSource=admin&replicaSet=rs0
var connectionString = "mongodb://localhost:27017/?replicaSet=rs0";

5.Despues de ejecutar el micriservicio de archivos es necesario ejecutar el endpoint "/api/files/inicializar-catalogo" con el JSON que aparece en esta carpeta "areas.json" 

