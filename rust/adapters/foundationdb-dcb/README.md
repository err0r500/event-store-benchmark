# foundationdb-dcb adapter

## ARM Docker image

The `foundationdb/foundationdb:7.4.5-arm` image is not published to Docker Hub and must be built locally:

```sh
git clone https://github.com/apple/foundationdb.git
cd foundationdb/packaging/docker

docker build --build-arg FDB_VERSION=7.4.5 \
    -t foundationdb/foundationdb:7.4.5-arm \
    --target=foundationdb .
```

## building on Apple Silicon
put this in `.cargo/config.toml`

```
[target.aarch64-apple-darwin]
rustflags = ["-L", "native=/usr/local/lib", "-C", "link-args=-Wl,-rpath,/usr/local/lib"]
```
