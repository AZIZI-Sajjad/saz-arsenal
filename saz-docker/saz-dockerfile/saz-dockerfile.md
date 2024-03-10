# saz-DockerFile
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/DockerFile
```

## DockerFile - COPY
```
COPY <Source-Locale> <Destination_In_Container>
```

## DockerFile - COPY & Install Requirements.txt
```
COPY <requirements_File> <Destination_DIR_In_Docker_To_Copy_Requirements.txt>
RUN pip install -r <Destination_DIR_In_Docker_To_Copy_Requirements.txt>
COPY <Source-Locale> <Destination_In_Container>
```


## DockerFile Build an image in current DIR & specified name
```
docker build -t <New_Docker-Image_Name>:<version_{{Tag}}> .
```

## DockerFile Build an image & specified name
```
docker build -t <New_Docker-Image_Name>:<version_{{Tag}}> -f <Dockerfile_Name> <DockerFile_Dir>
```
