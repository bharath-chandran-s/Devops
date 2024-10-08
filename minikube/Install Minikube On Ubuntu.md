Install Docker On Ubuntu 


1. Add Docker Official GPG Key

$ sudo apt update
$ sudo apt install ca-certificates curl -y
$ sudo install -m 0755 -d /etc/apt/keyrings
$ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
$ sudo chmod a+r /etc/apt/keyrings/docker.asc

2. Add Docker Official APT Repository

$ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

3. Install Docker on Ubuntu 24.04

$ sudo apt update
$ sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

4. Once docker and its dependencies are installed then add your local user to docker group so that local user can run docker command with sudo.

$ sudo usermod -aG docker $USER
$ newgrep docker
$ docker --version


5. Verify the docker service status

$ systemctl status docker





Install Minikube On Ubuntu 

1. Download the latest Minikube binary file using curl:

   $ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

2.  Install the downloaded Minikube binary file:

    $ sudo install minikube-linux-amd64 /usr/local/bin/minikube

3. Install Kubectl Utility

    $ curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

4. Once kubectl is downloaded then set the executable permissions on kubectl binary and move it to the path /usr/local/bin

   $ chmod +x kubectl
   $ sudo mv kubectl /usr/local/bin/


    
5. Verify that Minikube is successfully installed by checking its version:

   $ minikube version

6. Run the following command to check the status of Minikube:

   $ minikube status
   $ minikube start


