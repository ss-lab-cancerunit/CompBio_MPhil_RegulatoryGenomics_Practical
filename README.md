# Docker installation
The first section includes the docker installation instructions for macOS, windows as well as Linux.

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

- Install Docker Engine on [CentOS](https://docs.docker.com/engine/install/centos/)
- Install Docker Engine on [Debian](https://docs.docker.com/engine/install/debian/)
- Install Docker Engine on [Fedora](https://docs.docker.com/engine/install/fedora/)
- Install Docker Engine on [Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- Install Docker Engine from [binaries](https://docs.docker.com/engine/install/binaries/)

[non-root](https://docs.docker.com/engine/install/linux-postinstall/)

# Pull & Run docker image
_Our docker image is based on [rocker/rstudio](https://hub.docker.com/r/rocker/rstudio). Please make sure you have docker installed before running it!_

Now, you may follow these three steps:
1. Pull docker image: `docker pull xihajun/mphil_practical_ss:latest`
2. Run docker with sudo access: `docker run -d -p 8787:8787 -e ROOT=TRUE -e PASSWORD=123456 xihajun/mphil_practical_ss:latest`
3. Access this link: http://127.0.0.1:8787
4. Login (by default: `username: rstudio`, `password:123456`)
5. Enjoy!

Docker packed all the packages and software inside. Hopefully, it would make life easier now!

** you may need to login the docker terminal: `docker exec -ti -u 0 your_container_id /bin/bash`**

# Extract data from docker
You can either use `docker cp` or create a new docker image to save the change.
## `docker cp` (eg. extract the folder MPhil_Practical_SS)
- Check your container_name using `docker ps` *(note: it is not the container id)*
- `docker cp container_name:/home/rstudio/MPhil_Practical_SS DEST_PATH`


_(Note that DEST_PATH is the path in your machine. You can find out more [here](https://docs.docker.com/engine/reference/commandline/cp/))_

## Save as a custimised docker image 
- Quit your docker terminal
- Check your docker container id: `docker ps -a`
- Commit your change `docker commit [CONTAINER_ID] [new_image_name]`
  - If you want to save the image, a good way is to push it onto docker hub, you will need to create a new docker account [here](https://hub.docker.com)
  - Create a public repository (eg.dockerdisco) like what you do at Github
  - Now you can commit: `docker commit [CONTAINER_ID] yourusername/dockerdisco:tag`
- After committing, you are able to push. `docker push yourusername/dockerdisco:tag`


# R Packages
If you're using the Docker container you don't need to install these. If you want to run the code on your laptop or desktop, then install these packages.

### R-code:
```{}
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
options(timeout = 300)

#uncomment! if need to run

BiocManager::install(c("BiocStyle","EnsDb.Hsapiens.v86","org.Hs.eg.db","STRINGdb","ChIPpeakAnno","GenomicRanges","EnsDb.Hsapiens.v86","rGREAT","circlize","rGREAT","circlize","STRINGdb", "rGREAT", "circlize"))
```

----------

[HTML viewer](http://www.edu-ing.cn/sslab/tutorial.html)

