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
From
