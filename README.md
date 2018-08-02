# rails-console-ecs
This is simple shell script for executing rails console in a ECS Task.
You can exec `rails c` command from outside of ECS Cluster by executing only one command.

## How it works

1. Run a Task using a latest Task Definition in a specific ECS Cluster
2. Get private IP by AWS CLI
3. Get docker container ID via SSH
4. Exec `rails c` command in the container via SSH
5. Stop the Task

## Usage

```
Usage:
    rails-console-ecs [options]

Options:
    -v    Version
    -c    Ecs cluster which a task runs in. use RAILS_C_ECS_CLUSTER by default
    -d    Ecs task definition. use RAILS_C_TASK_DEFINITION by default
    -e    Rails env. use RAILS_C_ENV by default
    -r    Region. use RAILS_C_REGION by default
```

## Installation

### Requirement
- [aws-cli](https://github.com/aws/aws-cli)
- [jq](https://github.com/stedolan/jq)

### Install rails-console-ecs

```shell
curl https://raw.githubusercontent.com/mnc/rails-console-ecs/master/rails-console-ecs | sudo tee /usr/bin/rails-console-ecs
sudo chmod +x /usr/bin/rails-console-ecs
```
