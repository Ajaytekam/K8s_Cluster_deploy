# Deploying Java Web Application on Kubernetes Cluster  

__WebApp :__ The Containerized Java Web Application can be found [here](https://github.com/Ajaytekam/docker-containerization-project).      

__Requirements :__  

1. Kubernetes Cluster (kops in EC2)  
2. [Containerized Application](https://github.com/Ajaytekam/docker-containerization-project)   
3. EBS volume for Database Pod
4. Label Node with zone names 
5. Kubernetes definition files to create objects on kubernetes cluster. 
    * Deployment
    * Service
    * Secret
    * Volume

