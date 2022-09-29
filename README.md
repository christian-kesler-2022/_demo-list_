# Demo List

----
## Persisent Storage & XML Validation Server (NodeJS)

GitHub Repo:
  
    https://github.com/christian-kesler-2022/node-example-server

Head over to Play With Docker using the link below:

    https://labs.play-with-docker.com/
  
Now paste in the following commands into the terminal and open port 3000:

    mkdir node-example-server
    cd node-example-server
    git init
    git branch -m main
    git remote add origin https://github.com/christian-kesler-2022/node-example-server
    git pull origin main
    docker build . -t node-example-server
    docker run -d -p 3000:3000 -v /root/node-example-server/src/model:/src/model node-example-server
 
----
## Offline Installation of Persisent Storage & XML Validation Server (NodeJS)

GitHub Repo:
  
    https://github.com/christian-kesler-2022/node-example-server

Head over to Play With Docker using the link below:

    https://labs.play-with-docker.com/
  
Now paste in the following commands into the terminal in sequence:

#### Exporting the Images

    clear
    mkdir node-example-server
    mkdir docker-offline
    cd node-example-server
    git init
    git branch -m main
    git remote add origin https://github.com/christian-kesler-2022/node-example-server
    git pull origin main
    docker build . -t node-example-server
    docker save node-example-server > ../docker-offline/node-example-server.tar
    docker save node > ../docker-offline/node.tar
    cd ../docker-offline
    clear
    pwd
    ls -lh
    
#### Removing existing Images

    clear
    docker image ls
    docker image rm -f node-example-server
    docker image ls
    docker image rm -f node
    docker image ls
    docker image rm -f 954cea825b78
    clear
    docker image ls

#### Purging Source Code
    
    clear
    mv ../node-example-server/src/model ./model
    rm -r ../node-example-server
    cd ..
    clear
    pwd
    ls -lha
    
#### Loading exported Images

    clear
    cd docker-offline
    docker load --input node.tar
    docker load --input node-example-server.tar
    clear
    docker image ls

#### Running Container
    
    clear
    docker run -d -p 3000:3000 -v /root/docker-offline/model:/src/model node-example-server

#### Showcasing Persistent Storage

    clear
    cd model/input
    printf "\n\t INPUT \n"
    ls -l
    cd ../output/error
    printf "\n\t ERROR \n"
    ls -l
    cd ../fail
    printf "\n\t FAIL \n"
    ls -l
    cd ../ignore
    printf "\n\t IGNORE \n"
    ls -l
    cd ../pass
    printf "\n\t PASS \n"
    ls -l
    cd ../../..

----
## DevExtreme & Data Visualization (NodeJS)

GitHub Repo:  

    https://github.com/christian-kesler-2022/node-boilerplate

Head over to StackBlitz using the link below:

    https://stackblitz.com/edit/node-boilerplate
  
Now paste in the following commands into the terminal and open port 3000:

    cd src
    npm install
    node index.js

----
## Ironclad Authentication (NodeJS & MySQL)

GitHub Repo:
  
    https://github.com/christian-kesler-2022/ironclad

Head over to Play With Docker using the link below:

    https://labs.play-with-docker.com/
  
Now paste in the following commands into the terminal and open port 3000:

    docker run -d \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=ironclad \
    mysql:5.7
    mkdir ironclad
    cd ironclad
    git init
    git branch -m main
    git remote add origin https://github.com/christian-kesler-2022/ironclad
    git pull origin main
    docker build . -t ironclad
    docker run -it \
    -e MYSQL_ROOT_PASSWORD=secret \
    -p 3000:3000 ironclad
