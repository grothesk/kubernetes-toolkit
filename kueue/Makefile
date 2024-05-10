KUEUE_VERSION := v0.6.1
CLUSTER_NAME := kueue


create-cluster:
	minikube start -p ${CLUSTER_NAME} --cpus=4 --memory=8g

stop-cluster:
	minikube stop -p ${CLUSTER_NAME}

delete-cluster:
	minikube delete -p ${CLUSTER_NAME}

install-kueue:
	kubectl apply --server-side -f https://github.com/kubernetes-sigs/kueue/releases/download/${KUEUE_VERSION}/manifests.yaml

uninstall-kueue: 
	kubectl delete -f https://github.com/kubernetes-sigs/kueue/releases/download/${KUEUE_VERSION}/manifests.yaml

setup-kueue:
	kubectl apply -k deploy/setup

run-jobs:
	kubectl apply -k deploy/run
