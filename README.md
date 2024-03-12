# protobuf-docker
Protoc v2  
Docker image of old version of protobuf for generating sources using .proto files with syntax = "proto2  
Look in my docker-hub repository for actual images:  
https://hub.docker.com/repository/docker/atanava/protoc-2.6.1/general
### Java example:  
> docker run --rm  --name protoc2 \\  
> --env LANG=java \\  
> -v \<absolute path to .proto files folder on host\>:/protobuf \\  
> -v \<absolute path to generated files folder on host\>:/protobuf/output \\  
> -w /protobuf \\  
> atanava/protoc-2.6.1:0.0.1  
#### Or:
> docker run --rm  --name protoc2 \\  
> --env LANG=java \\  
> -v /home/username/myproject/src/main/resources/protobuf:/protobuf \\  
> -v /home/username/myproject/src/main/java:/protobuf/output \\  
> -w /protobuf \\  
> atanava/protoc-2.6.1:0.0.1
### Other languages: 
Other languages wasn't tested yet,  but you can try it by replacing --env LANG=java with another language.  
### Edit, Move, Delete etc.
After executing of ```docker run``` command, your generated files will be placed to new subfolder ```output``` of source folder you mentioned in docker run command.  
But only **root** user of created container will became an owner of this folder.  
Use **chown** command on host to get write access to these files.

