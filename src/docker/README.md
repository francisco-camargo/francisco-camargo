# Docker

[Return to top README.md](../../README.md)

## Install Docker on Ubuntu

First install Docker Engine and then install Docker Desktop.

### Install Docker Engine for Ubuntu

- [Guide](https://docs.docker.com/engine/install/ubuntu/)
- [Uninstall old versions](https://docs.docker.com/engine/install/ubuntu/#uninstall-old-versions) on how to uninstall previous versions of Docker
- [Installation methods](https://docs.docker.com/engine/install/ubuntu/#installation-methods) on different installation methods
- Set up [Docker's Package Repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository) by following the provided command line instructions.
- Verify that Docker Engine was successfully installed by running

    ```bash
    sudo docker run hello-world
    ```

### Upgrade Docker Engine

Repeat step 2 from [Docker's Package Repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

In particular, to get the latest packages run,

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Install Docker Desktop for Ubuntu

- [Docker Desktop for Ubuntu](https://docs.docker.com/desktop/install/ubuntu/) installation
- Download the DEB package
- Install the DEB package

Be sure to update the path pointing to the `.deb` file as needed

```bash
sudo apt-get update
sudo apt-get install ./docker-desktop-amd64.deb
```

## Launch Docker Desktop

To start Docker Desktop for Linux, search Docker Desktop on the Applications menu and open it.

Or instead, from the terminal, run

```bash
systemctl --user start docker-desktop
```

## Sign in into Docker Desktop

If you are unable to sign in into Docker Desktop for Linux, it is likely because you much [enable `pass`](https://docs.docker.com/desktop/get-started/#signing-in-with-docker-desktop-for-linux)

## Install `docker compose`

- [Guide](https://docs.docker.com/compose/install/). Seems to indicate that `docker compose` comes with Docker Desktop
- [Install Docker Compose plugin](https://docs.docker.com/compose/install/linux/#install-using-the-repository) if needed to install explicitly, run

```bash
sudo apt-get update
sudo apt-get install docker-compose-plugin
```

Verify the installation with

```bash
docker compose version
```
