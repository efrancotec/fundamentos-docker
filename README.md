# fundamentos-docker
proyecto para seguir curso de fundamento Docker 

Pasos del reto 2

1) Se crea un volumnes con el nombre "retodata"
   Comando: docker volume create retodata 
2) Se crea la red (netword)
   Comando: docker network create reto-network -d bridge
3) Se crea el contenedor del backend con el volumen previamente creado en el step 1
   Comando: docker run -d -p 3000:3000 --name teemii-backend -v retodata:/var/teemii-backend/data dokkaner/teemii-backend:develop
4) Se agrega el contendor creado a la red
   Comando: docker network connect reto-network teemii-backend
5) Se crea el contendor del frondend y se agrega a red
   Comando: docker run -d -p 8080:80 --name teemii-frontend --network reto-network dokkaner/teemii-frontend:develop
6) Ir a la interface grafica mendiante el navegador
   Url: localhost:8080
   Nota: es importante borrar datos de navegacion antes de ir a la url
