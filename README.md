# handnotes
# ############################################## AWS ###############################################################################

1Q  What is AMI?
 Ans:- AMI is an Amazon machine image mainly contains operating system and configuration files which is mainly used to deploy multi virtual machines, regardless of any AWS region

2Q What is an EC2 instance , and what are the types?
Ans:-  EC2(Elastic cloud Computing) is a virtual machine that represents your physical  machine for you to deploy an application.
Types of EC2
 General purpose(Web applications,small databases)
 Compute optimised,
 Memory optimised(machine learning), 
 Accelerated compute instance,
 Storage optimization instance.

3Q Different types of storage in AWS?
Ans:- 
Block storage
           Elastic block storage,
           Instant storage
Elastic File storage
AWS FSx Elastic file system is mainly used for Linux operating system. 
Aws fSx is mainly useful Windows operating system.
Object Storage -S3, glacier.

4Q What are the different types of load balances?
Ans:-  Application load balance
           Network load balancer
 Application load balancer works on TP and TPS protocol.TP measures data transmission rate and TPS measures transmission processing rate and network load balancer works on TCP and UDP protocol. Even application load balancer works on TCP protocol, but application load balancer doesn’t support UDP. Because UDP is very efficient protocol when we are using a streaming application or online meetings or any sort of streaming things, it is very useful. This is not supported by application load balancer. This is the major difference.
The major disadvantage with the network load balance is HTTP to https direction is not possible and also web application file was not supported.

5Q What are the different types of auto skilling groups we do have?
Ans:- 
  Vertical scaling- increasing resources of existing servers like More cpu , memory and   storage. 
Horizontal scaling-it will automatically create servers while the load is increasing.
horizontal scaling example DB servers, file, servers, APP servers for this server, vertical scaling is best suited.

6Q What are the different types of route 53 routing policies we do have??
Ans:- Latency means it will take the nearest data centre. To avoid the latency.
Failover- if one server goes down, the secondary server will take over
Weighted- example, there are a lot of uses in India due to large scale users. All the heads       are going to the US using latency to avoid such things. We need to load balancing that is waited.
Geo location -Jio location will strictly follow the band rules, Indian and NewZealand should go to India only and US region User should go to US only.
Multivalues -we can give multiple server IP in multi values, specifically, it takes any one of the IP.

