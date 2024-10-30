# Essential CLI Commands Note
*patcharanat p.*

## Bash / Shell
```bash
ls # -a for hidden folder '.' as prefix
mkdir <folder-name>
rm <file-name>
rmdir <folder-name> # -r for recursive deleting
cat <file-name>
nano <file-name>

export <var-name>=<value>
unset <var-name>

# grant execution access to a file
chmod +x <file-name>

# recursively find filename that match specified glob pattern
find . -iname "<glob-pattern>"

# sh script
var1="$1"
var2="$2"
var3="$3"

if [[ ]]; then [[ ]] else [[ ]] fi
command="..."
eval $command
```

## Python
```bash
# built-in python virtualenv
python -m venv <folder_name>

# bash (unable to use via Makefile)
source ./<folder_name>/Script/activate
```

## Docker
- Docker
```bash
docker ps

# Dockerfile located in the current workdir
docker build -t <image_name:tag> .
# or docker build -t <image_name:tag> -f <Dockerfile-name-path>

# rename image
# docker tag <built-image-name>:<tag> <repo-name>:<optional-tag>
docker tag kde-mbti-streamlit:latest patcharanat/kde-public-repo

# push to docker hub
# docker push <renamed-image-name>:<tag>
docker push patcharanat/kde-public-repo:latest

docker run -it --name <container_name> <image_name> <app_arg> ...
# -p for port

docker exec -it <container_name_or_id> bash

docker stop <container_name_or_id>
```
- Docker compose
```bash
# docker-compose.yml located in the current workdir
docker compose build

# (flag -d for detach mode)
docker compose up

# remove volumes
docker compose down -v
```

## Terraform
```bash
# terraform files located in the current workdir
terraform init

terraform plan

terraform apply

terraform destroy
```

## Kubernetes (k8s)
```bash
# install
# curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
# sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Initialize k8s cluster
minikube start
# check cluster status
minikube status
kubectl cluster-info
# minikube ssh


# --------------------------------------------------------
# Prepare environment
# check status
kubectl get namespaces

# create a new namespace
kubectl create namespace airflow

# kube config (~/.kube/config)
# kubectl config view
# kubectl config get-contexts
# kubectl config use-context <context-name>
# kubectl config delete-context <context-name>
# kubectl config set-context [Context-Name | --current] --namespace=airflow
# kubectl logs <pod-name> -n <namespace>


# --------------------------------------------------------
# Add helm repo
# helm pull apache-airflow/airflow --version 1.14.0 --untar
helm repo add apache-airflow https://airflow.apache.org
helm repo update
# helm ls

# --------------------------------------------------------
# Install the Airflow chart -- this may take a while
# helm install airflow apache-airflow/airflow
# helm install airflow apache-airflow/airflow -n airflow
helm install airflow apache-airflow/airflow --namespace airflow --debug

# for specific airflow version
# helm install airflow apache-airflow/airflow --version 1.14.0 --namespace airflow

# if release is stuck while installing or timed out --> reinstall chart
# helm delete airflow --namespace airflow

# --------------------------------------------------------
# Check status the deployed airflow
kubectl get pods -n airflow
# Check release
helm ls -n airflow

# Forward port
kubectl port-forward svc/airflow-webserver 8080:8080
# kubectl port-forward svc/airflow-webserver 8080:8080 -n airflow
# kubectl port-forward svc/airflow-webserver 8080:8080 -n airflow --context kind-airflow-cluster
# -- go to http:///localhost:8080

# --------------------------------------------------------
# Customize airflow deployment
helm show values apache-airflow/airflow > values.yaml
# -- edit values.yaml

# for the first time initialization with customized configuration
helm install airflow apache-airflow/airflow -f values.yaml
# for upgrading the existing release (Re-deploy)
helm upgrade airflow apache-airflow/airflow -f values.yaml
# helm upgrade --install airflow apache-airflow/airflow --namespace airflow --f values.yaml 

# --------------------------------------------------------
# Clean up
helm uninstall airflow
kubectl delete pvc --all
kubectl delete pv --all
minikube stop
minikube delete --all
```

## GCP
```bash
# As a developer, I want to interact with GCP via gcloud.
gcloud auth activate

# As a developer, I want my code to interact with GCP via SDK.
gcloud auth application-default login

# copy a file
gsutil cp <local-source-path-or-cloud-URI> <destination>
# copy folder use flag -r
```

## Azure
```bash
azcopy cp <file_name> "<target-url>"
```

## Postgresql
```bash
psql -U <username> -d <database-name>

# list all tables -- equal to '\d'
\dt

# list all schemas -- equal to '\dz'
\dn

\q
```
