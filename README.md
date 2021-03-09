# Docker installation
This repo includes the docker installation instructions for macOS, windows as well as linux.

## Install Docker Desktop on macOS
_In order to install Docker Desktop on macOS, your macOS will have to be version 10.14 or newer._

### Install it manually
You can easily go the [offical website](https://www.docker.com/products/docker-desktop) to download Docker Desktop for Mac.

<img width="733" alt="image" src="https://user-images.githubusercontent.com/25631641/110496385-549b4b00-80ed-11eb-888c-a4baf9ecc313.png">

You will download this [.dmg](https://desktop.docker.com/mac/stable/Docker.dmg) file. Just like other macOS applications, after double-clicking the `Docker.dmg` file, I believe you will get the docker desktop installed.

### Homebrew (terminal)
If you are familiar with command line, the easiest way would be use [Homebrew Cask](https://github.com/Homebrew/homebrew-cask).

```
brew install --cask docker
```

## Install Docker Desktop on windows
### Install it manually
Instead of a .dmg file, windows users will need to download an [.exe](https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe) file. By double-clicking `Docker Desktop Installer.exe` file, I believe you will get docker desktop installed.

### winget (terminal)
If you used [winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/) before, alternatively, you can try install docker desktop in this way:
```
winget install Docker.DockerDesktop
```

## Install Docker on linux
_DO NOT use apt/yum/dnf directly if you are not sure, as you may get the older version of docker_

For linux user, please go the [here](https://docs.docker.com/engine/install/) to find more details: https://docs.docker.com/engine/install/
