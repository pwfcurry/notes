# Kubernetes

## minikube

Host a local kubernetes cluster for testing

	minikube start|stop|dashboard
	
## kubectl

Interact with kubernetes (local minikube or otherwise)

	kubectl create ns <namespace name>
	kubectl create 0f <yaml file> --namespace=<ns>
	kubectl describe deployments --namespace=<ns>
	kubectl get pods --namespace=<ns>
	kubectl logs <pod name> --namespace=<ns>