7Q What is CDN ?
Ans:- CDN(Content Delivery Network will store cache version of the website content in multiple geographical locations across the world also called as point of presence.

8Q What are the different types of databases we do have?
Ans:- 1. Relational Databases:
    - Amazon RDS (MySQL, PostgreSQL, Oracle, SQL Server, MariaDB)
    - Amazon Aurora (MySQL, PostgreSQL)
2. NoSQL Databases:
    - Amazon DynamoDB (key-value, document-oriented)
    - Amazon DocumentDB (document-oriented)
    - Amazon Keyspaces (wide-column store)
3. In-Memory Databases:
    - Amazon ElastiCache (Redis, Memcached)

9Q What is the difference between AWS cloud Trail and AWS Config?
Ans:- AWS CloudTrail:
     - Provides a record of all API calls made within your AWS account, including:
    - Who made the call
    - When the call was made
    - What resources were accessed
    - What actions were taken
AWS Config:
    - Provides a record of the configuration of your AWS resources, including:
    - Resource properties
    - Relationships between resources
    - Configuration changes over time

10Q What is elastic beanstalk?
Ans:- AWS Elastic Beanstalk is a service offered by AWS that allows developers to deploy web applications and services without worrying about the underlying infrastructure.

11Q Difference Between  VPC Peering and Transit Gateway?
Ans:- VPC Peering Connection between 2 VPCs.
Transit gateway is a service that enables you to connect multiple VPCs & Aws Accounts  to single gateways.  which are used for large-scale networks with multiple VPCs, Accounts, on-prem connections.
12Q What is blue/green deployment?
Ans:- Blue/green deployment is a deployment strategy that involves running two identical environments:
1. Blue environment: The current production environment, serving live traffic.
2. Green environment: A duplicate environment, identical to the blue environment, but not yet serving live traffic.

We had an application which is currently running(Blue Env) and that application had new updates. So all the traffic will be hit to load balance, so we will direct the traffic to the already existing application. Once the testing part is done. Then we will route the traffic to the newly deployed application.

13Q What is IAM Roles and Importance in AWS?
Ans:- IAM roles in AWS are a way to grant permissions to AWS resources to perform specific actions without sharing credentials.

Common IAM role types:
1. EC2 instance role: For EC2 instances to access AWS resources.
2. Lambda execution role: For Lambda functions to access AWS resources.
3. S3 bucket role: For S3 buckets to access other AWS resources.
4. Federated role: For external identities to access AWS resources.

14Q What is Lambda in AWS?
Ans:- Lambda is a serverless computing aws service. Serverless means as a user we no need to worry about the
Server provisioning or managing
Hardware Operating
System CPU
These are all taken care of by service providers. Users can use Lambda to Run code in response to change to data in s3 bucket or larger applications.

15Q What is VPC and VPC Peering?
Ans:- VPC is a Network Service in AWS.
VPC is a virtual private cloud is Isolated of the aws cloud where users can launch AWs resources in a virtual private cloud. It enables Ip Address ranges, Subnets & route table configuration & network gateways
 VPC Peering allows two virtual Private clouds to communicate with each other as if they are within the same network. If establish a direct network Connection between VPCs, enabling them to share resource & Services
Real-time prod ex: In My Company we  have two ENvs like production & Development. each having its own VPCs for Security & management purposes. The dev team VPCs need to connect or Access databases which are in prod VPC for testing & integration. By setting up VPC Peering between prod & dev.  The dev team can securely access the required resources in production VPC without Exposing these resources to the public internet.  This allows seamless data transfer & communication between the two ENVs.


16Q What are VPC EndPoints?
Ans:- VPC Endpoints allow you to privately connect your VPC to supported AWS services without needing an internet gateway, NAT device, VPN Connection (or) AWS  Direct connect connection.
Real time Ex:
  We Created a VPC endpoint for S3 in both the development & Production VPC. This way bothe VPCs can access the S3 bucket directly over the Amazon network without using the internet.

17Q Difference Between SG, NACL and NAT GatWay?
Ans:-  Security Groups Controls Inbound and OutBound traffic at the instance level. It controls traffic based on protocols, ports, and IP addresses.
Network Access Control List Controls inbound and outbound traffic at subnet level.
NAT GatWay should be in public subnets because it has internet connectivity. Providing internet access to instances in private subnets without exposing their private IP Address.





 # ############################################## GIT ###############################################################################

1Q What are the types of branching strategies you do follow?
Ans:- we are following feature branching strategies, which are main and integration which are long live branches Main always points to the production comments, and the total code is available in the integration branch So whenever we want to work on Application code, we create branch from the integration we developed, and we check if the pipeline is running smooth or amount. Once it is good, we will raise the PR. If the PR conditions that the code is working, then only we merge. So once marking with the integration, if it’s good, then we will check with the rest of the teams like QA pre-product production So once it is succeeded in the production master points to the committee, so we point the tip and tag as version 1.0 By doing this, whatever the conflict, I will get, I will sit with the developers, and I will do the necessary things.

2Q What is Git and why is it used?
Ans:- Git is a tool for tracking changes in code. It helps developers work together and keep track of every change.

3Q Explain the difference between Git and GitHub?
 Ans:- Git is the tool that tracks changes in code. GitHub is a website where you can store and share your code using Git.

4Q What is a repository in Git?
Ans:- A repository is like a folder for your project. It contains all your project files and the history of changes made to those files.

5Q What does the git init command do?
Ans:- git init creates a new Git repository. It sets up all the necessary files for Git to start tracking changes.

6Q What is a commit in Git?
Ans:- A commit is a snapshot of your project. It records what the project looks like at a certain point in time.

7Q How do you check the status of your repository?
Ans:- Use the git status command. It shows you the changes that have been made and not yet committed.

8Q What does git add do?
Ans:- git add stages changes. It tells Git to include the changes in the next commit.

9Q What is the purpose of git clone?
Ans:- git clone copies a repository from a remote server to your local machine.

10Q What does git pull do?
Ans:- git pull updates your local repository with changes from a remote repository.

11Q What is a branch in Git?
Ans:- A branch is like a separate line of development. It lets you work on new features without changing the main codebase.

12Q Git Pull  vs Git Fetch?
Ans:- Git Pull is a combination of git fetch + git merge. git pull will directly copy code from remote repo to local repo without asking what changes  it is to merge.
Git Fetch ask the review what  changes  to merge the local repo.

13Q Git Merge vs Git Rebase?
Ans:- git merge create extra commit that is called merge commit. merge will preserve the complete history, like Chain structure. If a branch is developed by multiple developers (or) persons we can go with git merge because it maintains the commit history.
Git Rebase does not create any extra commits. It rewrites history. It will not preserve the history.
If a branch is developed by one developer (or) person we can go with git rebase.

14Q What is Cherry picking?

Ans:- We have multiple commits like R1, R2 and R3  in the Feature branch but we don't want to merge all into main. We need to take one Specific commit Id & merge into the main branch called Cherry Picking.

git Cherry-pick commit Id
15 Q Git Tag?
Ans:- Git tag is a reference to a specific commit in Cit.
16Q Git Stash?
Ans:- Git  stash is temporary storage for your  change or It hides the things. If you want keep your changes sure to commit (or) re apply Stash
17Q Git revert?
Ans:- Going back where it started
git revert commit Id
                                           
                                           

# ##################################################### Terraform ######################################################################

1Q What is terraform and what are the advantages?
Ans:- Terraform  is an infrastructure automation tool. It allows users to define and provision infra using declarative configuration language. Which means no order preference when we write a terraform file. which is mainly used to deploy/provision our cloud infrastructure. The main advantages terraform is automation dry checks, validation of code, with the help of state file or TF. We can deploy another infra.

2Q how to change a configuration file, which is already created using a terraform?
Ans:- Terraform import

3Q  What is the use case of Terraform statefile.tf And where do you save it?
Ans:- Terraform.tfstate having full details of current state. Terraform will check the current state , if the current state is equal to the desired state then it will not take any actions.if unexpectedly state file delete/lose we cannot get back if we store in local machine so for this purpose we do our state file store in aws s3 bucket and we can lock the state file using dynamoDB table. 
Statefile locking details in provider.tf

backend "s3" {
    bucket = "devopsrk-remote-state"
    key    = "backend"
    region = "us-east-1"
    dynamodb_table = "devopsrk-locking"
  }

4Q why state files are not safe to keep on a local machine?
Ans:- Basically the state file will contain very critical information. So keeping such files under a locking system is always the best practice.We need a central state file to check whether the infra exists or not. If we keep our state file  in local machine
collaboration:
Terraform will have no idea about the infra created, if multiple persons are working on same infra, it will try to create duplicate and errors will come
Security:
Tfstate is crucial, if you keep it in local it may be deleted or updated by mistake so we use S3 Bucket for Remotestate and locking by dynamoDB.

5Q What are the main features in terraform?
Ans:-  
Terraform can manage infrastructure in multiple cloud platforms and providers. 
Terraform uses HashiCorp language which is user readable.
Automatic dependency management.
We have super feature modules in terraform.
Its declarative way of create infrastructure.

6Q What are the different types of terraform modules?
Ans:- Terraform Modules are works on DRY principle (re-usable), encapsulated units of infrastructure code. They can be called multiple times with different inputs promoting code reusability.There are 3 modules and we are using VPC,SG,EC2 modules.
Route modules 
Route modules which consists of all resources defined in the TF file which is the main working directory. Example it contains main.Tf and  variable.tf and outputs.tf. The route modules will be considered as the main configuration for your entire infra project.
Publish modules
A published module in Terraform typically refers to a module that has been shared and made available for use by others in the Terraform community. There are several platforms where Terraform modules can be published, including:
Terraform Registry
Public Version Control Repositories (e.g., GitHub)
Private Module Registries
Child Modules
A Terraform module (usually the root module of a configuration) can call other modules to include their resources in the configuration. A module that has been called by another module is often referred to as a child module.

7Q Have you heard of remote backend?
Ans:- - remote backend is a place where we store all our TF state files which can be shared to other developers of infrastructure. Ex- AWS S3 bucket for  remote storage and locked with DynamoDB.

8Q How do you create multiple ENV with terraform?
Ans:- we have 3 ways to create multiple ENVs in terraform.
tfvars
workspaces
different repos for multi ENVs
Using tsvar files, we have maintain  separate tfvar files for diff env like prod.tfvars / dev.tfvars/Qa,tfvars
Terraform workspace, we can use single code for multiple ENVs. it allows us to manage separate files for each workspace. Each workspace has its own state file. It is enabled to maintain separate configuration for different ENV like Dev,Pod.
 ex: env/dev/workspace or env/prod/workspace
Create new workspace
              terraform workspace new Dev/Prod/Qa
List the workspaces
              terraform workspace list
 Moving workspaces
               terraform workspace select dev/prod/qa

9Q What is Taint in Terraform?
Ans:- Terraform taint command informs that particular object has become damaged or degraded. Terraform will propose to replace it in the next plan.
terraform -replace
10Q What Terraform Provider?
Ans:- Terraform providers are plugins that allow Terraform to manage resources in various cloud and on-premises environments. 
Some popular Terraform providers include:
AWS Provider: Manage AWS resources like EC2, S3, RDS, etc.
VMware Provider: Manage VMware resources like vSphere, vCenter, etc.
Kubernetes Provider: Manage Kubernetes resources like Deployments, Services, Pods, etc.
 Docker Provider: Manage Docker resources like Containers, Images, Networks, etc.
Cloudflare Provider: Manage Cloudflare resources like DNS, Load Balancing, etc.
GitHub Provider: Manage GitHub resources like Repositories, Users, Teams, etc.

11Q What is Taint in Terraform?
Ans:- Terraform taint command informs that particular object has become damaged or degraded. Terraform will propose to replace it in the next plan.
terraform -replace

12Q What are Terraform Locals?
Ans:- Terraform locals are just like variables but they have some extra capabilities. You can keep functions and expressions inside locals and use them.

13Q Terraform init, apply and plan?
Ans:- 1. terraform init:
    - Initialises the Terraform working directory
    - Downloads and install required providers
    - Sets up the Terraform backend (if configured)
2. terraform plan:
    - Creates an execution plan for the desired infrastructure changes
    - Shows the expected changes and resources to be created/updated/deleted
    - Allows for review and verification of the planned changes
3. terraform apply:
    - Applies the planned changes to the infrastructure
    - Creates, updates, or deletes resources as specified in the plan
    - Outputs the results and any relevant information

14Q What are data sources and outputs in terraform?
Ans: Data sources it is useful to query the data dynamically from Providers.
Ex: we can take ami id dynamically using data sources because of aws eevrey week updated the ami patches so we get dynamically using Owner details ,Root device type and Virtualization.
Outputs: Terraform output is used to get the information from creatary resources. We can get the output information at the output block or terminal.
Ex: amiid,vpc id, public and private ids.

                                       
 # ############################################## Jenkins #############################################################################
1Q How do you store Jenkins secrets?
Ans:- - Jenkins credentials or any third-party tools, such as AWS secrets, manager or Google cloud key management or Azure key or HashiCorp vault .

2Q What are shared modules in Jenkins?
Ans:- - shared modules in Jenkins refers to collection of reusable and resource that can be shared across multiple Jenkins jobs.

3Q What is the difference between freestyle project and pipeline project?
Ans:-  Freestyle Project is traditional way of approach to Building and Testing, where we do things manually through the web interface
pipeline project is the way of approach that uses cod usually in form of Jenkins or integrating git to automate steps to software delivery process

4Q What are Jenkins plug-in?
Ans:-  Jenkins plug-ins are additional software components that extend the functionality of the software they are used to integrate with other software and to automate various tasks. Some examples: ansi colour plug-in for output getting colours,GIT plug-in, docker pipeline plug-in, AWS plug-in, Sónar Q plug-in, Maven plug-in and Blue Ocean plug-in for creating visualisation pipeline, Jenkins Notification Plug-in like Email Extension, slack and Teams. Etc

5Q How can you test and destroy the Jenkins pipeline?
Ans:- we can use Jenkins bridal features to validate the syntax and structure of the Jenkins file Breakdown the pipeline stages and check independently to isolate and identify problems Log reviews error to identify the warning in other issues

6Q How can you manage to build artefacts in Jenkins?
Ans:- Jenkins provides several options for managing build artefacts, including the use of the artefacts post build actions which allows you to archive files generated by the build . You can also use the copy artefact plug-in to copy, build artefacts from one job to another 

7Q Concept Of Jenkins Master- Slave or Master-Node?
Ans:- Jenkins is based on distributed architecture called master-slave.
Master is the central control unit of Jenkins ENV. It has several responsibilities like Job Scheduling, dispatching jobs, monitoring slaves and Job config.
Jenkins master assigns the workload to each of its slave nodes using TCP/IP Protocol.

8Q steps to configure webhook triggers
webbook (Connection blw git & jenkins)
git repo webbook setting
git→ jenkins webhook configure Payload URL is
Ex: http://18-232-76-9:8080/github-webbook
content type- json/application 
If the developer pushes the code to git, then we want the pipeline to run automatically

9Q Steps to configure agent Server in jenkins
jenkins Dashboard-> Manage jenkins-> Nodes..
we need to give name like AGENT-1
We can provide Number of Executors 5. means We can ram at a time 5 jobs.
Setup remote root directory. home/centos/agent-jenkins
Provide Labels name as AGENT-1
Setup Launch methode via ssh & need to give-host agent IP
Add Credentials and Save it
Node successfully added
Need to provide agent details in Groovy Script
agent {
node {
   label "AGENT-1"
}
}
 Then The Jenkins looks at his agent details and it will run on that mentioned Agent only. I mean it works by agent.
Need to install java in Agent server.

10Q What is a build node ?
Ans:-  Jenkins build note is a machine that Jenkins uses to execute build job . It can be a machine or virtual machine, or it can be run on premises or on cloud.

11Q What are Jenkins shared libraries?
Ans: jenkins shared library treats your pipeline as a library, use it wherever you want. I added in jenkins system configuration, location and name of the library
nodejs vm/java vm/python vm/go vm is a centralised pipeline, we need to send parameters.In my project we have used a shared library for node js java and python applications CICD.we are written groovy scripts based on the application. We used jenkins code in 100+ projects. If we have a change in code we need to change 100+ projects pipeline so avoid this by using best practices like using jenkins-shared-libraries. We are importing the jenkins shared library in my project and setting up the details in the jenkins pipeline.



# ############################################## Ansible ###############################################################################

1Q What is Ansible and what is it used for?
Ans:- Ansible is an open-source automation tool used for configuration management, application deployment, task automation, and orchestration. It simplifies IT operations by automating repetitive tasks.

2Q Explain the difference between Ansible and other configuration management tools like Chef or Puppet?
Ans:- Ansible uses an agentless architecture, relying on SSH and Python to execute tasks on remote servers. Ansible is push based Architecture.
Chef and Puppet use an agent-based approach where agents need to be installed on managed nodes. Chef and Puppet are pull based architects. We will configure an agent to check every 1 hour.

3Q What are Ansible playbooks?
Ans:- Ansible playbooks are YAML files that define a set of tasks to be executed. They automate configurations, deployments, and orchestration of tasks across managed nodes.

4Q How do you run an Ansible playbook?
Ans:- You run an Ansible playbook using the ansible-playbook command followed by the playbook filename. For example, ansible-playbook site.yml.

5Q What is an Ansible role?
Ans:- Roles are like Don't Repeat Yourself(DRY). It will have proper directory structure. We can share roles with other users.
Ansible role is a way to organise playbooks and other files in a reusable structure. It encapsulates tasks, variables, templates, and files into a directory structure.

6Q How do you install Ansible on your local machine?
Ans:- Ansible can be installed using package managers like apt, yum, or brew depending on your operating system. For example, sudo apt-get install ansible on Ubuntu.

7Q What is an inventory and Dynamic inventory files in Ansible?
Ans:- An inventory file in Ansible lists the IP addresses or hostnames of managed nodes (servers) that Ansible will work with. It defines the targets for Ansible playbooks and ad-hoc commands.
Dynamic Inventory files allow Ansible to fetch a real-time list of hosts from the External System.
8Q Explain the difference between Ansible ad-hoc commands and playbooks?
Ans:- Ad-hoc commands are run from the command-line to perform quick tasks on remote nodes (ansible command). Playbooks are YAML files that provide a more structured and reusable way to automate tasks.

9Q Ansible common?
Ans:- Common also a ansible role. Where you can keep common things between all the roles and call it whenever it is required. Like files, tasks , web etc.

10Q How does Ansible handle idempotency?
Ans:- Providing the same results irrespective of the number of executions is called Idempotency. If you run a program multiple times. That can create something multiple times. Even if you run your program infinite times. It should not create any damage.

11Q What is the Ansible Galaxy?
Ans:- Ansible Galaxy is a website and command-line tool for finding, reusing, and sharing Ansible roles. It provides a repository of community-contributed roles that can be used to extend Ansible functionality.

12Q Difference between Ansible command and Ansible shell module?
Ans:- command The command module won't respect target machine shell variables and environments. It is running the command from outside the server.
Shell It is like you logged inside a target machine directly and running commands. Due to the inside logged target machine shell module slower than command. 

13Q What are Ansible handlers?
Ans:- Ansible handles are used for when change is made on running a machine, We need to restart the service so the handler notifies us when a change has occurred otherwise we no longer need to restart un-necessary.

14Q Most commonly used ansible modules in your project?
Ans:- For external modules 
ansible.builtin.Service:
		State:present
		enabled: yes.
		enabled: yes.
For External module.
ansible.builtin.Shell:
ansible. Builtin.command:

ansible.builtin.Pacakege:
name: mongodb-on
For Uger Creation module
ansible.builtin.user:
		name: usennam.
For Create dir module
ansible.builtin.file:
		path:
		State: directory (otherwise it will take as file)
For downloading the File module.
ansible.builtin.get.Urls
		Dest:
For Extracting the File module,
ansible, builtin. unarchive
		src
		dest
		remote_src: yes (File already available) in remote machine
	
For copy the file
ansible.builtin.copy:
For delete the dir.
ansible.builtin.file:
		state:absent.
For replace the hostname connections
ansible.builtin.replace
		Path:
		reggxp: replace


15Q What is Ansible Vault and its use?
Ans:- Ansible Vault is a feature that allows you to keep sensitive data, such as passwords and encryption keys, encrypted and secure. It uses AES256 encryption to protect your data.
1. ansible-vault create aws_cred.yaml: a new Ansible Vault file aws_cred.yaml.
2. ansible-vault edit aws_cred.yaml: edits an existing Ansible Vault file.
3. ansible-vault view aws_cred.yaml: views the contents of an Ansible Vault file.
4. ansible-vault encrypt aws_cred.yaml: encrypts a file using Ansible Vault.
5. ansible-vault decrypt aws_cred.yaml:decrypts a file using Ansible Vault.
6. ansible-vault rekey aws_cred.yaml: changes the password existing Ansible Vault.



# ############################################## Docker ###############################################################################

1Q What is Docker and why is it used?
Ans:- Docker is a platform that allows you to package, distribute, and run applications in containers. It's used for creating consistent environments across development, testing, and production.

2Q What is a Docker image and a Docker container?
Ans:-
Docker image is a read-only template that contains the application and its dependencies.
A Docker container is a runnable instance of a Docker image. container is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including code, runtime, libraries, and dependencies.

3Q What is Docker Hub?
Ans:- Docker Hub is a cloud-based registry service that allows you to store and share Docker images publicly or privately. It's a repository of Docker images maintained by Docker.

4Q What is a Dockerfile?
Ans:- A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. It's used to build Docker images automatically. A declarative way of creating our own image.

5Q Explain the concept of Docker volumes?
Ans:- Containers are ephemeral/temporary. If the container is removed, by  default the data is removed so we used docker volumes for store/save/persist data which is generated by docker container using Docker volumes. Even if the container is removed we have the generated data on volumes.

6Q What are Docker networks and why are they used?
Ans:- Docker networks allow containers to communicate with each other and with other non-containerized devices on the same network. Docker containers cannot communicate with each other if they use docker default networks. So we can create our own network for our containers.

7Q Difference  between CMD vs  ENTRYPOINT in Docker?
Ans:- 
CMD command can be Overridden by  Another command at runtime
Ex:- CMD Hello RK" Hellopriya. "Hello Priya” => Hello Priya
ENTRY POINT Cannot be Overridden. If you try to do so, the command you are entering at runtime will go & append to ENTRYPOINT.
We can use both combinations for better results.
 you can use CMD instruction to supply arguments to ENTRYPOINT. Users can always Override CMD arguments from run time.

8Q EXPOSE Instruction?
Ans:-  Which is used for Information purposes only. The EXPOSE instruction informs Docker that the container listens on the Specified network Ports at runtime.

9Q COPY vs ADD?
Ans:- Copy which is used to our local files to Container.
Both are used to copy the files from local to image but ADD have 2 Extra capabilities.

10Q  Docker Architect?
Ans:- How the system receiving the request and sending a response to them is  called Architecture. Docker Architecture having 

docker Execution flow
Command ex: docker run nginx
	1. docker shell/ docker command send a request to docker daemon
	2. docker engine receives the request
	3. it will check whether image is available in local or not
	4. if available it will create container and show the response in client
	5. if not available, it will pull from docker central hub, keep it in local.
	6. create container and response to client

11Q multi-stage Build in Docker?
Ans:- Multistage builds in Docker allow you to Create more efficient Dockerbiles by reducing image size and complexity. This technique involves using multiple FROM Statements in a Single Dockerfile to build different Stages of an application and then copying Only necessary artefacts from one stage to another.This approach helps to keep the final image size Smaller by discarding unnecessary build dependencies and intermediate files
 Ex: This approach is used mainly for java applications. Generally we take jar files on to another stage. Where we will have only a jdk or jre environment that can reduce the image size because we don't need maven in the runtime environment.

12Q: What are the best practices of docker used in your project?
Ans: Best Practices
1. use official images
2. reduce image size by using bare minimum OS like alpine, disto, core os, etc.
3. use multi stage builds
4. use docker volumes to persist the data
5. use custom network to isolate containers from other projects

13Q Difference  between CMD vs  ENTRYPOINT in Docker?
Ans:- CMD command can be Overridden by  Another command at runtime
Ex:- CMD Hello RK" Hellopriya. "Hello Priya” => Hello Priya
ENTRY POINT Cannot be Overridden. If you try to do so, the command you are entering at runtime will go & append to ENTRYPOINT.
We can use both combinations for better results.
 you can use CMD instruction to supply arguments to ENTRYPOINT. Users can always Override CMD arguments from run time.

14Q EXPOSE Instruction?
Ans:-  Which is used for Information purposes only. The EXPOSE instruction informs Docker that the container listens on the Specified network Ports at runtime.

15Q COPY vs ADD?
Ans:- Copy which is used to our local files to Container.
Both are used to copy the files from local to image but ADD have 2 Extra capabilities.
It can directly download files from the internet.
It can directly untar the tar files

16Q  ARG VS ENV?
ARG can only be used inside Dockerfile and only in build time.
ENV can be used both in the build time & run time. Assign the values of ARG to ENV variables so that you can access them inside the container as well.
ARG instruction can be used before FROM instruction to provide values to FROM instruction

17Q Difference between docker swarm and kubernetes?
Ans:- Docker Swarm and Kubernetes are both container orchestration tools, but they have different design principles, architecture, and use cases. 
Docker Swarm Dis-Advances:
Docker Swarm doesn't have TLS Secrets, RBAC, State Full Sets, Health Probs and ENV Secrets.

18Q Write a Dockerfile for an Nginx web server?
Ans:- 
FROM nginx:latest   # Use the official Nginx image as the base
WORKDIR /usr/share/nginx/html  # Set the working directory 
COPY . /usr/share/nginx/html  # Copy the static website files from the current directory
EXPOSE 80  # Expose port 80 for HTTP traffic
CMD ["nginx", "-g", "daemon off;"]   # Run Nginx when the container starts
19Q Docker Layers ?
base image
creates container out of first instruction, intermediate container
 runs second instruction in the container, creates image out of this
creates a container out of 2 instructions.
runs the command in the intermediate container. creates image out of these 3


20Q Difference between DockerFile And Docker ComposeFile?
Ans:- Dockerfile:A Dockerfile is a text file that contains instructions for building a Docker image. It specifies the base image, copies files, sets environment variables, exposes ports, and defines commands to run during the build process.
       Key elements in a Dockerfile:
- FROM specifies the base image
- COPY copies files from the host machine to the container
- ENV sets environment variables
- EXPOSE exposed ports
- CMD defines the default command to run when the container starts
Docker Compose file (docker-compose.yml):A Docker Compose file is a YAML file that defines and configures multiple containers, networks, and volumes for an application. It allows you to define the services, their dependencies, and the overall application structure.



# ############################################## Kubernetes ###########################################################################


1Q What is Kubernetes and why is it used?
Ans:- Kubernetes is an open-source platform for automating the deployment, scaling, and management of containerized applications. It helps in managing containerized applications across multiple hosts.

2Q What is a container?
Ans:- A container is a lightweight, executable package of software that includes everything needed to run a piece of software, including code, runtime, libraries, and dependencies.

3Q Explain the difference between Kubernetes and Docker?
Ans:- Docker is a platform for building and running containers, while Kubernetes is a container orchestration platform that manages the deployment and scaling of containers.

4Q What are Pods in Kubernetes?
Ans:- Pods are the smallest and simplest Kubernetes objects. They represent a single instance of a running process in the cluster, which may consist of one or more containers that share storage and network resources.

5Q How do you create a Pod in Kubernetes?
Ans:- You create a Pod by defining a Pod manifest file in YAML format, which specifies the Pod's configuration, such as containers, volumes, and metadata. Then, you apply this manifest file using kubectl apply -f pod.yaml.

6Q What is a Deployment in Kubernetes?
Ans:- A Deployment in Kubernetes manages a set of identical Pods, ensuring that the desired number of Pods is running and handling updates and rollbacks.

7Q How do you create a Deployment in Kubernetes?
Ans:- You create a Deployment by defining a Deployment manifest file in YAML format, which specifies the desired state of the Deployment, including the number of replicas and the Pod template. You then apply this manifest file using kubectl apply -f deployment.yaml.

8Q What is a Service in Kubernetes?
Ans:- A Service in Kubernetes is an abstraction that defines a logical set of Pods and a policy by which to access them. It provides a stable endpoint for connecting to the Pods.


9Q How do you expose a Deployment as a Service in Kubernetes?
Ans:- You expose a Deployment by creating a Service manifest file in YAML format, which specifies the type of Service (e.g., ClusterIP, NodePort, LoadBalancer) and selects the Pods to expose. You apply this manifest file using kubectl apply -f service.yaml.



10Q What is the role of kubectl in Kubernetes?
Ans:- kubectl is the command-line tool used to interact with Kubernetes clusters. It allows you to deploy and manage applications, inspect and manage cluster resources, and view logs and troubleshooting information.

11Q What is a Namespace in Kubernetes?
Ans:- A Namespace in Kubernetes provides a way to divide cluster resources among multiple users or projects. It helps organize and isolate resources within a cluster.

12Q How do you scale a Deployment in Kubernetes?
Ans:- You scale a Deployment by updating the replicas field in the Deployment manifest file to the desired number of replicas (e.g., kubectl scale deployment/myapp-deployment --replicas=3).

13Q What is a ConfigMap in Kubernetes?
Ans:-  A ConfigMap in Kubernetes is an API object used to store non-sensitive configuration data in key-value pairs. It can be used to decouple configuration from Pods and containers.

14Q How do you manage application logs in Kubernetes?
Ans:- Application logs in Kubernetes can be accessed using kubectl logs command followed by the Pod name and optional container name. For example, kubectl logs mypod.

15Q What is a Node in Kubernetes?
Ans:- A Node in Kubernetes is a worker machine in the cluster. It may be a physical machine or a virtual machine, and it runs Pods managed by the Kubernetes control plane.

16Q What are Labels and Selectors in Kubernetes?
Ans:- Labels are key-value pairs attached to Kubernetes objects (e.g., Pods, Services) for identification and grouping. Selectors are used to filter and select objects based on labels.

17Q How does Kubernetes handle container restarts?
Ans:- Kubernetes automatically restarts containers that fail or exit, based on the Pod's restartPolicy (default is Always). It ensures that the desired state of the Pod (defined in the Deployment or Pod manifest) is maintained

18Q What is a Persistent Volume (PV) in Kubernetes?
Ans:-  A Persistent Volume in Kubernetes is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using StorageClasses. It provides storage resources for Pods.


19Q How do you upgrade Kubernetes cluster components?
Ans:-  Kubernetes cluster components (e.g., API server, Controller Manager, Scheduler) can be upgraded by updating the Kubernetes version in a controlled manner, following the upgrade instructions provided by the Kubernetes documentation.

20Q What is the difference between a StatefulSet and a Deployment in Kubernetes?
Ans:-  A StatefulSet is used for stateful applications that require stable, unique network identifiers and persistent storage. It manages Pods that are not interchangeable, whereas a Deployment is used for stateless applications and manages interchangeable Pods.


# ############################################## Monitorning Tools #####################################################################


# Prometheus

Prometheus mostly depents on Time Series DataBase(TSDB).
Prometheus connected to other servers to get a metrics and every server need to install or have node exporter. 
Prometheus connected to node exporters and collect the data and stored in Timebase DB.
prometeus works on 9090 port.

node exporter running continously and getting collecting metrics from node.
we can configure or add new targets to prometheus node exporter(vm only not containers) and configuration details in prometeus.yaml file. Prometheus hit default evry 25 seconds it will collect the metrics from node exporter and saved in time base DB.

    
# scrape_configs:
     - targets: ["localhost:9090"]

- job name: "node-exporter"
        static_configs:
        -  targets: ["172.31.83.66:9100]
- job_name: "prometheus"
    static_configs:
    - targets: ["localhost:9090"]

- job name: "ec2-scrapping"
    ec2-sd-configs:
    - region: us-east-1
        port: 9100
        filters:
    - name:"tag:Monitoring" ## active server
        values:
        - true

In ec2-sd-config we can add scrapping concept. prometheus monitoring entier region active servers. If we use filters we can configure tags in ec2 server like monitoring is true. so that particular one only prometheus collecting mentrics.

        - job name: "ec2-scrapping"
            ec2-sd-configs:
            - region: us-east-1
                port: 9100
                filters:
            - name:"tag:Monitoring" ## active server
                values:
                - true


# Grafana
Prometheus graphs are nor user friendy so we can use Grafana for that.
It can get from multiple soureces . prometeus one of the sourece to grafana.
Need to download grafana in prometheus server for better results i.e no lag.

# Dynamic Scrapping:-
In cloud and dyanmic invernments IP Address are temporary mens all ways change.
