helm install dockerhub  --namespace registry --set replicaCount=1  --set persistence.enabled=true  --set persistence.size=500Gi  --set persistence.deleteEnabled=true  --set persistence.storageClass=csi-rawfile-default  --set persistence.existingClaim=dockerhub-pvc  twuni/docker-registry  --version 1.10.1


kubectl port-forward -n registry svc/dockerhub-docker-registry 5000:5000


ssh -N -L 5000:localhost:5000 ubuntu@16189102.
