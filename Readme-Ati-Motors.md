                                             Part 1

1. Fork the given repo:
     * This can be done by opening the given link in the assignment and clicking the "Fork" option on the right. This will prompt a fork page and you can give the desired name to the repo.
      * This will create a new repo in your GitHub account with the same contents as in the assignment repo

2. Jenkins:
      * Before starting with Jenkins, install Jenkins by downloading the war file from Google
      * Open CMD and go to your downloads directory, using the dir command in Windows and the cd command in Linux OS
     and run the "java -jar jenkins. war", if you already used Jenkins on your system, you can now browse it on http://localhost:8080
      * If this is the first time setting it up, store the password it displays and browse to the above URL mentioned, use the password to set up your account and install the required dependencies
      * But as the assignment said to use Jenkins on port 3000, the simple way to do this is by running "java -jar jenkins. war --httpPort=3000", this will open Jenkins on port 3000
      * We need to run the app on port 3004, so go to the Jenkinsfile in the GitHub repo and update the port from 3000 to 3004.
      * Now back in Jenkins, click on "New item", select pipeline, give it a name, and click on OK.
      * Now scroll down and go to the pipeline section, select "pipeline from SCM", select Git, provide the repo URL, and configure your credentials.
      * provide the branch name where the code is present and the directory details in the script path.
      * Save the pipeline.
      * Before running the pipeline, make sure your docker daemon is running, this can be done by installing the docker desktop application and running it.
      * Click on the pipeline and build now option.
      * This will run the pipeline and host the app locally on the host 3004, and you can access it using HTTP://localhost:3004

---------------------------------------------------------------------------------------------------------
                                            Part 2
                                            
1. Creating a pipeline to pull images and build them
     * Create a Jenkinsfile to write the declarative script, which will help us to pull images and build them as containers using Docker
     * The jenkinsfile can be found in this repo at the folder named "Rupesh Files"
     * In the file, after the basic syntax, you will mention the registry credentials provided in the assignment file, this can be done using the "registryCredentials" variable, and provide the credentials in the next lines using the db_user and db_password
     * Next up, we have to configure the stage and steps to perform the image pull and build.
     * In the first stage, you can mention, the names of the images that need to be pulled and use the latest tag to pull their latest version of images
     * After this, these images can be built into containers using the docker build command.

-----------------------------------------------------------------------------------------------------------
                                                Part 3

1. Setup a K3s cluster
    * You can set the k3s cluster on a server/VM of your choice, create an Amazon Linux VM, and log in to it using ssh, before you set up k3s cluster, you can run the "sudo apt update" to do the updates on your system.
    * Then you can run "curl -sfL https://get.k3s.io | sh", to install k3s on your server.

2. Kubernetes manifest files
   *  you need to create the Kubernetes manifest files that are yaml files for your pods (fleet_manager, PostgreSQL, Nginx, Redis, MongoDB, Grafana, and local docker registry.)
   *  You can deploy these files using the command "Kubernetes apply -f fleet_manager.yaml", "kubernetes apply -f PostgreSQL.yaml", like this for each file.
   *  you can also verify this using "kubectl get pods".
   *  The YAML files are present in the repo in the folder named "Rupesh files"
     
