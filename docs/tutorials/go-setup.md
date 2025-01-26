# Setting up a dev container for Go

1. **Prerequisites**
    1. You need the following softwares: VSCode and Docker
    2. Install the Dev Containers extension on VSCode 

2. **Setting up a Dev Container in VSCode**
    1. Create a new project 
    ```
    mkdir go-dev-container
    ```
    and
    ```
    cd go-dev-container
    ```
    and 
    ```
    git init
    ```
    2. Open **VSCode** and navigate to the `go-dev-container` directory
    3. Type `Cmd+Shift+P` on Mac and `Ctrl+Shift+P` on Windows type `Dev Containers: Add Development Container Configuration Files`.
    4. Press `Add configuration to workspace`. Search for **Go**. Press `Go, devcontainers` from from the list of container configurations and choose the version you want to run. Keep the default configurations.
    5. Now you should have a default `.devcontainers/devcontainers.json` file



    6. Now you have set up the Go Container environment. To start the container, press `Cmd+Shift+P` on mac or `Ctrl+Shift+P` on windows. Click `Dev Containers: Rebuild and Reopen in Container`. This will take a while.
    7. To customize your Dev Container, you can modify the `devcontainer.json` file as follows. The name of the container is in the `name` field. The `image` is the default Docker base environment. With the `customizations`, you can modify the settings or the extensions used in the environment. And finally there are further settings such as `postCreateCommand` which are commands that run after the container is built. Further documentation exists at [Create a Dev Container](https://code.visualstudio.com/docs/devcontainers/create-dev-container).
    8. In the terminal, once the container is running you can type ```go version```

<ins>**Step E Code**</ins>
```json
    {
        "name": "Go",
        "image": "mcr.microsoft.com/devcontainers/go:1-1.23-bookworm",
        "features": {
            "ghcr.io/devcontainers/features/go:1": {}
        }
    }
```
<ins>**Step G Code**</ins>
```json
        {
            "name": "COMP423 Course Notes",
            "image": "mcr.microsoft.com/devcontainers/python:latest",
            "customizations": {
                "vscode": {
                    "settings": {},
                    "extensions": ["ms-python.python"]
                }
            },
            "postCreateCommand": "pip install -r requirements.txt"
        }
```
    
3. **Now let us actually create in Go!**
    1. No type in the terminal ```go mod init hello-dev-container```
    2. This should create a file which should initialize Go in this directory.
    3. Create a new file named `main.go`
    4. In this new file we will code our program as follows.
    5. In the terminal type go `go run main.go` and this should result in a "Hello COMP423!" outputted.

<ins>**Step D Code**</ins>
```Go
    package main
    import "fmt"
    func main() {
        fmt.Println("Hello COMP423!")
    }
```




    


* Primary author: [Pranav Turlapati](https://github.com/pranavturlapati28)

* Reviewer: [Tianyi Zhou](https://github.com/Bugaboolol)

