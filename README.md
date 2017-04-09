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
* [`0.19`, `latest` _(build-assets/Dockerfile)_](https://github.com/codycraven/docker-hugo/blob/master/build-assets/Dockerfile)

## Usage

### Setup an alias

Create an alias to run Hugo in a Docker container (to avoid lots of typing):

```bash
alias hugo='docker run --rm -it -p 1313:1313 -v $(pwd):/site -w /site codycraven/hugo'
```

Notes:

* Be sure to also place this in your .bashrc (or other relevant location) so that you will not need to redefine it each time you open a new terminal.
* If you want to use a port other than 1313 then be sure to change `-p 1313:1313` to your desired value, such as `-p 8080:8080`.
* You can pin your alias to a specific release by appending `codycraven/hugo` with the Docker tag. Example: `codycraven/hugo:0.18.1`

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

Run Hugo with [LiveReload](https://gohugo.io/extras/livereload/) on [localhost port 1313](http://localhost:1313):

```bash
hugo server --bind=0.0.0.0 -w
```

Run Hugo on a custom port (be sure to change your alias to match the port) with LiveReload:

```bash
hugo server --bind=0.0.0.0 --port=8080 -w
```

### Build static files for deployment

```bash
hugo
```

## About Hugo

If you're new to Hugo, be sure to read the [Getting Started guide](https://gohugo.io/overview/introduction/). There's more you'll need to know about Hugo to effectively make use of it, such as installing/creating a theme.

This project is not involved with the Hugo project in any way. I simply love using Docker for managing my tools and love Hugo's flexibility and performance.

Lastly, if you browse the source of this repo, you'll notice there are files within the build-assets directory. The [Dockerfile](build-assets/Dockerfile) was written by me, [Cody Craven](https://github.com/codycraven). All other assets in that directory are from the [latest release of Hugo](https://github.com/spf13/hugo/releases). These assets are used by [Docker Hub](https://hub.docker.com/r/codycraven/hugo/) to automatically build the `latest` tag for the Docker image.
