# chef-workstation
Управление конфигурацией Серверов [до 50 000 конфигов … на один сервер]
Но при активном участии Facebook'а, которые управляют, наверное, самой большой в мире инсталляцией Chef'а, система была переписана на Erlang + PostgreSQL.

https://sdtimes.com/opscode-unleashes-new-generation-of-chef/

“Chef 11 is a powerful automation platform that allows us to create unprecedented utility supercomputers from 50 to 50,000 cores.

Согласно заявлению Opscode, благодаря изменениям требования к оперативной памяти уменьшились в 10 раз, а масштабируемость системы увеличилась в 4 раза (до 10 000 клиентов на один сервер).

Система управления конфигурацией Chef написана на языках Ruby и Erlang, и предлагает предметно-ориентированный язык для создания инструкций ("рецептов"). Chef может применяться для централизованного изменения конфигурации и автоматизации управления приложениями (установка, обновление, удаление, запуск) в серверных парках различного размера и облачных инфраструктурах. В том числе поддерживается автоматизация развёртывания начинки новых серверов в облачных окружениях Amazon EC2, Rackspace, Google Cloud Platform, Oracle Cloud, OpenStack и Microsoft Azure. Решения на базе Chef применяются компаниями Facebook, Amazon и HP. Управляющие узлы Chef могут быть развёрнуты в дистрибутивах на основе RHEL и Ubuntu. В качестве объектов управления поддерживаются все популярные Linux-дистрибутивы, macOS, FreeBSD, AIX, Solaris и Windows.

# Chef Workstation
https://github.com/chef/chef-workstation

**Umbrella Project**: [Chef Workstation](https://github.com/chef/chef-oss-practices/blob/master/projects/chef-workstation.md)

* **[Project State](https://github.com/chef/chef-oss-practices/blob/master/repo-management/repo-states.md):** Active
* **Issues [Response Time Maximum](https://github.com/chef/chef-oss-practices/blob/master/repo-management/repo-states.md):** 14 days
* **Pull Request [Response Time Maximum](https://github.com/chef/chef-oss-practices/blob/master/repo-management/repo-states.md):** 14 days

Chef Workstation installs everything you need to get started using Chef on Windows, Mac and Linux.
It includes:
- chef-run, a new tool for executing ad-hoc tasks against your servers
- ChefDK, all the tools you know and love

## Getting Started

1. Download [Chef Workstation](https://downloads.chef.io/chef-workstation)

2. Double-click the `.dmg` or `.msi` file to start the install process, or use the package manager for your Linux distribution.

3. Open a terminal, and try out an ad-hoc task. Here's the general usage:

    `chef-run  [flags] <Target host|IP|SSH|WinRM> <Resource> <Resource Name> [properties]`

  * Install the 'ntp' package on 'hostname' over ssh, using password from the environment:

    `chef-run username:$PASSWORD@hostname package ntp`

  * Create user 'timmy' on 'hostname' over winrm:

    `chef-run winrm://username@hostname user timmy`

  * Run the recipe 'nginx::passenger' on 'hostname' over ssh on port 2222 using a keyfile:

    `chef-run ssh://hostname:2222 -i ~/.ssh/id_rsa nginx::passenger`

4. Use `chef-run -h` for additional information about usage and available flags.

## Building Chef-Workstation Packages

We use Omnibus to describe our packaging. Please review [chef-workstation/omnibus/README.MD](https://github.com/chef/chef-workstation/tree/master/omnibus) for further details.

## Copyright and License

Code released under the [Apache license](LICENSE). Images and any trademarked content are Copyright 2018 by [Chef Software, Inc.](https://www.chef.io).