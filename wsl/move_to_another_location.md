# Move WSL container to another location

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

Now we...
- make a backup and
- remove the currently installed version and
- install it at the new location and
- delete the backup file

~~~shell
wsl --export Ubuntu d:\backup.wsl
wsl --unregister Ubuntu
wsl --import Ubuntu d:\wsl\Ubuntu d:\backup.wsl --version 1
del d:\backup.wsl
~~~

> **Tipp:**
> You can add the location of your wsl to the "Virus & threat protection settings" under "Exclusions" for enhanced
> performance.
