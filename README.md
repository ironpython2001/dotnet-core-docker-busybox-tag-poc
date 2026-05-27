# dotnet core docker busybox tag poc
A simple experiment to use docker busybox tag with dotnet core

Make sure visual studio Instance.

Navigate to the csproj directory and run the commands.


1. podman machine start
2. podman build -t hello-app .
3. podman run --rm hello-app

will see "Hello, World!" message on console 

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





