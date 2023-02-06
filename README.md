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


__Steps :__  

1. Configure Hosted zone on AWS Route53 for k8s cluster domain  
2. Create Kubernetes Cluster on AWS EC2 with kops, kubectl   
3. Containerize the application, build images and push it to dockerhub registry. 
4. Create Kubernetes manifest files to create deployment and service components for application application, database, memcache and rabbitmq containers. 
5. Create EC2 volume and mount it to database deployment, deployed all the components and setup AWS Route53 subdomain to access the web application.

```   
   ┌─────────────┐   
   │Load-Balancer│             
   └─────────────┘
          |↑
          ||   _______┌─────┐
          ||  //-----→│MySQL│←-----
          ↓|  ↓|      └─────┘----||
    ┌─────────────┐     |↑       ||
    │Tomcat_Server│     ||       ||
    └─────────────┘     ↓|       ||
          |↑        ┌────────┐   ||
          ||        │Memcache│   ||
          ||        └────────┘   || 
          ↓|         ↑|          ||
      ┌────────┐     //          ||
      │RabbitMQ│____//           ||
      └────────┘←----            //
          |↑                    //
          ||___________________//
          ----------------------     
```     
