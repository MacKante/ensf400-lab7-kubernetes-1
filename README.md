# ensf400-lab7-kubernetes-1

## Objectives
This lab will teach us the basic usage of Kubernetes. Through Minikube, a simplified Kubernetes engine running on a single computer, we practice the key concepts and usage of Kubernetes.

## Environment

### Set Up Your GitHub CodeSpaces Instance

Same as Lab 6, this lab will be performed in [GitHub CodeSpaces](https://github.com/codespaces). Create an instance using GitHub Codespaces. Choose repository `denoslab/ensf400-lab7-kubernetes-1`.


```bash
minikube start
```

This step will start the Minikube service in a container.

## Steps

Go to Section 1 - 6 and complete the steps for each section. The steps can be found in the `README.md` files in each subdirectory.

## Have Your Work Checked By a TA

The TA will check the completion of the following tasks:

- Output of Section 1.
- Output of Section 2.
- Output of Section 3.
- Output of Section 4.
- Output of Section 5.
- Output of Section 6.

Each member of the group should be able to answer all of the following questions. The TA will ask each person one question selected at random, and the student must be able to answer the question to get credit for the lab.

- Q1: How to check which Node a Pod is running on? Use an example to show where this information can be found.
    - Create a manifest for pod then create it: kubectl apply -f <manifest file here>
    - `kubectl get pods -o wide`

- Q2: How to scale a ReplicaSet? Use an example to demonstrate scaling a ReplicaSet to 3 replicas.
    - `kubectl scale --replicas=6 -f nginx_replicaset.yaml`

- Q3: Briefly describe the process of a deployment rolling update, i.e., how are new version of pods created and how are old version of pods terminated. Which configurations can control the pods being created or deleted in parallel?
    - It generates a new ReplicaSet revision that is initially scaled up based on maxSurge. Phase out of old Pods managed by maxSurge and maxUnavailable.

- Q4: Inside the Kubernetes cluster, how to access a service named "svc1" offering HTTP service at Port 8000?
    - Get the IP: `kubectl get svc1`, choose the node
    - curl whatever the IP

- Q5: What is an Ingress in Kubernetes? What type of resources does an Ingress configuration typically point to as its backend? 
    - An ingress is an object that allows us to access kubernetes services from outside the cluster, can be configured by accessin