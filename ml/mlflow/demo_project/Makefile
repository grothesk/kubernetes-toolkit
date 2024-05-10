IMG ?= quay.io/maltegroth/mlflow-kubernetes-example
CONTAINER_CLI ?= docker

docker-build:
	${CONTAINER_CLI} build -t ${IMG} -f Dockerfile .

docker-push:
	${CONTAINER_CLI} push ${IMG}

run-project:
	pipenv run mlflow run . --backend kubernetes --backend-config kubernetes_config.json
