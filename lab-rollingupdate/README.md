  ## Rolling update
   
   ```shell script
     k create -f curl.yaml -n kube-public  # to set up curl command
     k create -f frontend.yaml
     k create -f webapp-service.yaml    
     chmod +x curl-test.sh
     ./curl-test.sh
     #kubectl port-forward service/webapp-service 31717:8080 --address='0.0.0.0'
     # ouvrir un second shell pour modifier l'objet deployment k8s directement
    ./curl-test.sh
     k edit deploy  frontend 
     kubectl rollout status deployment/frontend  
     kubectl rollout history deployment/frontend
    :
   ```