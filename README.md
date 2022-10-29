# GCP-Final-Task 
Deploy a python web application on GKE. Infrastructure built using terraform. Using docker to containerize the application.

## Build image and upload to GCR
```
docker build -t <img-name> gcr.io/<project-id>/<img-name> .
gcloud auth configure-docker   # to add 
docker push gcr.io/<project-id>/<img-name>
```
## Build infrastructure on GCP
```
cd terraform/
terraform init
terraform apply
```
## Connect to private GKE cluster through private vm
```
gcloud compute ssh management-instance --tunnel-through-iap
gcloud container clusters get-credentials private-cluster --zone us-central1-a
```
## Deploy app to GKE cluster and expose deploymnet through load balancer
```
helm install myapp ./Helm
```
!
## Connect using load balancer public IP
![![Screenshot%20from%202022-10-29%2022-35-42](https://github.com/Alialshemy/GCP_Project/blob/main/images/Screenshot%20from%202022-10-29%2022-35-42.png)
]
