# Curated Dockerfiles examples
This repository contains examples of Dockerfiles using the [best practices that docker recommends](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/). This approach allows to build a Docker image with a minimal footprint, by copying only the necessary files from the build stage to the final image and using non-root user to run the application.

For more information about multi stage builds, please refer to the [official documentation](https://docs.docker.com/develop/develop-images/multistage-build/).

# Best practices and security checks
- [ ] Use a lightweight image.
- [ ] Minimun number of layers.
- [ ] Optimize build order.
    - [ ] Install OS packages and dependencies first (cache in another image).
    - [ ] Copy library definitions first, then build.
- [ ] Multi-stage.
    - [ ] Avoid compilers.
    - [ ] Avoid caching the build process.
- [ ] Avoid using the root user.
- [ ] File permissions (when copying from the builder).
- [ ] Sort multi-line arguments.
- [ ] Exclude with dockerignore.



## Examples by language or technology
* [Java](java/)
* [Python](python/)
* [Node](node/)
* [Go](go/)
* [Rust](rust/)

# How to use these examples
Each example contains a Dockerfile and Dockerfile.old. The .old file contains simple Dockerfile without multi stage builds and the Dockerfile contains the multi stage build version. 

To build the image, you can use the following command:
``` bash
docker build -t <image_name> .
```

If you want to build the image using the old Dockerfile, you can use the following command:
``` bash
docker build -t <image_name> -f Dockerfile.old .
```

To run the image, you can use the following command:
``` bash
docker run -it <image_name>
```



# How contribute to this repository
If you want to contribute to this repository, please follow these steps:
1. Fork this repository
2. Add your example in a new folder or update an existing example (always grouped by language or technology). This example must to contain a curated dockerfile and an old version called "dockerfile.old" to exemplify the less optimized version.
4. Create a pull request with your changes

https://docs.docker.com/develop/develop-images/multistage-build/$ gpg -d sha256sums.asc | grep git-lfs-linux-amd64-v2.10.0.tar.gz | shasum -a 256 -c
