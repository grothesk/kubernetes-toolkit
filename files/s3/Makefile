MINIO_ACCESS_KEY := minio
MINIO_SECRET_KEY := minio123

deploy-minio:
	kubectl apply -k deploy/minio

deploy-local-storage:
	kubectl apply -k deploy/local-storage

establish-minio-port-forwarding:
	kubectl -n minio port-forward svc/minio 9000:9000

create-backup-bucket:
	mc config host add s3 http://localhost:9000 ${MINIO_ACCESS_KEY} ${MINIO_SECRET_KEY}
	mc mb s3/backup
