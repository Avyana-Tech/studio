# Studio

Avyana Studio is a robotic visualisation tool, built for the Self Driving Car, available as web-app and would be soon available also as a desktop app for osx, linux and windows.

## RUN

To run the Studio,

clone the repo, install everything using `yarn install --immutable`, and run as follows

```sh
# To launch the desktop app (run both scripts concurrently):
$ yarn desktop:serve        # start webpack
$ yarn desktop:start        # launch electron

# To launch the browser app:
$ yarn web:serve

# To launch the browser app using a local instance of the backend server:
$ yarn web:serve:local

# To launch the storybook:
$ yarn storybook

# Advanced usage: running webpack and electron on different computers (or VMs) on the same network
$ yarn desktop:serve --host 192.168.xxx.yyy         # the address where electron can reach the webpack dev server
$ yarn dlx electron@13.0.0-beta.13 .webpack # launch the version of electron for the current computer's platform

# To launch the desktop app using production API endpoints
$ yarn desktop:serve --env FOXGLOVE_BACKEND=production
$ yarn desktop:start

# NOTE: yarn web:serve does not support connecting to the production endpoints
```

Or you can even run a dockerimage and access it on the web by

```
docker run --rm -p "8080:8080" avyana/studio:latest
```

on localhost:8080. This will run the most recent release of the docker image.

To run the latest Tag Build
```
docker run --rm -p "8080:8080: avyana/studio_tagBuild:latest
```


If you want to run the latest nightlyBuild

```
docker run --rm -p "8080:8080" avyana/studio_nb:master
```

## CONNECT

Assuming that you have already installed [Avyana-Core](https://github.com/Avyana-Tech/Avyana-Core.git) on the robot, launch Avyana Studio on the robot and follow the steps below:

    - In the *Get Started* dialog box, click on *Open Connection*.
    - In the webSocket URL tab, you can see `ws://localhost:9090`.
    - Then press Open.

If you want to run the Studio on a different computer, but in the same wifi network, launch Avyana Studio on the remote computer and follow the steps below:

    - Collect the IP address of the robot using -ifconfig.
    - In the *Get Started* dialog box, click on *Open Connection*.
    - In the webSocket URL tab, enter ` ws://ip address:9090`.
    - Then press Open.

## Notice

_AVYANA STUDIO_ is a fork of [FoxgloveStudio](https://foxglove.dev). The required LICENSE & NOTICE are provided as is. The codebase has been changed as required, but [AVYANA TECH](https://avyana.tech) does not provide warranty of any kind, and is not liable to anything.
