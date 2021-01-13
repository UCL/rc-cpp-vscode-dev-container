# rc-cpp-vscode-dev-container
Docker container definitions for Visual Studio Code C++ development environment

The Dockerfile inside `.devcontainer` defines an Ubuntu docker image that can be built and linked to as a remote container from within VS code. This means you can use VS Code on your host Mac, Windows, other Linux machine and be able to develop in a self contained environment matching what we recommend for PHAS0100: Ubuntu 20.04, g++ 9.3.0 and with other tool like cmake, git, clang-format already installed. 

### Visual Studio Code with C++ development environment

To get setup follow the steps here https://code.visualstudio.com/docs/remote/containers-tutorial to:
   * Install VS Code on your host machine (Mac, Windows, Linux variant)
   * Install Docker Desktop on your host machine and make sure it is running
   * Open VS Code and add the `Remote - Containers` extension `ms-vscode-remote.remote-containers`
   * Click on the green remote containers status button at the bottom left of the window
   * Then to check everything works select the `Remote-Containers: Try a Sample...` and the C++ example
   * Go through the README.md and suggested things to try to familiarise yourself  
 
To use the Ubuntu 20.04 dev container you should clone this repository to your host machine and then copy the `.devcontainer` folder including the devcontainer.json and Dockerfile files inside it to the cmake project you want to develop:
`cp -r .devcontainer /path/to/YourCMakeProject/`.

You can then open `YourCMakeProject` inside VS Code and it will ask if you want to reopen and build the project in the dev container that we defined. Once you have done that you can build, compile, debug and use the VS Code terminal from within the dev container. Try opening a VS Code terminal and typing `cat /etc/os-release` and you should see the the OS is Ubuntu 20.04.1 LTS (Focal Fossa). 
  
### Using the docker without VS Code

If you just want to try out running from the command line you can build and run the docker image without using VS Code. Follow the steps above to install Docker Desktop and make sure the app if running. Then clone this repository and from the command line on your host machine run the following to build and then run the docker image. From the folder containing the Dockerfile:
* `docker build -t phas0100env .`
* `docker run -it phas0100env /bin/bash`

You'll then have an interactive terminal on the ubunutu image where you can try out commands.
