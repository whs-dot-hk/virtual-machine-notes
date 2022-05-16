# Debian

## Preseed
```sh
curl -o preseed.cfg https://www.debian.org/releases/stable/example-preseed.txt
```

## Debian 9
```sh
virt-install \
  --name debian9 \
  --memory 2048 \
  --vcpus 2 \
  --disk size=50 \
  --network=bridge:virbr0 \
  --location http://ftp.debian.org/debian/dists/stretch/main/installer-amd64 \
  --os-variant debian9 \
  --initrd-inject ./preseed.cfg \
  --extra-args="ks=file:/preseed.cfg"
```
