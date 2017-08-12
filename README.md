# python-dev: A Docker-in-Docker inspired develpoment container for Python projects

`python-dev` is a Docker image inspired by Docker's
[Docker-in-Docker|https://docs.docker.com/samples/docker/] development
container used for developing the Docker project. The `python-dev` is
focused on supporting Python 3 development data science related projects but
should be easily reusable for other Python projects.


## Image Contents
Python 3.6
* Jupyter
* Matplotlib
* Pandas
* scikit-learn
* Flask
* Flask-SQLAlchemy

Node
* npm
* create-react-app
* react-c3js

## Installation
Start the container in the background by running:

```
docker run -d --name python-dev anidata/python-dev tail -f /dev/null
```

You can then access the shell in the container through

```
docker exec -it python-dev /bin/bash
```

*NOTE:* This project does not work with Docker Toolbox/VirtualBox-based VM's
on Windows do to limitations of the `vboxsf` shared folder driver. In order
for this to work on Windows, please use Docker for Windows and enable
Hyper-V when requested.

## Troubleshooting
*My React application is not reload on file changes on Windows*

Windows shared folders with Docker containers do not trigger inotify events,
which is what initiates the reload process. For projects using `chokidar` or
created using `create-react-app` set the environment variable
`CHOKIDAR_USEPOLLING=1` to fallback to file change polling.

e.g., an application created by `create-react-app`

```
CHOKIDAR_USEPOLLING=1 npm start
```
