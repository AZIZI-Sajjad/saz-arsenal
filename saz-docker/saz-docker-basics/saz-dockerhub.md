# saz-dockerhub
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/dockerhub
```

## DockerHub - Login with Shell Linux
```
docker login -u <UserName>
    ## Then Type the Huckerhub TOKEN
```

## DockerHub - Publish an Image to DockerHub
```
    #### 1- Login to DockerHub via username & TOKEN
docker login -u <UserName>

    #### 2- Tag Image as the same that will be On Dockerhub
docker tag <Old_Image_Name>:<Old_Image_Tag> <Repository_Name_In_Dockerhub>:<Tag_In_DockerHub>

    #### 3- Push the Image to DockerHub
docker push <Repository_Name_In_Dockerhub>:<Tag_In_DockerHub>
```

