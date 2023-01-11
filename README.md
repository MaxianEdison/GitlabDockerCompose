# Docker compose for run Gitlab Server

A ready to use docker compose configuration for gitlab server and gitlab runner.

## Requirements

- Docker
- Docker Compose

## Usage

```
$ git clone https://github.com/MaxianEdison/GitlabDockerCompose.git

$ cd GitlabDockerCompose && docker-compose run [-d]
```

> Note: if you want see logs don't use -d option otherwise use.

## Short description

After going through the above steps, two container with names "gitlab-ce" and "gitlab-runner" will be executed(This operation may take several minutes)
After runnung this two containers you must change password(for root user) for this purpose see [this](https://docs.gitlab.com/ee/security/reset_user_password.html)

After changing root password, you can login to the Gitlab server. Now it's time to register Gitlab Runner with help of this [guide](https://docs.gitlab.com/runner/register/)
