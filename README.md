# rust-mingw64-gtk Docker image

This Fedora-based Docker image allows you to quickly and easily build GTK+3 apps written in Rust for the Windows MinGW-W64 (Windows 64-bit) platform without installing all the dependencies natively.

It is meant to be customized for your use case, but also has a published Docker image.

## Usage 

One could build a project in the current directory, where this Dockerfile is, by
1) Modifying the Dockerfile to add all your native dependencies
2) Building the image: `$ docker build . -t PROJECTNAME-build-image`
3) Creating a container with the source mounted the image (which kicks off the build): `$ docker create -v $(pwd):/home/rustacean/src --name PROJECTNAME-build PROJECTNAME-build-image`
4) Each time you want to build the project, start the Docker container. Add "-ai" to watch the build progress. `$ docker start PROJECTNAME-build`
