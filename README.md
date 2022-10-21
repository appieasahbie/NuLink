# `•.¸¸.•´´¯`••._.•   🎀  𝒩𝓊𝐿𝒾𝓃𝓀  🎀   •._.••`¯´´•.¸¸.•`



![nulink`](https://user-images.githubusercontent.com/108979536/195450969-3f145a92-4951-4c70-a581-62675af7841f.png)





# Minimum Hardware Requirement :
   + Ubuntu 20.04
    
   + 4 GB RAM
    
   + 30 GB HDD
   
   + 2 CPU
   
# Officiel Links
 + Nulink Telegram : https://t.me/NuLink2021
 + Nulink Discord Channel : https://discord.gg/NAcsqGAp
 
# Introduction to NULINK

![nuu](https://user-images.githubusercontent.com/108979536/195452270-aa65e940-d482-4c60-9c65-9fdc53d35c24.png)


 NuLink network is a decentralized solution for privacy-preserving applications developers to implement best practices and best of breed security and privacy. The    NuLink platform provides endpoint encryption and cryptographic access control. Sensitive user data can be securely shared from any user platform to cloud or decentralized storage and access to that data is granted automatically by policy in Proxy Re-Encryption or Attribute-Based Encryption. For the data user on the other side, Zero-Knowledge Proof can help them verify the data source. In more advanced privacy-preserving use cases, NuLink uses Fully Homomorphic Encryption to customize enterprise-level data computation services.
 
 
# Intallation One time  (automatic)
 + You can setup your Nulink testnet in few minutes by using automated script below. It will prompt you to input your wallet name!
 
 
             wget -q -O Nulink.sh https://raw.githubusercontent.com/appieasahbie/Nulink/main/Nulink.sh && chmod +x Nulink.sh && sudo /bin/bash Nulink.sh
  
# (optional) [Migrate your validator to another machine](https://github.com/appieasahbie/Nulink-Migrate)  


# NuLink node installation 

 +Open poorts and ssh
 
     sudo ufw allow ssh
     sudo ufw allow 9151
     sudo ufw enable
   
### After running auto install command you will see output that your keystore file is saved in /root/geth-linux-amd64-1.10.24-837382a7/keystore/UTC-XXXXX Copy the keystore file to Nulink Directory that we just created   
   
# NuLink Worker Installation:

     cp xxxxxxxxxxxxxxxxxxxxx /root/nulink
     
Remplace “xxxxxxxxxxx” by your Path of the “secret key file” like pictyre
![path](https://user-images.githubusercontent.com/108979536/195454279-0ced09f2-0d11-41a5-800c-25b94cc64eb5.png)

     
 And type this command :
 
     chmod -R 777 /root/nulink
must show like this 

<img width="435" alt="bnn" src="https://user-images.githubusercontent.com/108979536/195454515-dcde21a3-6dd1-4ffe-b14b-3c72905c8707.png">

# NuLink Worker Initialization and Running

   Export Node Environment Variables

       export NULINK_KEYSTORE_PASSWORD=xxxxxxxxxxxx

Replace xxxxxxxxxx with your own password and save it 

and this (use the same password as above )

      export NULINK_OPERATOR_ETH_PASSWORD=xxxxxxxxxx
      
Password used to unlock the keystore file of Worker account, you should have set it up when you create the Worker account using Geth or other sources. please use the same password for both commands

# Run Node via Docker


please Replace xxxxxxxx and ggggggggggg with your own codes and don`t forget to make a backup for your nulink files geth an nulink

      
    docker run -it --rm \
    -p 9151:9151 \
    -v /root/nulink:/code \
    -v /root/nulink:/home/circleci/.local/share/nulink \
    -e NULINK_KEYSTORE_PASSWORD \
    nulink/nulink nulink ursula init \
    --signer keystore:///code/xxxxxxxxxxxxxxxxxx \
    --eth-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
    --network horus \
    --payment-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
    --payment-network bsc_testnet \
    --operator-address gggggggggggggggggg \
    --max-gas-price 100
      
      
Example 


    docker run -it --rm \
    -p 9151:9151 \
    -v /root/nulink:/code \
    -v /root/nulink:/home/circleci/.local/share/nulink \
    -e NULINK_KEYSTORE_PASSWORD \
    nulink/nulink nulink ursula init \
    --signer keystore:///code/UTC--2022-10-12T22-57-48.314469723Z--310529366838a3af37a658d0ea50dbe542a16ac1 \
    --eth-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
    --network horus \
    --payment-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
    --payment-network bsc_testnet \
    --operator-address 0x310529366838A3aF37A658D0ea50dbe542a16aC1 \
    --max-gas-price 100

press enter and make screen for youe phars or type it on your notepad because you need to type after this command to continue

<img width="691" alt="lbadil" src="https://user-images.githubusercontent.com/108979536/195464052-3232ee19-9809-47cb-8d3c-374cbef43875.png">


 type y and enter after enter Save all info on a notepad 
 
 type your phars and press enter 
 
 <img width="697" alt="phars" src="https://user-images.githubusercontent.com/108979536/195464192-07b18911-168b-4738-9797-6b13fb798be1.png">

 
 # Launch the Node

      docker run --restart on-failure -d \
      --name ursula \
      -p 9151:9151 \
      -v /root/nulink:/code \
      -v /root/nulink:/home/circleci/.local/share/nulink \
      -e NULINK_KEYSTORE_PASSWORD \
      -e NULINK_OPERATOR_ETH_PASSWORD \
      nulink/nulink nulink ursula run --no-block-until-ready
      
      
# Chexck the status 

    docker logs -f ursula


# Bond and staking  active worker (follow the pictures one by one )

(Give me 0.5 BNBs)

 <img width="1091" alt="binance smart chain" src="https://user-images.githubusercontent.com/108979536/195460681-4d574ae9-b9db-4a0a-8cdb-e30335dc2fdc.png">

 <img width="1049" alt="switch 2" src="https://user-images.githubusercontent.com/108979536/195460693-2979ad0d-5051-41d9-8c21-787dbd14c7b2.png">

<img width="317" alt="3" src="https://user-images.githubusercontent.com/108979536/195460702-e231e162-5f99-44f5-90d8-b2461343bc3c.png">

<img width="284" alt="5" src="https://user-images.githubusercontent.com/108979536/195460736-c73b798e-fbcc-4c36-8f53-6e5b7a87f887.png">


<img width="299" alt="6" src="https://user-images.githubusercontent.com/108979536/195460760-8b060419-731b-44ea-9ce9-8fb7360fae8a.png">


<img width="312" alt="7" src="https://user-images.githubusercontent.com/108979536/195460770-917eb8b2-805b-47ae-bc54-c7ad4e3166f6.png">



<img width="293" alt="8" src="https://user-images.githubusercontent.com/108979536/195460795-d140bc27-bcc6-4f04-9ba4-3ba37370c0cb.png">


<img width="1055" alt="9" src="https://user-images.githubusercontent.com/108979536/195460806-219b5f3b-dfa7-43fb-86de-81b3a4405be0.png">


<img width="1128" alt="10" src="https://user-images.githubusercontent.com/108979536/195460809-eb254176-3c3e-4c41-8bb8-62d0805e865b.png">

<img width="949" alt="11" src="https://user-images.githubusercontent.com/108979536/195460819-c1e0f562-32f9-4d11-8b4d-22a5d222448f.png">


<img width="1031" alt="12" src="https://user-images.githubusercontent.com/108979536/195460832-9f112137-34dc-46a9-8a12-12ab547d069f.png">


<img width="520" alt="13" src="https://user-images.githubusercontent.com/108979536/195460844-8a3d6067-6d1d-4529-b99e-1d697d4f8d4e.png">


<img width="1104" alt="14" src="https://user-images.githubusercontent.com/108979536/195460854-365e41be-ea80-4849-a041-78c07301790f.png">


<img width="263" alt="15" src="https://user-images.githubusercontent.com/108979536/195460864-7f5307e1-8ad9-48f5-8d83-68c4ec6b7bae.png">



<img width="1052" alt="16" src="https://user-images.githubusercontent.com/108979536/195460875-60620145-67c3-43dd-95ad-b3eeff46f6b9.png">


<img width="842" alt="17" src="https://user-images.githubusercontent.com/108979536/195460880-c9445344-f19b-4637-b5fb-43dbee93aa08.png">





Congratulations don’t forget fill the form (by Airdrop Eth addresse put you metamask wallet addresse) : https://docs.google.com/forms/d/e/1FAIpQLSep0rgPRcMd2kUhz53GYmBoktu-u-8npU2DakmzGpmpCmYZPw/viewform


# [Buy me a cup of coffee.](https://paypal.me/AbdelAkridi?country.x=NL&locale.x=en_US)
