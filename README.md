# HelloHolz
1st project !

********************************************************************************************************************************************************************
This will be the first DevOPS project from scratch, the plan is to create a simple webpage, containerize it, use k8s, jenkins , and might add monitoring tools later
********************************************************************************************************************************************************************
1) Using Gemini :
- I created ( index.js , package.json ) files to have a simple webpage saying " Hello Holz ", http, port 3000.
- Created this github repo
2) locally :
- installed npm ( $ sudo apt install npm )
- ( $ npm start ) It was tested locally on my ubuntu lab machine, works fine
3) github :
  - since username and password cant be used again ( to push from local repo ), SSH keys is used
    ```
    $ ssh-keygen -t ed25519 -C "xxxxxxdin@outXXX", cat the output/hash , paste it to github, created the ssh key, now we can pull and push easily !
    ```

4) using  VScode, I tested the docker extension to automatically create a dockerfile.yml
here is the output !
```
FROM node:lts-alpine
ENV NODE_ENV=production
WORKDIR /usr/src/app
COPY ["package.json", "package-lock.json*", "npm-shrinkwrap.json*", "./"]
RUN npm install --production --silent && mv node_modules ../
COPY . .
EXPOSE 3000
RUN chown -R node /usr/src/app
USER node
CMD ["npm", "start"]
```

--- For a reason, the above code was not working as expected, tried to simplify things :
```
FROM node:lts-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . . 
EXPOSE 3000
CMD ["node", "index.js"]
```
- also the const home in index.js ---> '0,0,0,0' because localhost was not working from the container

5) Created the final docker image ( hello-holz )

5) now I want to use kubernetes, installed minikube
6) Trying to upload the image to dockerhub, keeps saying "unauthorized "
7) "docker login" was already done
8) $ docker tag hello-holz mohazmy/hello-holz 
9) $ docker tag hello-holz mohazmy/hello-holz
10) ( $  kubectl apply -f deployment.yml ) because i ran it before fixing the docker image issue
20) git push to update github repo
21) now we make the ( service.yml ) so we can access our webpage
*****
*****
NOTE 
****
****
 Since we are using minikube, we need to run ( $ minikube tunnel ) to have an ip 

 ************************************

######################
 22) Jenkins TIME
######################

22) 
