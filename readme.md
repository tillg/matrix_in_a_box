# matrix_in_a_box

Running a matrix installation with many options within one docker container. Uses the [advanced Matrix Ansible Playbook](https://github.com/spantaleev/matrix-docker-ansible-deploy) to run multiple dockers within one docker using [Docker in Docker!](https://hub.docker.com/_/docker).

## Usage

**1.** Start the matrix in a box:

```shell
docker run -it --privileged --name mib -d tgartner/matrix_in_a_box
```

**2.** Check that startup worked:

```shell
docker logs mib
```

**3.** Access the box:

```shell
docker run -it --rm --link mib:docker docker sh
```

## Notes

* We use the Docker IN Docker (dind) image [from docker](https://hub.docker.com/_/docker)
* For installing Matrix within the docker:dind (we call it the _box_) we use the [Ansible scripts](https://github.com/spantaleev/matrix-docker-ansible-deploy)