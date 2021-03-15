# Dockerfile for playwright-python on raspberry pi 4

This dockerfile demonstrate how to install playwright-python on raspberry pi 4. 

I tested it only on ubuntu 20.04 64bits on rpi4. It may work on other raspberries.

## Run it

```bash
# Build the image
docker build --pull --rm -t playwrightrpi4:latest "."

# Run it
docker run --rm -it  playwrightrpi4:latest
# it should show playwright webpage title:
# Fast and reliable end-to-end testing for modern web apps | Playwright
```

## Install Playwright outside of docker

1. You need to download playwright package manually as shown in the dockerfile because there is no version for arm and if you use the `pip install playwright` command, it will download you an old version.
2. You need to install chromium. It may be available as a package depending on your distribution. On ubuntu 20.04, use `sudo apt-get install chromium-browser`. It will be installed as a snap.
3. You need to install node. `sudo apt-get install nodejs`
4. Follow the commands in dockerfile to replace the chrome and node binaries with the one you installed.