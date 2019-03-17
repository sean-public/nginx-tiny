# nginx-tiny docker image

Built-from-source container image of the [NGINX HTTP server](https://nginx.org/). 

```
docker pull seanpublic/nginx:tiny
```



Based on [`ricardbejarano/nginx`](https://hub.docker.com/r/ricardbejarano/nginx), which I couldn't get to build due to errors and wanted to shrink even further. This is not for use in environments or circumstances where there's a chance you'll want to easily debug the running process because the binary has been stripped of symbols.



### Features

- Very small container: **3.2MB**. Compare: `nginx:1.15-alpine` at 16.1MB and  `ricardbejarano/nginx` is 12.3MB.
- Uses [musl](https://www.musl-libc.org/) in place of glibc
- Strips and compresses `nginx` binary
- Produces from scratch (no OS) container using Alpine Linux interim to build
- Built from verified sources, including libraries with Position-Independent Code (`-fPIC`)
- Reduced attack surface (no `bash`, no UNIX tools, no package manager...)

