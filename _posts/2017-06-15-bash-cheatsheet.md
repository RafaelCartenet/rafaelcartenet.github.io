---
layout: single
title:  "Bash"
date:   2017-06-15 20:16:01 -0600
author_profile: true
excerpt_separator: "<!--more-->"
header:
  overlay_image: /images/paris.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
---

This is a bash cheatsheet I created when I got my hands on server remote control, process handling etc.

<!--more-->


## GPU related

Find out the models of the GPUs
```sh
$ lspci | grep -i --color 'vga\|3d\|2d'
```

Get GPUs status
```sh
$ nvidia-smi
```

htop:
```sh
$ htop
```

## Processes handling

Check the processes running
```sh
$ ps aux | grep X (example: ps aux | grep apt)
```

Kill a process using its PID
```sh
$ kill -9 PID
```

## Remote control

Copy from local to ssh, from ssh to local
```sh
$ scp (-r) chemin/fichier login@serveur:chemin
$ scp (-r) login@serveur:chemin/file chemin/
```

Atom Remote, open distant folder on Atom
```sh
$ ssh -R 52698:localhost:52698 rafaelcartenet@143.248.39.104
```

Download content from the given url
```sh
$ wget URL
```

History of all different ssh commands used
```sh
$ history | grep ssh
```

Call command ID
```sh
$ !idcommand
```

## Unzip

Unzip tar files
```sh
$ tar -xvf file.tar
```

Unzip tar.gz files
```sh
$ tar zxvf file.tar.gz
```

# Other

Number of files in a repository/file
```sh
$ ls -1 | wc -l
$ wc -l <filename>
```
