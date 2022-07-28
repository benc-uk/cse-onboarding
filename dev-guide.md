# Local Developer Environment Setup

There is no prescribed dev environment in CSE, and everyone is free to set up their machine and work how they wish. The wide range of customer projects we engage on requires us to be flexible and willing to work with many languages, toolchains and platforms. This is in line with our "meet the customer where they are" aspiration.

This section contains a *suggested* set of tools and dev environment which many in CSE use, it has been found to be flexible and works well in nearly every scenario.

## Windows Users

The two core pieces of software you'll need installed within Windows, are VS Code and the new Windows Terminal. You can install these manually if you wish, however using WinGet (details below) can automate and simplify this.

- Install [Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)
- Install [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-gb&gl=GB)

WinGet is the standard package manager for Windows and is included as part of the OS. With it you can automate the install of what you need. A "pack" for WinGet has been created and it contains all of the tools & software you will need

- [Install 'Dev Tooling' pack here](https://winstall.app/packs/zzbVwCc3M)

For all the development tools, software, SDKs and other things you will be using day to day - these should be installed in WSL (Windows Subsystem For Linux) and not into Windows. This is the STRONGLY recommended route for Windows users to carry out their work.

- [Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install)
  - It is recommended to use a Debian based Linux distro such as Ubuntu
  - You can simply run `wsl --install` (from an elevated/admin prompt) and this will take care of everything (it will pick Ubuntu for you)
- Install the [remote development extensions](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) in VS Code to work with WSL.

### WSL Setup

These steps should be run inside WSL. This repo [https://github.com/benc-uk/tools-install](https://github.com/benc-uk/tools-install) contains a maintained library of easy install scripts which can accelerate this stage

### Setup Tools Install Repo

1. Latest WSL Ubuntu versions come with `git` installed. You can check if git installed by running `git --version` in your WSL Terminal tab.
2. Clone Tools Install repo to your WSL
    ```
    cd ~
    git clone https://github.com/benc-uk/tools-install
    cd tools-install
    ``` 
3. There is a load of bash scripts in this repo. Not every project would need all of these tools. So here is a suggested list of tools to install as sane defaults for optimial experience.

    1. **Common Tools Installation**   
        ```
        ./base.sh
        ```
    1. **Docker Installation**   
        ```
        ./docker.sh
        ```
        Validate installation
        ```
        docker --version
        ```
    1. **Node Installation**  
        ```
        ./node.sh
        ```
        Validate installation
        ```
        node --version
        npm --version
        ```
    1. **Dotnet Installation**  
        ```
        ./dotnet.sh
        ```
        Validate installation
        ```
        dotnet --version
        ```
    1. **Go Installation**
        ```
        ./golang.sh
        ```
        Validate installation
        ```
        go version
        ```
    1. **Java Installation**
        ```
        ./jdk.sh
        ```
        Validate installation
        ```
        java --version
        ``` 
    1. **Azure CLI Installation**
        ```
        ./azure-cli.sh
        ```
        Validate installation
        ```
        az --version
        ``` 

4. Install VS Code extensions for relevant languages.
  
    This is a list of recommended VS Code extensions
    - [Azure (extension bundle pack)](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)
    - [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
    - [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
    - [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
    - [Kubernetes](https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools)
    - [Terraform](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform)
    - [Bicep](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-bicep)
    - [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
    - [Shellcheck](https://marketplace.visualstudio.com/items?itemName=timonwong.shellcheck) (If working with bash a lot)
    - [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
    - [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) (If you have been accepted into the [technical preview](https://github.com/features/copilot/signup))
    - [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) (For JS/Node/TS work)
    - [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) (For HTML/JS/Node/TS work)
    - [Draw.io](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)
5. Install Docker in WSL. There are a number of ways to do this but [this script will quickly and easily install Docker CLI and container runtime](https://github.com/benc-uk/tools-install/blob/master/docker.sh)
    - Many guides including the VS Code docs will claim that Docker Desktop is required. However that is ***no longer the case***, as long as you open the project folder in WSL first, then open it as a container.
    - However you can use Docker Desktop should you wish - [Docker Desktop](https://www.docker.com/products/docker-desktop/)
    - Install Azure CLI, see above tools-install repo for a helper script [or follow the docs](http://aka.ms/azure-cli)

6. Pushing and pulling code with Azure DevOps from WSL can be tricky due to the credentials & auth required, there are two options
    - Use git with SSH. [Create a SSH keypair, and add this to any Azure DevOps projects](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops)
    - Install and configure [Git Credential Manager](https://github.com/GitCredentialManager/git-credential-manager) (Mixed results trying to get this to work)

## MacOS Users

TBA 🙃

## Dev Containers

Many in CSE use ["Dev Containers"](https://microsoft.github.io/code-with-engineering-playbook/developer-experience/devcontainers/) which is a feature of VS Code, where you run VS code from inside a container which can include all the tools and setup needed to work with a particular code base.

To validate this feature is working, you can [clone this repo](https://github.com/benc-uk/nodejs-demoapp) to your local machine. Open the repo from WSL in VS Code, then select the option "Reopen in container", if you get no errors and can open a terminal in VS Code and execute `make run` also without error, then Dev Containers is working. NOTE. You must ensure that VS Code has the project open using WSL (You will see 'WSL' the very bottom left) before reopening in a container.
