# dotnet core docker busybox tag poc
A simple experiment to use docker busybox tag with dotnet core

Make sure visual studio Instance.

Navigate to the csproj directory and run the commands.


1. podman machine start
2. podman build -t hello-app .
3. podman run --rm hello-app

will see "Hello, World!" message on console 

***** get inside the docker container 
podman run -it --rm --entrypoint /bin/sh hello-app

***** to run the binary inside the docker container
/hello-binary

**** To clean(optional) Clean Everything
# Stop all running containers
podman stop -a

# Remove all containers
podman rm -a

# Remove all images
podman rmi -a

# Remove all volumes
podman volume rm -a

# Remove all networks (except default)
podman network rm -a

# Remove all pods
podman pod rm -a


#Check Freed Space
# Before/after disk usage
podman system df

# Verify Nothing Left
podman images        # should be empty
podman ps -a         # should be empty
podman volume ls     # should be empty


