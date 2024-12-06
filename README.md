# Dockerfile Bug: Missing WORKDIR
This repository demonstrates a common error in Dockerfiles: omitting the `WORKDIR` instruction. This can lead to unexpected behavior during the build and runtime of your container, primarily due to incorrect file paths.

## Bug Description
The provided `Dockerfile` attempts to copy files and execute a Python script. However, without specifying a working directory, the paths used in `COPY` and `CMD` are relative to the root of the container's filesystem, leading to errors.

## Solution
The corrected `Dockerfile` includes the `WORKDIR` instruction to set a working directory within the container. This ensures that relative paths within the Dockerfile are correctly interpreted.