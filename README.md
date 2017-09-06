# bash
bash utilities

# install

```
curl https://raw.githubusercontent.com/Jumpscale/bash/master/install.sh?$RANDOM > /tmp/install.sh;bash /tmp/install.sh
```

# install from branch

```
export ZUTILSBRANCH=<BRANCH>
export ZBRANCH=<BRANCH>
curl https://raw.githubusercontent.com/Jumpscale/bash/${ZUTILSBRANCH}/install.sh?$RANDOM > /tmp/install.sh;bash /tmp/install.sh
```

what happens
- xcode-tools will be installed & then brew (https://brew.sh/) (osx only)
- python & jumpscale will be installed all in basic version
- ipfs will be installed to make sure all files can be retrieved locally from peer2peer network
- ssh-key will be looked for & created if it doesn't exist yet
- ZBRANCH is the target branch for js9 components, default to master

the basic init script will be added to ~/bash_profile

- when you start a new terminal the tools will be available

# to install full jumpscale on host machine
```bash
ZInstall_host_js9_full
```

# to install full jumpscale on a docker
 - To get basic jumpscale (core + lib + prefab with all their dependencies)
    ```bash
    ZInstall_js9_full
    ```
 - To get an AYS docker (core + lib + prefab + ays with all their dependencies)
    ```bash
    ZInstall_ays9
    ```
 - To get a portal as well (core + lib + prefab + ays + portal with all their dependencies)
    ```bash
    ZInstall_portal9
    ```

# to install all editor tools for local machine

```bash
ZInstaller_editor_host
```

# to get docker on ubuntu

```bash
ZDockerInstall
```

# ssh tools

```bash
#set node we will work on
ZNodeSet 192.168.10.1

#if different port
ZNodePortSet 2222

#to see which env has been set
ZNodeEnv

#to sync local install bash tools to the remote node
RSync_bash

#to remote execute something
ZEXEC ls /

#to remote execute multiple commands, do not forget the `` IMPORTANT
ZEXEC 'mkdir -p /tmp/1;mkdir -p /tmp/2'

#to remote execute something and make sure bash tools are there & loaded
ZEXEC -b ls /

```

# docker tools

```bash
~/code/jumpscale/bash/zlibs.sh
ZDockerBuildJS9 # -f to build full js9 not the minimal
ZDockerRunJS9
```

will install js9 & build docker with ubuntu 17.04 and required tools.

# to manually source the zlibs use

```
#LINUX
. /opt/code/github/jumpscale/bash/zlibs.sh

#OSX
. ~/code/github/jumpscale/bash/zlibs.sh
```

this will source all methods, codecompletion will now work.


# lede tools

```bash
#configure a remote lede box, first make sure the ZNodeSet ... is done
#will install mc, curl, git, ...
LEDE_Install


```
