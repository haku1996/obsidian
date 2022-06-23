# Usage


---
# Installation
## Docker ![:whale:](https://camo.githubusercontent.com/bb2da325a1339d5d03d779cbfbb4139ae6a54d39668852ab8aa044c1731ae127/68747470733a2f2f6769746875622e6769746875626173736574732e636f6d2f696d616765732f69636f6e732f656d6f6a692f756e69636f64652f31663433332e706e67 ":whale:")

Docker is the recommended way of installing RustScan. This is because:

-   It has a high open file descriptor limit, which is one of the [main problems](https://github.com/RustScan/RustScan/issues/40) with RustScan. Now you don't have to fiddle around trying to understand your OS.
-   It works on all systems, regardless of OS. Even Windows, which we don't officially support.
-   The Docker image uses the latest build from Cargo, our main source-of-truth package. This means that you will always be using the latest version.
-   No need to install Rust, Cargo, or Nmap.

To install Docker, [follow their guide](https://docs.docker.com/engine/install/).

**Once Docker is installed, you can either build your own image using the `Dockerfile` (alpine) provided in the repo, or alternatively, use the published Docker image like below (most convenient)**

Please see our [DockerHub](https://hub.docker.com/repository/docker/rustscan/rustscan) for further info, however, note that we have two Docker images:

```
rustscan/rustscan:alpine

rustscan/rustscan:latest
```

We strongly recommend using the `alpine` tag, as this is the latest major - stable - release of RustScan. This README uses the `alpine` image by default, however, note that the`latest` image is considered experimental.

### To get started:

Simply run this command against the IP you want to target:

`docker run -it --rm --name rustscan rustscan/rustscan:alpine <rustscan arguments here> <ip address to scan>`

Note: this will scan the Docker's localhost, not your own.

Once done, you will no longer need to re-download the image (except when RustScan updates) and can use RustScan like a normal application.

You will have to run this command every time, so we suggest aliasing it to something memorable.

`alias rustscan='docker run -it --rm --name rustscan rustscan/rustscan:alpine'`

Then we can:

`rustscan 127.0.0.1 -t 500 -b 1500 -- -A
`
### To build your own image:

Download the repo:

`git clone https://github.com/RustScan/RustScan.git`

Ensure you navigate to the download location of the repo:

`cd /path/to/download/RustScan`

Build away!

docker build -t <yourimagename> .