# python-dev: A Docker-in-Docker inspired develpoment container for Python projects

`python-dev` is a Docker image inspired by Docker's
[Docker-in-Docker|https://docs.docker.com/samples/docker/] development
container used for developing the Docker project. The `python-dev` is
focused on supporting Python 3 development data science related projects but
should be easily reusable for other Python projects.

## Image Contents
* Jupyter
* Matplotlib
* Pandas
* scikit-learn
* Flask
* Flask-SQLAlchemy

## Running
Start the container in the background by running:

```docker run -d --name python-dev python-dev tail -f /dev/null```

You can then access the shell in the container through

```docker exec -it python-dev /bin/bash```
