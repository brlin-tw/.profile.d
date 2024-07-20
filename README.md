# .profile.d

A decentralized user profile configuration management solution  
<https://github.com/brlin-tw/.profile.d>

\[English\] \[[台灣中文](README.zh-TW.md)\]

The .profile file in the root of the user's home directory is a configuration file that will be loaded and executed once while the user is logging in on Unix-like OSes.  It is normally used to configure the user's environment variables(including the `PATH` environment variable which is used to search the executable file of the command).

This project provides a solution to host the user's script fragments that is originally placed into the ~/.profile file in order to minimize the pollution of the OS distribution-provided version and allows reusing of the configuration fragments.

You need to create the .profile.d directory in you home directory(if it didn't exist), then place your configuration fragments in the directory under the .source.sh filename extension.  The logic in the .profile file will automatically source and execute these files.

## Features

* Supplies utility functions to install specified directory into the command search PATHs.
* If the specified directory doesn't exist or the command search PATHs already contains that directory then it won't be added, avoid unnecessary time wasted by the additional search path.

## Setup

1. Clone or download&extract this Git repository to the .profile.d directory under your home directory, ensure that the README.setup and other files are available in the ~/.profile.d directory.
1. Add the following content in the ~/.profile file:

    ```shell
    # Setup .profile.d/
    # https://github.com/brlin-tw/.profile.d
    . "${HOME}/.profile.d/README.setup"
    ```

    You need to logout and re-login your user session to make the configuration change in effect.

## Remark

The .profile file is a generic shell script, you should use [the POSIX.1-2008 specification-compliant shell script syntax](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html) to write the configuration scriptlets instead of specific shell script syntaxes like Bash.

## Licensing

GPLv3+
