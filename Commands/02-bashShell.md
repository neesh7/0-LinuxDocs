## Commands
### Working with BASH Shell

```bash
# There are different types of shell in linux, the one which we are using we can check with below command.

$ echo $SHELL # list the shell we are using '$SHELL' is an environment variable.

$ cat /etc/shells # lists all available shells on systems

# BASH shell supports autocompletion using tabs, aliases and cmd history.

$ history
$ alias dt=date
$ alias upt=uptime # alias <youralias>=<command>
# making alias persistent
$ echo 'alias up=uptime' >> ~/.profile
# SWITCHING SHELL
$ sudo chsh -s /bin/sh neesh # neesh is username
$ sudo chsh -s /bin/sh $USER
```
#### Environment variables
```bash
$ env # to print all existing env variables
$ export <envVar>=<envVar_Value> # to set value of environment variables
$ export OFFICE=MICROSOFT  # example of how to set environment variables
# using export whatever variable we define is for current session only and to make our variable persistent we need to save it under /.profile or ~/.pem_environment file
$ echo 'export OFFICE=MICROSOFT' >> /home/<username>/.profile
$ echo 'export OFFICE=MICROSOFT' >> $HOME/.profile
$ echo 'export OFFICE=MICROSOFT' >> ~/.profile

$ name=neesh # simple variable assignment

```

#### Path variables
```bash
# when user issues any external command what happens shell tries to look out for path variables of that program which ultimately have the location of that program to run.

$ echo $PATH # prints overall list of path variables
$ which python # prints the path variable for python
$ which tree # if tree is not available in system it will result 'no tree in (PATH VARIABLE LIST)'

$ export PATH=$PATH:/opt/obs/bin # appening path for obs-studio into path variables list
$ which obs-studion # it will print path of obs-studion
```
#### Prompt Customizations
```bash
# Update Bob's prompt so that it displays the date as per the format below:
# Example: [Wed Apr 22]bob@caleston-lp10:~$

# Run:PS1='[\d]\u@\h:\w$' and add this to the ~/.profile file echo 'PS1="[\d]\u@\h:\w$"' >> ~/.profile
[~]$ ps1="ubuntu-server"
```

#### NOTE
```
User profile scripts, such as ~/.profile, ~/.bash_profile, ~/.bashrc, and others, are executed when a user logs in, allowing the setup of the environment according to personal preferences.

To make changes persistent in Unix-like operating systems, variables, aliases, and other configurations can be added to these profile files.

For example, to add a variable using the command line:

echo 'export MY_VARIABLE="example_value"' >> ~/.profile

This command appends the export statement to the end of the ~/.profile file, making the variable MY_VARIABLE persistent across sessions.

To add an alias, like ll for ls -l, use:

echo 'alias ll="ls -l"' >> ~/.profile
```