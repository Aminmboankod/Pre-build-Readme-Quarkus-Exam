# [Nombre del examen]

Este proyecto es mi solución al examen de Quarkus planteado por nuestro profesor de programación y entornos de desarrollo. En el se encuentran los dos ficheros con los test para desarrollar la aplicación APIREST mediante TDD, uno para el desarrollo de los servicios y otro para los endpoints.

- [Indice](#)
  - [Pruebas](#ejecución-de-pruebas)
  - [Ejecución de la aplicación](#ejecutar-la-aplicación-en-modo-desarrollo)
  - [Uso](#uso)


## Ejecución de pruebas

Puedes ejecutar las pruebas utilizando el siguiente comando:

```shell script
./mvnw test
```

Para ejecutar sólo las pruebas de servicios:

```shell script
./mvnw -Dtest="ServiceTest" test
```

Para ejecutar las pruebas de integración:

```shell script
./mvnw -Dtest="ResourceTest" test
```

## Ejecutar la aplicación en modo desarrollo

Puedes ejecutar tu aplicación en modo desarrollo que permite la codificación en vivo utilizando:
```shell script
./mvnw compile quarkus:dev
```

## Empaquetar y ejecutar la aplicación

La aplicación puede ser empaquetada utilizando::
```shell script
./mvnw package
```
Esto producirá el archivo quarkus-run.jar en el directorio target/quarkus-app/.
Ten en cuenta que no es un über-jar ya que las dependencias se copian al directorio target/quarkus-app/lib/.

La aplicación ahora se puede ejecutar utilizando java -jar target/quarkus-app/quarkus-run.jar.

## Uso

La aplicación se sirve en http://localhost/8080.

Los endpoints que expone son lo siguientes:

```shell script

curl -w "\n" http://localhost:8080/examen/ -H "Content-Type: application/x-www-form-urlencoded"

curl -w "\n" http://localhost:8080/examen/ -H "Content-Type: application/json"

curl -d '{"name":"examen", "description":"examen"}' -H "Content-Type: application/json" -X POST http://localhost:8080/examen

curl -d '{"name":"examen", "description":"examen"}' -H "Content-Type: application/json" -X DELETE http://localhost:8080/examen

curl -w "\n" http://localhost:8080/examen/1 -v
curl -w "\n" http://localhost:8080/examen/1 -v

```
