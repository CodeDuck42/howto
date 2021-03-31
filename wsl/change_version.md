# Change the version of a WSL container

Open a cmd or powershell prompt and run

~~~shell
wsl -l -v
~~~

The output should look something like this:

~~~text
  NAME      STATE           VERSION
* Ubuntu    Running         1
~~~

We have to make sure that the wsl is not running anymore with:

~~~shell
wsl --shutdown Ubuntu
~~~

> **Warning** The process takes a little while and needs roughly twice the space on the drive where the distribution is
> located. You might want to [move the WSL from to another location](move_to_another_location.md) first.

Switch to WSL to version 2 of the distribution with

~~~shell
wsl --set-version Ubuntu 2
~~~

Switch to WSL Version 1 of the distribution with

~~~shell
wsl --set-version Ubuntu 1
~~~
