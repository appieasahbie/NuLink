\# NuLink  Phase 2 Worker  update to version 0.2.0
 
 
 
### List containers in tabular structure

    docker ps
    
    
<img width="733" alt="1" src="https://user-images.githubusercontent.com/108979536/197086125-c13a6828-b64f-4216-b1d4-d054de1cb924.png">


you wil get results like this 

<img width="487" alt="wq" src="https://user-images.githubusercontent.com/108979536/197084484-4bad996d-e0a7-42e8-8cf6-1ea142efc5bb.png">


copy the container id and use this command :

   <img width="739" alt="2" src="https://user-images.githubusercontent.com/108979536/197084630-a3a4711b-be58-4df4-ab38-725df08e9498.png">
 
 ### 1-Stop the running node in Docker by running this two commands one bby one
 
     docker kill <container ID>
     
     docker rm <container ID>
     
 Example: 
 
     docker kill he8303xdede03e
     
    
  <img width="368" alt="4" src="https://user-images.githubusercontent.com/108979536/197085119-1eda3329-25e1-44cc-a87b-9576cdbf19c7.png">


     docker rm he8303xdede03e
     
  <img width="353" alt="5" src="https://user-images.githubusercontent.com/108979536/197085197-eedcea19-95aa-426a-938c-13239f1b7ca4.png">


### Pull the latest NuLink image :

     docker pull nulink/nulink:latest
     
  <img width="518" alt="6" src="https://user-images.githubusercontent.com/108979536/197085395-45e47cee-d8a6-41ae-9906-607da3768c61.png">


     
###  Re-launch the worker node :


     docker run --restart on-failure -d \
     --name ursula \
     -p 9151:9151 \
     -v /root/nulink:/code \
     -v /root/nulink:/home/circleci/.local/share/nulink \
     -e NULINK_KEYSTORE_PASSWORD \
     -e NULINK_OPERATOR_ETH_PASSWORD \
     nulink/nulink nulink ursula run --no-block-until-ready
     
     
### Check the logs :

    docker logs -f ursula
    
    
<img width="410" alt="swsk" src="https://user-images.githubusercontent.com/108979536/198828436-472c09a6-0081-4401-88a7-65980b1c7c6f.png">



# Make sure putting a small amount of BNB(test) to the worker account for sending one confirmation transaction.

 ### END   
