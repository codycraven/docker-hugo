[Docker Hub](https://hub.docker.com/r/codycraven/hugo/) | [GitHub](https://github.com/codycraven/docker-hugo) | [Hugo Website](https://gohugo.io/)

## Supported tags

* `0.10`
* `0.11`
* `0.12`
* `0.13`
* `0.14`
* `0.15`
* `0.16`
* `0.17`
* `0.18`
* `0.18.1`
* `0.19`
* `0.20`
* [`0.20.1`, `latest` _(build-assets/Dockerfile)_](https://github.com/codycraven/docker-hugo/blob/master/build-assets/Dockerfile)

## Usage

### Setup aliases for dockerized Hugo

Define a couple aliases in your .bashrc (or other relevant location) to run Hugo in a Docker container.

_Note: You can pin your alias to a specific release by appending `codycraven/hugo` with the Docker tag. Example: `codycraven/hugo:0.18.1`_

#### hugo

```bash
alias hugo='docker run --rm -it \
    -v /tmp:/tmp:Z \
    -v $(pwd):/site:Z \
    -w /site \
    codycraven/hugo'
```

#### hugo-server

```bash
alias hugo-server='docker run --rm -it \
    -v /tmp:/tmp:Z \
    -v $(pwd):/site:Z -w /site \
    -p 8080:8080 \
    codycraven/hugo \
    server \
    --bind=0.0.0.0 \
    --port=8080 \
    -w'
```

_Note: To set the port of your development site, change all three instances of `8080` to whatever port you'd like to use._

### View help

```bash
hugo --help
```

### Check the version of Hugo

```bash
hugo version
```

### Create a Hugo site

```bash
hugo new site mysite
```

_This will create a new directory under your current directory with the name of `mysite`._

### Hugo server

```bash
hugo-server
```

### Build static files for deployment

```bash
hugo
```

## About Hugo

If you're new to Hugo, be sure to read the [Getting Started guide](https://gohugo.io/overview/introduction/). There's more you'll need to know about Hugo to effectively make use of it, such as installing/creating a theme.

This project is not involved with the Hugo project in any way. I simply love using Docker for managing my tools and love Hugo's flexibility and performance.

Lastly, if you browse the source of this repo, you'll notice there are files within the build-assets directory. The [Dockerfile](https://github.com/codycraven/docker-hugo/blob/master/build-assets/Dockerfile) was written by me, [Cody Craven](https://github.com/codycraven). All other assets in that directory are from the [latest release of Hugo](https://github.com/spf13/hugo/releases). These assets are used by [Docker Hub](https://hub.docker.com/r/codycraven/hugo/) to automatically build the `latest` tag for the Docker image.
