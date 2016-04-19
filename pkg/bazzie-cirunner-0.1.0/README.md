# cirunner

Manage config and installation of Gitlab CI runner

This module may be used with a simple `include ::cirunner`

===

### Table of Contents
1. [Compatibility](#compatibility)
1. [Parameters](#parameters)
1. [Examples](#sample-usage)

===

# Compatibility

This module has been tested to work on the following systems with Puppet
versions 4.x with Ruby versions 1.9.3, 2.0.0 and 2.1.0.

Operating systems:
* EL 7

===

# Limitations

The cirunner type is limited to the following executors:
* shell
* docker

# Parameters

manage_repo
-----------
Manages the Gitlab CI runner YUM repository

- *Default*: true

install_package
-----------
Manages the Gitlab CI package installation

- *Default*: true

# Parameters for cirunner type

url
-----------
The Gitlab CI url

- *Default*: undef

token
-----------
The Gitlab CI registration token

- *Default*: undef

executor
-----------
The CI runner executor (shell, docker)

- *Default*: 'shell'

docker_image
-----------
The docker image used by the docker executor

- *Default*: undef

tags
-----------
The runner tags (Used to choose witch runner to use at build time)

- *Default*: undef


## Sample usage:

``` Puppet
runner { 'testrunner':
  ensure       => present,
  url          => 'http://<gitlab.url>/ci',
  token        => '<TOKEN>',
  executor     => 'docker',
  docker_image => 'centos/latest',
  tags         => 'dockerrunner',
}
```

## Disclaimer

This module is far from complete and under development.
Feel free to contribute!