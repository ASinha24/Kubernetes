# Kubernetes
This repository contains guide for k8s related things.


* A Kubernetes Operator acts as an automated site reliability engineer for its application.​
* The operator continues to monitor its application while it runs, and can automatically back up data, recover from failures, and upgrade the application over time.
* k8s operator can be created on CRDs(custom resource definitions)

## CRD
* The CustomResourceDefinition API resource allows you to define custom resources. 
* Defining a CRD object creates a new custom resource with a name and schema that you specify. 
* The Kubernetes API serves and handles the storage of your custom resource. The name of a CRD object must be a valid DNS subdomain name.

## k8s operator Architecture Diagram

![controller Architecture]([https://github.com/[username]/[reponame]/blob/[branch]/image.jpg?raw=true](https://github.com/kubernetes/sample-controller/blob/master/docs/images/client-go-controller-interaction.jpeg)https://github.com/kubernetes/sample-controller/blob/master/docs/images/client-go-controller-interaction.jpeg)

### steps To apply Business logic on CRDs
```
1. golang client -> generate golang client using CRDs, which does create data definition and API client for the CRD
2. webhook (validation and mutation) -> webhook takes the crds object and validates the spec and add mutate it (add custom lable etc)
3. Controller -> it contains the business logic of CRDs on event(create/update/delete) based.
```

