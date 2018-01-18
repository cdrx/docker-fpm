# FPM (effing package manager) Docker Images

**cdrx/fpm-{$distro}** are a series of Docker images to quickly get packages building in fpm on different Linux distributions.

Each distro has fpm installed and all the required dependencies to build packages for that platform. All images are 64bit.

You should mount the files you want to put into your package into `/src/`.

If you need to do any complicated setup in the environment before running `fpm` then it would be best to write a bash script, mount it into `/src/` and override the containers entrypoint when you run it. `fpm` is available to run in the system path.

## Images

* Ubuntu w/ fpm
  * `cdrx/fpm-ubuntu:18.04` - bionic
  * `cdrx/fpm-ubuntu:16.04` - xenial
  * `cdrx/fpm-ubuntu:14.04` - trusty

* Debian w/ fpm
  * `cdrx/fpm-debian:8`
  * `cdrx/fpm-debian:7`

* Fedora w/ fpm
  * `cdrx/fpm-fedora:24`
  * `cdrx/fpm-fedora:23`
  * `cdrx/fpm-fedora:22`
  * `cdrx/fpm-fedora:21`
  * `cdrx/fpm-fedora:20`

* CentOS w/ fpm
  * `cdrx/fpm-centos:7`
  * `cdrx/fpm-centos:6`
  * `cdrx/fpm-centos:5`

The `:latest` tag will always point to the most recent release of the distro.

## Usage

```
docker run -v "$(pwd):/src/" cdrx/fpm-ubuntu:16.04 fpm -s dir -t deb ..
```

```
docker run -v "$(pwd):/src/" cdrx/fpm-fedora:24 fpm -s dir -t rpm ..
```
