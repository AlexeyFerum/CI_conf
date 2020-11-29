# CI_conf
In this task, I set up a local GitLab instance and applied it to build a CI for the project. 
Used docker executors, CI contains three stages: build, test, package. Project to build CI for is Godot engine

The '.gitlab-ci.yml' configuration file can be used to build, test and zip the linux binary from the 'master' branch of the Godot repository.
The runner can be registered with the command 'sudo docker exec -i task2_runner_1 gitlab-runner register'.

To allow executors inside the runner to be able to communicate with GitLab that the runner to be able to communicate with GitLab the 'network_mode = "gitlab_network"' parameter should be added in the 'gitlab-runner/config.toml' file. 
This can be done by adding the 'network_mode = "gitlab-network"' parameter after the runner is registered, by supplying the '--docker-network-mode gitlab-network' parameter to the register command, by supplying the '--template-config template-config.toml' parameter to the register command and adding the 'network_mode = "gitlab-network"' parameter in the 'template-config.toml' file.

In the result the 'gitlab-runner/config.toml' file should contain network_mode = "gitlab-network".
