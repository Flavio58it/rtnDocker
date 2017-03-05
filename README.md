# rtnDocker - Dockerfiles and scripts for building and running Manifold and rtndf nodes

### Introduction

This repo contains Dockerfiles and scripts that can be used to build containerized Manifold and rtndf apps. Each directory consists of three files:

    * Dockerfile.
    * build.
    * run (only for nodes, not core libraries).
  
### Build and run
  
To build and run a component:

    cd ~/
    git clone git://github.com/richardstechnotes/rtnDocker
    cd ~/rtnDocker/<component>
    ./build
    ./run
    
The core Mainfold and rtndf components (manifoldcore, manifoldcoretf, manifoldcoretfgpu, rtndfcore, rtndfcoretf and rtndfcoretfgpu) will be pulled from Docker Hub (https://hub.docker.com/r/rtndocker/) if they have not been build locally so it is ok just to build the nodes without worrying about the core components.

ManifoldNexus can also just be pulled from Docker directly:

    docker pull rtndocker/manifoldnexus
    
It could then be run using:

    docker run --rm --net=host --name manifoldnexus \
        -u $UID \
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        -e="DISPLAY" \
        -v $HOME/.config/Manifold:/.config/Manifold\
        rtndocker/manifoldnexus
        
Or, use the script in rtnDocker/manifoldnexus:

    ~/rtnDocker/manifoldnexus/run
        
To build all components locally, use the all script.

### GUI mode and console/daemon mode

Any nodes that support a GUI will start up in GUI mode by default. To run in console/daemon mode (necessary on headless servers), run:

    ~/rtnDocker/manifoldnexus/run -x -y
    
The "-x -y" flags can be added to any GUI node to force console/daemon mode.

See https://richardstechnotes.wordpress.com/ for more information.
