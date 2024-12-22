<p align="center">
    <img width="233px" height="auto" src="https://www.coozila.com/static/themes/prometheus/img/coozila.png" />
</p>

<p align="center">
    <a href="https://twitter.com/coozila"><img src="https://badgen.net/badge/twitter/@coozila/1DA1F2?icon&label" /></a>
    <a href="https://github.com/coozila/apps"><img src="https://badgen.net/github/stars/coozila/apps?icon=github" /></a>
    <a href="https://github.com/coozila/apps"><img src="https://badgen.net/github/forks/coozila/apps?icon=github" /></a>
    <a href="https://facebook.com/coozila"><img src="https://badgen.net/badge/facebook/@coozila/1877F2?icon&label" /></a>
    <a href="https://opensource.org/licenses/MIT"><img src="https://badgen.net/static/license/MIT/blue" /></a>
</p>

# The Coozila! APPS Library

Discover popular applications provided by [Coozila!](https://coozila.com), expertly containerized and ready for immediate deployment.

## Why Use Coozila! Images?

- **Up-to-Date**: Coozila! actively monitors upstream source changes and promptly publishes new versions of its images through automated systems.
- **Latest Features**: With Coozila! images, you gain access to the latest bug fixes and features as soon as they are available.
- **Consistent Components**: Coozila! apps, virtual machines, and cloud images utilize the same components and configuration approach, making it easy to switch between formats based on your project requirements.
- **Regular Releases**: Coozila! app images are released consistently with the latest distribution packages available.

## Getting an Image

The recommended way to obtain any of the Coozila! Images is to pull a prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/coozila/).

```console
docker pull coozila/app
```

To use a specific version, you can pull a versioned tag:

```console
docker pull coozila/app:[TAG]
```

If you prefer, you can also build the image yourself by cloning the repository, navigating to the directory containing the Dockerfile, and executing the `docker build` command:

```console
git clone https://github.com/coozila/apps.git
cd apps/app
docker build -t coozila/app .
```

> [!TIP]
> Remember to replace the `app` placeholders in the example command above with the appropriate values.

## Running the Application Using Docker Compose

Each application’s main folder includes a functional `docker-compose.yml` file. You can easily run the application using the following command:

```console
curl -sSL https://raw.githubusercontent.com/coozila/apps/main/APP/docker-compose.yml > docker-compose.yml
docker-compose up -d
```

> [!TIP]
> Remember to replace the `APP` placeholder in the example command above with the correct application name.