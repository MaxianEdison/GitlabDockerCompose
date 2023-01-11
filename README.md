# Docker compose for run Gitlab Server

A ready to use docker compose configuration for gitlab server and gitlab runner.

## Requirements

- Docker
- Docker Compose

## Usage

1. clone this repository with following command.
`$ git clone https://github.com/MaxianEdison/GitlabDockerCompose.git`

2. Run the following command
`$ cd GitlabDockerCompose && docker-compose run [-d]`
Note: if you want see logs don't use -d option otherwise use.

## Short description

- After going through the above steps, two container with names "gitlab-ce" and "gitlab-runner" 
- will be executed.(This operation may take several minutes)
- After runnung this two containers you must change password(for root user). 
- for this purpose see https://docs.gitlab.com/ee/security/reset_user_password.html

After changing root password, you can login to the Gitlab server.
Now it's time to register Gitlab Runner with help of this guide(https://docs.gitlab.com/runner/register/)
=================================================
Configuration:
Port binding in "gitlab-ce" container
      - '80:80'
      - '443:443'
      - '2222:22'
Volumes in "gitlab-ce" container
      - '/srv/gitlab/config:/etc/gitlab'
      - '/srv/gitlab/logs:/var/log/gitlab'
      - '/srv/gitlab/data:/var/opt/gitlab'
Volumes in "gitlab-runner" container
      - '/var/run/docker.sock:/var/run/docker.sock'
      - '/srv/gitlab/gitlab-runner:/etc/gitlab-runner'
And finally all containers use "gitlab" network.
