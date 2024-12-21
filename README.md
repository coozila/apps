<p align="center">
    <img width="400px" height=auto src="https://www.coozila.com/static/themes/prometheus/img/coozila.png" />
</p>

<p align="center">
    <a href="https://twitter.com/coozila"><img src="https://badgen.net/badge/twitter/@coozila/1DA1F2?icon&label" /></a>
    <a href="https://github.com/coozila/apps"><img src="https://badgen.net/github/stars/coozila/apps?icon=github" /></a>
    <a href="https://github.com/coozila/apps"><img src="https://badgen.net/github/forks/coozila/apps?icon=github" /></a>
    <a href="https://github.com/coozila/apps/actions/workflows/ci-pipeline.yml"><img src="https://github.com/coozila/apps/actions/workflows/ci-pipeline.yml/badge.svg" /></a>
</p>

# The Coozila! APPS Library

Popular applications, provided by [Coozila!](https://coozila.com), containerized and ready to launch.

## Why use Coozila! Images?

* Coozila! closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Coozila! images the latest bug fixes and features are available as soon as possible.
* Coozila! apps, virtual machines, and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* Coozila! apps images are released regularly with the latest distribution packages available.

## Get an image

The recommended way to get any of the Coozila! Images is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/coozila/).

```console
docker pull coozila/app
```

To use a specific version, you can pull a versioned tag.

```console
docker pull coozila/app:[TAG]
```

If you wish, you can also build the image yourself by cloning the repository, changing to the directory containing the Dockerfile, and executing the `docker build` command.

```console
git clone https://github.com/coozila/apps.git
cd apps/app
docker build -t coozila/app .
```

> [!TIP]
> Remember to replace the `app` placeholders in the example command above with the correct values.

## Run the application using Docker Compose

The main folder of each application contains a functional `docker-compose.yml` file. Run the application using it as shown below:

```console
curl -sSL https://raw.githubusercontent.com/coozila/apps/main/APP/docker-compose.yml > docker-compose.yml
docker-compose up -d
```

> [!TIP]
> Remember to replace the `APP` placeholder in the example command above with the correct value.
