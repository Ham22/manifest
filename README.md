# Manifest

Manifest for cloning creator kit repositories.

#### Steps for cloning could be:
- mkdir local_dir_name
- cd local_dir_name
- repo init -u https://github.com/CreatorKit/manifest.git -b branch_name
- repo sync

After above steps, your directory structure would be like:
```
.
├── build
├── constrained-os
│   └── contiki
├── dist
│   ├── openwrt
│   ├── openwrt-ckt-feeds
|   |       ├── button-led-controller
|   |       ├── motion-led-controller
|   |       └── relay-gateway
│   └── openwrt-feeds
|   |       ├── awalwm2m
|   |       ├── board-test
|   |       ├── ca8210
|   |       ├── fping
|   |       ├── glog
|   |       ├── proddata
|   |       ├── totd
|   |       └── u-boot
└── packages
    ├── AwaLWM2M
    ├── button-sensor
    ├── motion-sensor
    ├── button-led-controller
    ├── motion-led-controller
    ├── relay-gateway
    └── libobjects
```

#### Contents
This repository contains two different manifest files :-

1. creator-kit.xml

    This is the default manifest file. This manifest has repository paths which points to their master branch. Hence it is **NOT** recommended as a stable release.
    
        repo init -u https://github.com/CreatorKit/manifest.git -b master

2. creator-release.xml

    This manifest has repository paths which points to latest stable creator kit project's release.

        repo init -u https://github.com/CreatorKit/manifest.git -b master -m creator-release.xml
    
    Above will build the latest release for you. For building any other release use :-
    
        repo init -u https://github.com/CreatorKit/manifest.git -b refs/tags/<release_tag> -m creator-release.xml

    For example,

        repo init -u https://github.com/CreatorKit/manifest.git -b refs/tags/v0.9.1 -m creator-release.xml
