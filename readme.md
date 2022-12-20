# dclong/jupyterhub-toree [@DockerHub](https://hub.docker.com/r/dclong/jupyterhub-toree/) | [@GitHub](https://github.com/dclong/docker-jupyterhub-toree)

JupyterHub with Spark via Apache Toree (for Scala/Spark) and pyspark/findspark (for PySpark).
<span style="color:red">
This Docker image is no longer maintained.
</span>
Please refer to 
[Recommended Docker Images](http://www.legendu.net/en/blog/my-docker-images/#recommended-docker-images) 
for alternatives.

## [Recommended Docker Images](http://www.legendu.net/en/blog/my-docker-images/#recommended-docker-images) 

## Prerequisite
You need to [install Docker](http://www.legendu.net/en/blog/docker-installation/) before you use this Docker image.


## Usage in Linux/Unix

Please refer to the Section
[Usage](http://www.legendu.net/en/blog/my-docker-images/#usage)
of the post [My Docker Images](http://www.legendu.net/en/blog/my-docker-images/) 
for detailed instruction on how to use the Docker image.

The following command starts a container 
and mounts the current working directory and `/home` on the host machine 
to `/workdir` and `/home_host` in the container respectively.
```
docker run -d \
    --hostname jupyterhub-toree \
    --log-opt max-size=50m \
    -p 8000:8000 \
    -e DOCKER_USER=$(id -un) \
    -e DOCKER_USER_ID=$(id -u) \
    -e DOCKER_PASSWORD=$(id -un) \
    -e DOCKER_GROUP_ID=$(id -g) \
    -e DOCKER_ADMIN_USER=$(id -un) \
    -v $(pwd):/workdir \
    -v $(dirname $HOME):/home_host \
    dclong/jupyterhub-toree /scripts/sys/init.sh
```
The following command (*only works on Linux*) does the same as the above one 
except that it limits the use of CPU and memory.
```
docker run -d \
    --hostname jupyterhub-toree \
    --log-opt max-size=50m \
    --memory=$(($(head -n 1 /proc/meminfo | awk '{print $2}') * 4 / 5))k \
    --cpus=$(($(nproc) - 1)) \
    -p 8000:8000 \
    -e DOCKER_USER=$(id -un) \
    -e DOCKER_USER_ID=$(id -u) \
    -e DOCKER_PASSWORD=$(id -un) \
    -e DOCKER_GROUP_ID=$(id -g) \
    -e DOCKER_ADMIN_USER=$(id -un) \
    -v $(pwd):/workdir \
    -v $(dirname $HOME):/home_host \
    dclong/jupyterhub-toree /scripts/sys/init.sh
```
## [Use the JupyterHub Server](http://www.legendu.net/en/blog/my-docker-images/#use-the-jupyterhub-server)

## [Add a New User to the JupyterHub Server](http://www.legendu.net/en/blog/my-docker-images/#add-a-new-user-to-the-jupyterhub-server)

## [Use Spark in JupyterLab Notebook](http://www.legendu.net/en/blog/my-docker-images/#use-spark-in-jupyterlab-notebook)

## [Detailed Information](http://www.legendu.net/en/blog/my-docker-images/#list-of-images-and-detailed-information) 

## [Known Issues](http://www.legendu.net/en/blog/my-docker-images/#known-issues)

## [About the Author](http://www.legendu.net/pages/about)
