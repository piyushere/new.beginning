- first switch to the docker env of minikube  
`eval $(minikube docker-env)`

- build your image using docker as usual  
`docker build ...`  
// or alternatively  
`docker compose build`

- create new deployment  
`kubectl create deployment <dep-name> image=<dep-image>:<version>`

- get the status of the deployment  
`kubectl get deployments`

- get the service status  
`kubectl get pods -l app=<name>`

- access the  service locally  
`kubectl port-forward deployment/kubecdc 80:3000 --address 0.0.0.0`

- Get the service URL when configured as NodePort  
`minikube service <service-name> --url`

- Attach to a pod  
`kubectl exec --stdin --tty cdcclient-5fff675b64-97pkv -- /bin/bash`
