# R-cheat-sheet

### Start Docker
see wiki page for documentation [link](https://github.com/rocker-org/rocker/wiki)
```bash
docker run -it --rm -p 8787:8787 rocker/ropensci:latest <<optional_command>>
#optionally, add parameters to configure: username, password, working directory, root privileges, etc

-v 'path/to/machine/dir:path/to/container/dir'
```
Then in browser, go to:  http://127.0.0.1:8787 . (default un/pw = 'rstudio')

explannation of above: 
 - `run`: run a container
 - `-i` : interactive mod (will relay messages from the virtual container to your host terminal
 - `-t` : enable tty mode (necessary for the `-i` to work properly, hence always used together)
 - `--rm` : delete the container after it finishes (other times, you may want to keep it around, if you want to start later at the same "state" of the previous point
 - `-p` : port mapping, follows the convention host:container (allows you to use a different port on your machine)
 - `rocker/ropensci:latest` : not unlike github, account/repository:tag (by default, tag is assumed to be "latest")
 - `<<optional_command>>` : e.g. `bash` to start a bash terminal in the container; even if no command is given, sometimes containers have startup scripts that start a program by default

some useful docker commands
```bash
#check running containers
docker ps

#check all containers including previously run ones
docker ps -a

#stop running container
docker stop <container_id>

#check installed images of containers
docker images

#uninstall/delete image of container
docker rmi <image_id>

#download an image of a container
docker pull account/repository:tag
```
