# 1. Get the image

```bash
git clone https://github.com/marcopalena/polito-os161-docker
cd polito-os161-docker-main
docker build -t os161 .
```

In this case the name of the image is `os161`

# 2. Create a named volume

This command crates a volume named `os161-vol`

```bash
docker volume create os161-vol
```

You can check all your volumes by running

```bash
docker volume list
```

# Run the container

Run the container mounting the volume `os161-vol` as the home folder of user `enf`. Make sure to to change *<imagename>* with the name of your image

```bash
docker run --volume os161-vol:/home/enf --name os161 -itd os161 /bin/bash
```

If everything went well, you should see it by running

```bash
docker ps
```

# Uninstall

If you just used docker for OS161, you can run this command safely
``` bash
docker prune -a
```
