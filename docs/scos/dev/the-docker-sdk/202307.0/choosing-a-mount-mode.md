---
title: Choosing a mount mode
description: Learn about supported mount modes and how to choose one.
last_updated: Jun 16, 2021
template: howto-guide-template
originalLink: https://documentation.spryker.com/2021080/docs/choosing-a-mount-mode
originalArticleId: b5accb12-910a-4958-b39f-3c4d21d96b95
redirect_from:
  - /2021080/docs/choosing-a-mount-mode
  - /2021080/docs/en/choosing-a-mount-mode
  - /docs/choosing-a-mount-mode
  - /docs/en/choosing-a-mount-mode
related:
  - title: The Docker SDK
    link: docs/scos/dev/the-docker-sdk/page.version/the-docker-sdk.html
  - title: Docker SDK quick start guide
    link: docs/scos/dev/the-docker-sdk/page.version/docker-sdk-quick-start-guide.html
  - title: Docker environment infrastructure
    link: docs/scos/dev/the-docker-sdk/page.version/docker-environment-infrastructure.html
  - title: Configuring services
    link: docs/scos/dev/the-docker-sdk/page.version/configure-services.html
  - title: Docker SDK configuration reference
    link: docs/scos/dev/the-docker-sdk/page.version/docker-sdk-configuration-reference.html
  - title: Choosing a Docker SDK version
    link: docs/scos/dev/the-docker-sdk/page.version/choosing-a-docker-sdk-version.html
  - title: Configuring a mount mode
    link: docs/scos/dev/the-docker-sdk/page.version/configuring-a-mount-mode.html
  - title: Configuring access to private repositories
    link: docs/scos/dev/the-docker-sdk/page.version/configuring-access-to-private-repositories.html
  - title: Configuring debugging in Docker
    link: docs/scos/dev/the-docker-sdk/page.version/configuring-debugging-in-docker.html
  - title: Running tests with the Docker SDK
    link: docs/scos/dev/the-docker-sdk/page.version/choosing-a-docker-sdk-version.html
---

This document describes mount modes and how you can choose one.

## Selecting a mount mode for development

Depending on your operating system (OS), choose one of the mount modes in the table.

| MOUNT MODE |        MACOS            | LINUX              | WINDOWS (WSL1)          | WINDOWS (WSL2)     |
|--------------|-------------------------|--------------------|-------------------------|--------------------|
| native       | ☑️ | ✔️ | ☑️ | ✔️ |
| mutagen      | ✔️      |                    |                         |                    |
| docker-sync  | ✅      |                    | ✔️      |                    |

* (✔️) - recommended solution
* (✅) - supported solution
* (☑️) - supported solution with very slow performance

## Supported mount modes

The Docker SDK supports the following mount modes:

* baked
Copies source files into image, so they *cannot* be changed from host machine.
The file or directory is referenced by its absolute path on the host machine.
This mount mode is default for the Demo mode. It is not suitable for the application Development mode.

* native
Mounts source files directly from host machine into containers.
Works perfectly with Linux and Windows (WSL2).

* mutagen
Synchronizes source files between your host machine and a container in an effective real-time way that combines the performance of the rsync algorithm with bidirectionality and low-latency filesystem watching.
This mount mode is stable with MacOS.

* docker-sync
Synchronizes source files from host machine into running containers.
This mount mode is stable with MacOS and Windows (WSL1).



## Changing a mount mode for development

To set a mount mode, in `deploy.dev.yml`, define your OS for the desired mount mode:

```yaml
docker:

...

    mount:
        native:
            platforms:
                - linux

        docker-sync:
            platforms:
                - windows

        mutagen:
            platforms:
                - macos
```

{% info_block infoBox "Multiple mount modes" %}

If the same OS is defined for multiple mount modes, the first mount mode matching the OS in descending order is selected.

{% endinfo_block %}

## Configuring a mount mode

To configure a mount mode, see [Configuring a mount mode](/docs/scos/dev/the-docker-sdk/{{page.version}}/configuring-a-mount-mode.html).

## Synchronization mount modes

Synchronization mount modes, such as mutagen or docker-sync, use algorithms to synchronize your code between host machine and a docker volume. This allows you to run applications at full speed avoiding file system mount latency.

![mutagen-diagram](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Installation/Spryker+in+Docker/Docker+SDK/Choosing+a+mount+mode/mutagen-diagram.png)

- Mutagen daemon listens to the host file system changes.
- Mutagen sidecar container listens to the VM file system changes.
- The daemon and the sidecar interact and update files on each side.
- Applications work with the docker volume directly, which is almost equal to a direct file system access.

### What should I keep in mind when using synchronization mount modes?

Keep the following in mind:

* When you change one or more files, it may take several seconds to synchronize them.
* When performing big file operations, like `git checkout` or `composer install`, make sure to wait for synchronization by looking at the synchronization status.
* To check synchronization session status, use `docker/sdk sync logs`. It works for mutagen and docker-sync.
* When you finish working, make sure to terminate the synchronization session by running `docker/sdk down`.

## See also

* [Manage data in Docker](https://docs.docker.com/storage/)
* [Mutagen documentation](https://mutagen.io/documentation/introduction)
* [Docker-sync documentation](https://docker-sync.readthedocs.io/)
