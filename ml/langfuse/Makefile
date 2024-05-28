MANIFEST := rendered.yaml

.PHONY: render deploy undeploy

render:
	kustomize build deploy/ --enable-helm --output ${MANIFEST}

deploy:
	kubectl apply -f ${MANIFEST}

undeploy:
	kubectl delete -f ${MANIFEST}