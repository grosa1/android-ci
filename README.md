<a href="https://hub.docker.com/repository/docker/grosa1/ionic-android-ci">
        <img src="https://img.shields.io/docker/pulls/grosa1/ionic-android-ci.svg?style=flat-square&color=brightgreen&logo=docker&logoColor=white"
            alt="Pulls"></a> 

## Docker Image for Ionic Android CI
Docker image based on seanghay/android-ci for Ionic Android CI pipelines.

## Latest version:
```sh
docker pull grosa1/ionic-android-ci:latest
```

## Usage in GitLab CI

```
image: grosa1/ionic-android-ci
    
stages:
    - build

assembleDebug:
    stage: build
    script:
        - npm install
        - ionic cordova build android
        - cp platforms/android/app/build/outputs/apk/debug/app-debug.apk app-debug.apk
    artifacts:
        paths:
            - app-debug.apk
        expire_in: 3 day
    only:
        - master
```
