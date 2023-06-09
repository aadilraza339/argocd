Create Application in Argocd

### Declarative Setup
Argo CD applications, projects and settings can be defined declaratively using Kubernetes manifests. 
These can be updated using kubectl apply, without needing to touch the argocd command-line tool.
![Screenshot from 2023-06-03 14-10-37](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/a2f40e65-0e42-49c6-80b0-1604910d1311)
### Create Argo Cd Application.
Define an Argo Cd application declaratively using Yaml. </br>
You get over view how to create application using Yaml here is [link](https://github.com/aadilraza339/udemy-app-definition/blob/main/application.yaml)

Run this command on termial to crate application in Argo CD
```
kubectl apply -f application.yaml 

```
Output: </br>
![image](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/345b2e7a-4ae0-465a-b17f-8f6e5528f58a)

### We also can create application using Argocd UI
![image](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/02af4583-aca5-4cd9-b1d8-4ed8350a0542)
Please complete the required fields to create the application.

### Create application using CLI
Command:
```
argocd app create demo-app-for-testin --repo https://github.com/aadilraza339/udemy-coruse.git --path guestbook --dest-namespace default --dest-server https://kubernetes.default.svc --directory-recurse

```
Output: </br>
![image](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/3d0330e7-2488-4f13-b07e-38a870e1b37a)

### Crated Application
![image](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/675298ea-2038-436c-b9c3-f405f8d25a25)

# What is a project in Argocd

Projects provide a logical grouping of application
- Access Restriction
- Useful when argocd is used by multiple teams
- Allow only specific sources trusted git repos
- Allow apps to be deployed into specific clusters and namespaces.
Project Role feature
- Enables you to create a role with a set of policies and permission to grant access to a project's application 
- default argocd project
- Argocd creates a default project once you install it.

### Creating projects options
- Declaratively
- CLI
- Web UI
Create a project with Argocd UI: [video](https://drive.google.com/file/d/1CbLplrXIAJnZITXqolnao7aIsfew-t0i/view?usp=drive_link)
Lets create a project using Declaratively yaml [file](https://github.com/aadilraza339/udemy-app-definition/blob/main/project.yaml)
```
kubectl apply -f project.yaml 
```

output: </br>
![image](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/6b4c9bfd-d4b6-4dea-a93c-8aa66de2a49e)


Now creating application under a project: [file](https://github.com/aadilraza339/udemy-app-definition/blob/main/application-set-project.yaml)
```
kubectl apply -f application-set-project.yaml
```
Output </br>
![image](https://github.com/aadilraza339/udemy-app-definition/assets/47937273/7f53c8e9-5361-424b-bcf1-d1a5a7e63fe9)

### Create a project with name-space restiction: [video](https://drive.google.com/file/d/1CbLplrXIAJnZITXqolnao7aIsfew-t0i/view?usp=drive_link) 

### Create a project with role. [Video](https://drive.google.com/file/d/1_8mOwrGCyKD3FsjOadzzishNrTCDype7/view?usp=drive_link)

Create role
```
argocd proj role create-token project-with-role <role name>
```
Delete app  

```
argocd app delete <gestbook-dev-project> --auth-token <token>
```

