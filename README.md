# Kubernetes
[guide 1](https://kodekloud.com/blog/setup-kubernetes-cluster/)
[guide 2](https://kodekloud.com/blog/python-web-application-kubernetes-cluster/)

## Tools 

### [Minikube](https://minikube.sigs.k8s.io/docs/start/)
to create, run, delete a single-node or multi-node local Kubernetes cluster. can easily monitor the status of our clusters. used for daily development work

### [Kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/)
to create, manage, customize, and configure our clusters according to our needs and preferences. can automate the whole process by initializing the control plane and joining worker nodes to the cluster. can work on bare metal servers, cloud providers, and virtual machines alike.

### [kubectl](https://kubernetes.io/docs/tasks/tools/?)
to run commands against Kubernetes clusters. You can use kubectl to deploy applications, inspect and manage cluster resources, and view logs


## Steps
### Setup a Kubernetes cluster using Minikube
- start the cluster: `minikube start`
- interact with it: `kubectl get nodes`
- create an nginx Pod that we can later fetch from our Python web application: `kubectl run nginx --image=nginx`


## Notes
### If `minikube start` fails then if may be because it can’t connect to the Docker daemon due to permission issues
- list all the groups that the specified user ($USER) is a member of `groups $USER`

- add the specified user to the docker group. `sudo usermod -aG docker $USER`

    - `usermod` is the command used to modify a user account.
    - `-aG` option means "append the user to the group".

- start a new shell session with the specified group. refreshes group membership without needing to log out and back in. `newgrp docker`

- run `docker run hello-world` to verify Docker permissions
