# Kubernetes ArangoDB backups
This Script is used to backup ArangoDB and upload it to Google Cloud Storage which runs as a cronjob in Kubernetes cluster

## Steps
- Create a bucket in Google Cloud Storage to upload the backups

- Create Google cloud service account with credentials and access permisions for GCS (Storage Object Creator, Storage Object Viewer): 

- Create kubernetes secret in your kubernetes cluster to store Service Account Credentials:
  kubectl create secret generic gcs-key --from-file=key.json=<PATH-TO-KEY-FILE>.json

- Replace the env in arangodb-cron.yaml 

- Apply arangodb-cron.yaml to your kubernetes cluster:
  kubectl apply -f arangodb-cron.yaml
