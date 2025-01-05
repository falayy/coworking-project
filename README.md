## **Overview**

The deployment pipeline is designed to ensure seamless, reliable, and scalable application deployment. The solution leverages modern containerization, CI/CD, and Kubernetes orchestration to manage the entire process from development to production.

### **Key Technologies**
- **Docker**: Containerizes the application for consistent runtime environments.
- **Amazon ECR**: Stores and manages Docker container images.
- **AWS CodeBuild**: Automates the build process and integrates with version control systems.
- **Kubernetes (EKS)**: Manages the deployment and scaling of containerized applications.
- **CloudWatch**: To record the logs of the nodes.



 **How to deploy changes?**

1. Push Changes to GitHub

Push your code changes to GitHub. The pre-configured triggers with AWS CodeBuild will automatically build a new Docker image and tag it with the latest version.

2.Update and Deploy the Deployment File

Ensure the deployment file (e.g., coworking.yaml) references the newly built image with the updated tag.
Deploy the changes to your Kubernetes cluster by running:
```
kubectl apply -f coworking.yaml
```
3. Verify Deployment

Check the status of your deployment to ensure it is running successfully:
```
kubectl get svc
kubectl get pods
```

If needed, check the application logs in CloudWatch for more details about the application's status on the node.




