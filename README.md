# pruebaCuatro

Instrucciones para la prueba, primero descargue el repositorio completo con todos los archivos.

1. Ingrese a visual code y ejecute: cd ./prueba mvn clean package
    O si desea desde eclipse solo con clean package

2. Ejecuta desde la carpeta del proyecto 
   docker-compose up --build

3. Probar la api en el siguiente url:  http://localhost:8080/api/universidades

4. Crear universidad:
  curl -X POST http://localhost:8080/api/universidades -H "Content-Type: application/json" -d '{"nombre":"Universidad UPS","ciudad":"Quito"}'

5. Verificar que se haya guardado:
  curl http://localhost:8080/api/universidades

7. Iniciar docker-desktop y minikube 
   minikube start 

6. Despliegue de kubernetes - Subir imagen Docker al Docker Hub (antes del despliegue):

docker login
docker tag pruebacuatro-app koker18/universidad-app:latest
docker push koker18/universidad-app:latest

7. Comandos para desplegar en Kubernetes

kubectl apply -f database-deployment.yaml
kubectl apply -f database-service.yaml
kubectl apply -f microservice-deployment.yaml
kubectl apply -f microservice-service.yaml

8. Verificar recursos
kubectl get pods
kubectl get services

9. En Minikube, acceder al servicio:

minikube service universidad-service
