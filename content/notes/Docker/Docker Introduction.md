**Docker** is a tool that promises to easily encapsulate the process of creating a distributable artifact for any application, deploying it at scale into any environment, and streamlining the workflow and responsiveness of Agile software organizations.

**Docker** is an open-source platform that uses **containerization** to package applications and all their required dependencies (libraries, system tools, and code) into a single unit called a container

It is not an Enterprise virtualization platform (VMware, KVM, etc.). Virtual machines contain a complete operating system, running on top of a hypervisor that is managed by the underlying host operating system. Hypervisors create virtual hardware layers that make it possible to run additional operating systems on top of a single physical computer system. This makes it very easy to run many virtual machines with radically different operating systems on a single host. With containers, both the host and the containers share the same kernel. This means that containers utilize fewer system resources but must be based on the same underlying operating system (e.g., Linux).

It is not a Cloud platform (OpenStack, CloudStack, etc.). It only handles deploying, running, and managing containers on preexisting Docker hosts. It doesn’t allow you to create new host systems (instances), object stores, block stor age, and the many other resources that are often managed with a cloud platform.

# Terminology

Docker client - This is the `docker` command used to control most of the Docker workflow and talk to remote Docker servers.

Docker server - This is the `dockerd` command that is used to start the Docker server process that builds and launches containers via a client.

Docker or OCI images - Docker and OCI images consist of one or more filesystem layers and some important metadata that represent all the files required to run a containerized application. A single image can be copied to numerous hosts. An image typically has a repository address, a name, and a tag. The tag is generally used to identify a particular release of an image (e.g., docker.io/superorbital/wordchain:v1.0.1). A Docker image is any image that is compatible with the Docker toolset, while an OCI image is specifically an image that meets the Open Container Initiative standard and is guaranteed to work with any OCI-compliant tool.

Linux container - This is a container that has been instantiated from a Docker or OCI image. A specific container can exist only once; however, you can easily create multiple containers from the same image. The term Docker container is a misnomer since Docker simply leverages the operating system’s container functionality.

Atomic or immutable host - An atomic or immutable host is a small, finely tuned OS image, like Fedora CoreOS, that supports container hosting and atomic OS upgrades