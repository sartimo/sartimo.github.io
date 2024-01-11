+++
author = "Timo Sarkar"
title = "Compiling NetHack from Source"
date = "2024-01-11"
description = "Tutorial on how to compile NetHack from source on Ubuntu 22.04 LTS"
+++

First we need to clone the official git repository.

```bash
git clone https://github.com/NetHack/NetHack
```

Keep in mind. We need ```git, gcc, make, flex, bison and ncurses``` installed. Next, we can define the ```HACKDIR``` in the Hintsfile located at ./sys/unix/hints/unix.
Next we need to fetch the lua binary used for scripting within NetHack. We do this using ```make fetch-lua```. Then we need to modify the ./Makefile and the ./src/Makefile to include the NCURSES library instead of termlib.

![image](https://github.com/sartimo/sartimo.github.io/assets/71646577/dd518eb6-fed3-4a2d-a123-93149297d51b)

Now save the two Makefiles and recompile using ```make```. After that. The ```nethack``` binary is located under ./src. When you execute the binary, it will complain that SYSCNF could not be found.
We can fix this by creating an empty file named ```sysconf``` under the HACKDIR that we noticed earlier. Now you are able to run NextHack on Ubuntu 22.04 LTS. Have fun.

![image](https://github.com/sartimo/sartimo.github.io/assets/71646577/bf8e7718-4fbc-494d-a5ae-79dbaf7a71a4)
