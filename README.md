# FFmpeg with Docker

This repo contains two Dockerfiles: `Dockerfile.ffmpeg-dyn` and `Dockerfile.ffmpeg-frozen`. The former is built on `ubuntu:latest` and uses the latest FFmpeg snapshot; the latter is built on `ubuntu:24.04` and uses FFmpeg 7.1.

This exists primarily because I wanted to have available the `libfdk_aac` library (Fraunhofer FDK AAC) in other projects, such as [audiotame](https://github.com/veralvx/audiotame). It is not shipped with FFmpeg by default due to licensing issues. 

## Docker/Podman

```console
podman build -f Dockerfile.ffmpeg-frozen -t ffmpeg:7.1
```

Or, pull the image:

```console
podman pull veralvx/ffmpeg:7.1
```

Then, run it:

```console
podman run -it --rm -v $(pwd)/workspace ffmpeg:7.1
```