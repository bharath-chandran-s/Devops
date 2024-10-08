Requirements
 - Installed minikube.
 - Installed kubectl command-line tool.

1. Install Argo CD

   $ kubectl create namespace argocd
   $ kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


2. Change Argo CD Service From ClusterIP To NodePort

   $ kubectl edit svc argocd-server -n argocd
   
3. Copy The URL For Argo CD

   $ minikube service list -n argocd
   
     ![Image reference](Argo CD/Screenshot from 2024-10-08 23-15-07.png)



4. View The Argo CD Login Page On The Browser:

     ![Image reference](Argo CD/Screenshot from 2024-10-08 23-16-50.png)
     


5. Get the Password From the Secrets:
    
    $ kubectl get secrets -n argocd

      NAME                          TYPE     DATA   AGE
      argocd-initial-admin-secret   Opaque   1      16m

    - Edit the secret to copy the encoded password

                 $ kubectl edit secrets -n argocd argocd-initial-admin-secret

    - Decode the password using the below command

                 $ echo <paste the password here> | base64 --decode

6. Login with the username and password:

     - Username: admin
     - Password: 
