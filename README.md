# Demo List

## DevExtreme (NodeJS)

GitHub Repo:  

    https://github.com/christian-kesler-2022/node-boilerplate

Head over to StackBlitz using the link below:

    https://stackblitz.com/edit/node-boilerplate
  
Now paste in the following commands into the terminal and open port 3000:

    cd src
    npm install
    node index.js

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
