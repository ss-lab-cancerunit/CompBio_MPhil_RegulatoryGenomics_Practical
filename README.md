# Docker installation
This repo includes the docker installation instructions for macOS, windows as well as Linux.

## Install Docker Desktop on macOS
_In order to install Docker Desktop on macOS, your macOS will have to be version 10.14 or newer._

### Install it manually
You can easily go to the [docker website](https://www.docker.com/products/docker-desktop) to download Docker Desktop for Mac.

<img width="733" alt="image" src="https://user-images.githubusercontent.com/25631641/110496385-549b4b00-80ed-11eb-888c-a4baf9ecc313.png">

You will download this [.dmg](https://desktop.docker.com/mac/stable/Docker.dmg) file. Just like other macOS applications, after double-clicking the `Docker.dmg` file, I believe you will get the docker desktop installed.

### Homebrew (terminal)
If you are familiar with the command line, the easiest way would use [Homebrew Cask](https://github.com/Homebrew/homebrew-cask).

```
brew install --cask docker
```

## Install Docker Desktop on windows
### Install it manually
Instead of a .dmg file, windows users will need to download an [.exe](https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe) file. By double-clicking the `Docker Desktop Installer.exe` file, I believe you will get the docker desktop installed.

### winget (terminal)
If you used [winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/) before, alternatively, you can try to install docker desktop in this way:
```
winget install Docker.DockerDesktop
```

## Install Docker on Linux
_DO NOT use apt/yum/dnf directly if you are not sure, as you may get the older version of docker_

For Linux users, please go [here](https://docs.docker.com/engine/install/) to find more details: https://docs.docker.com/engine/install/



# R Packages
If you're using the Docker container you don't need to install these. Else if you want to run the code on your laptop or desktop install these packages.

### R-code:
```{}
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
options(timeout = 300)

#uncomment! if need to run

BiocManager::install(c("BiocStyle","EnsDb.Hsapiens.v86","org.Hs.eg.db","STRINGdb","ChIPpeakAnno","GenomicRanges","EnsDb.Hsapiens.v86","rGREAT","circlize","rGREAT","circlize","STRINGdb", "rGREAT", "circlize"))
```


