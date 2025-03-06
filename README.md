# NPCI Blockchain Assignment-8

## Kubernetes Introduction [10 Marks]

## Assignment Objective

The goal of this assignment is to develop hands-on expertise in deploying and managing applications in a Kubernetes cluster. The assignment requires setting up a dedicated namespace, deploying an **NGINX-based web application**, and configuring services for both **internal access**.

By completing this assignment, students will gain practical experience in:

*   Creating and managing **Kubernetes namespaces**.
*   Deploying applications using **Deployments** and managing replicas.
*   Configuring **ClusterIP** service to expose applications.
*   Scaling and updating deployments dynamically.
*   Verifying and troubleshooting Kubernetes deployments.


## Steps to Follow

- This GitHub repository will be accessible to you once you accept the Assignment.
- You have to work directly in this GitHub repository. It is like your own copy of the original repository.
- Start a new Codespace. It will have Kubernetes preinstalled.

  Note that it may take around 5 minutes for the Codespace to start after you click on "Create Codespace".

- If you are using Kubernetes from your system then below are the prerequisites:
  *   **GitHub Account** (for code submission).
  *   **Docker and Docker Compose** installed.
  *   **kind CLI** (for running local Kubernetes cluster) [https://kind.sigs.k8s.io/docs/user/quick-start/].
  *   **kubectl CLI** (for deploying updates to the Kubernetes cluster) [https://kubernetes.io/docs/tasks/tools/].

- Do not edit anything in `.devcontainer` and `cli` folders.


## Assignment Tasks

1.  **Create a Namespace** [2 Marks]
   
    *   Create a new namespace called **web-app-namespace**.
    *   Verify the new namespace.
      
2.  **Deploy an NGINX Application** [3 Marks]
   
    *   Deploy an NGINX application inside the **web-app-namespace**.
      
        *   Name: `nginx-deployment`
        *   **3 replicas** for high availability.
        *   A container image of `nginx:latest`.
        *   The container should listen on **port 80**.
        *   Set an environment variable **APP_ENV=production** inside the container.
          
3.  **Expose the Application via a Service** [3 Marks]
   
    *   Create one service:
      
        *   **ClusterIP Service** (Internal Access):
            *   Name: `nginx-clusterip`
            *   Type: `ClusterIP`
            *   Exposes **port 80**
              
4.  **Verify the Deployment & Service** [2 Marks]
   
    *   Ensure the pods are running in the correct namespace.
    *   Check if the **ClusterIP service** is accessible from within the cluster.
    *   Check if you are able to make a request to the Nginx application using the service. For example: `curl://nginx-clusterip.web-app-namespace.svc.cluster.local`.

## Deliverables

Upon completion of this assignment, students will be able to:

*   Set up a namespace and deploy applications within it.
*   Define and apply Kubernetes **Deployment manifests** for containerised applications.
*   Expose applications via **ClusterIP** (internal) service.
*   Add screenshots of the deployed pod, services, and curl request to the `SubmissionImages` folder in the repository.

## Bonus Tips

```bash
kubectl get ns
kubectl get pods -n web-app-namespace
kubectl describe pod nginx-deployment -n web-app-namespace
kubectl get svc -n web-app-namespace

curl://nginx-clusterip.web-app-namespace.svc.cluster.local
