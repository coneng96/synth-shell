![synth-shell](doc/synth-shell.jpg)


**synth-shell**  improves your terminal experience and productivity through a 
combination of small bash scripts.


- **System status report**:
  - Automatically printed in new terminal sessions (local, SSH, ...).
  - Monitor your servers, RaspberryPis, and workstations. All system info you
    need at a glance (e.g. external IP address, CPU temperature, etc.).
  - Detect broken services or CPU hogs.
  - Print your own ASCII logo every time you log in.

- **Fancy bash prompt**:
  - Configurable colors and aesthetics.
  - Git statuses (requires pull/push, is dirty, etc.) if inside a directory that
    is part of a git repository.
  - Better separation between user input and command outputs.
  
- **More coming soon...**


All features are optional during installation and you can configure their 
behaviour. Once set up, they are simply called from within you `.bashrc` file, 
so they become part of any new session. You can find more details and similar 
tools on [Yet Another Linux'n Electronics Blog](https://yalneb.blogspot.com/).



<br/><br/>



<!--------------------------------------+-------------------------------------->
#                                     Setup
<!--------------------------------------+-------------------------------------->

### Automatic setup

The included [setup script](setup.sh) will guide you step by step through the
process and let you choose what features to install. During the setup, you can
choose to install synth-shell for your user only (recommended) or system-wide
(superuser privileges required). To proceed,
[open and play this link in a separate tab](https://www.youtube.com/embed/MpN91wHAr1k)
and enter the following into your terminal or telnet session:
```
git clone --recursive https://github.com/andresgongora/synth-shell.git
chmod +x synth-shell/setup.sh
synth-shell/setup.sh
```

Once done, you can fire up a new terminal and enjoy the result. Note that for
`fancy-bash-prompt.sh` you might also need
[power-line fonts](https://github.com/powerline/fonts). You can instal it
as follows (the exact name of the package varies from distro to distro):

* ArchLinux: `sudo pacman -S powerline-fonts`
* Debian/Ubuntu: `sudo apt install fonts-powerline`

Finally, open up a new terminal and test that everything works. Sometimes,
despite power-line fonts being properly installed, the triangle separator is
still not shown. In this case, make sure that your `locale` is set to UTF-8 by
editing `/etc/locale.conf` file (select your language but in UTF-8 format) and
running `sudo locale-gen`.
[More info on locale](https://wiki.archlinux.org/index.php/locale).



### Configuration/customization
You can configure your scripts by modifying the corresponding configuration
files. In addition to said files, you can also find configuration examples
in the following folders depending on how you installed **synth-shell**:

* Current user only: `~/.config/synth-shell/`
* System wide: `~/etc/synth-shell/`



### Uninstallation
It's hard to say goodbye, but we had good times together, didn't we? :) 
Just run the setup script again as if to install it, 
but choose `uninstall` when prompted.



<br/><br/>



<!--------------------------------------+-------------------------------------->
#                                    Overview
<!--------------------------------------+-------------------------------------->

![Example with status.sh and fancy-bash-prompt.sh](doc/screenshot.png)


### status.sh
`status.sh` provides a summarized system report at a single glance every time
you open up a new terminal. If it detects that any system parameter
(e.g. CPU load, memory, etc.) is over a critical threshold, it will provide a
warning and additional information about the cause. Last but not least, it
prints a user-configurable ASCII logo to impress your crush from the library
with how awesome you are.

Feel free to customize your status report through the many available options
in `~/.config/synth-shell/status.config` (user-only install) or
`/etc/synth-shell/status.config` (system-wide install),or by replacing their
content with the examples files you can find under the same directory.

![status configuration options](doc/status_config_preview.png)



### fancy-bash-prompt.sh
Adds colors and triangular separators to your bash prompt, and if the current
working directory is part of a git repository, also git statuses and branches.
For best results, consider installing (and telling your terminal to use) 
the `hack-ttf` font alongside the powerline-fonts (the later is required for
the separators).

As for the git status info, `fancy-bash-prompt.sh` prints an additional, fourth 
separator with the name of the current branch and one of the following icons
to indicate the state of the repository (can be changed in the config file):

|                                    | Local branch has no changes | Local branch is dirty |
|------------------------------------|:---------------------------:|:---------------------:|
|                         Up to date |                             |           !           |
|           Ahead of upstream (push) |              △              |           ▲           |
|          Behind of upstream (pull) |              ▽              |           ▼           |
| Diverged from upstream (pull-push) |              ○              |           ●           |



<br/><br/>



<!--------------------------------------+-------------------------------------->
#                                   Contribute
<!--------------------------------------+-------------------------------------->

This project is only possible thanks to the effort and passion of many, 
including developers, testers, and of course, our beloved coffee vending machine.
You can find a detailed list of everyone involved in the development
in [AUTHORS.md](AUTHORS.md). Thanks to all of you!

If you like this project and want to contribute, you are most welcome to do so.



### Help us improve

* [Report a bug](https://github.com/andresgongora/synth-shell/issues/new/choose): 
  if you notice that something is not right, tell us. We'll try to fix it ASAP.
* Suggest an idea you would like to see in the next release: send us
  and email or open an [issue](https://github.com/andresgongora/synth-shell/issues)!
* Become a developer: fork this repo and become an active developer!
  Take a look at the [issues](https://github.com/andresgongora/synth-shell/issues)
  for suggestions of where to start. Also, take a look at our 
  [coding style](coding_style.md).



### Git branches

There are two branches in this repository:

* **master**: this is the main branch, and thus contains fully functional 
  scripts. When you want to use the scripts as a _user_, 
  this is the branch you want to clone or download.
* **develop**: this branch contains all the new features and most recent 
  contributions. It is always _stable_, in the sense that you can use it
  without major inconveniences. 
  However, it's very prone to undetected bugs and it might be subject to major
  unannounced changes. If you want to contribute, this is the branch 
  you should pull-request to.



<br/><br/>



<!--------------------------------------+-------------------------------------->
#                                     About
<!--------------------------------------+-------------------------------------->

**synth-shell** started as a loose collection of (very simple) bash scripts I 
used for system maintenance. In the beginning, they were simple aids to make my 
life easier, but as I progressively got the hang out of bash, I also wanted them
to print some nice output to the terminal.

Naturally, it didn't start the way you see it today. The content of most scripts
were loose snippets from third parties that were somehow smashed together. They
worked, but not exactly the way I wanted. So, over time I have rewritten all
scripts from scratch, removed fluff, and teamed up with super-friendly and
engaged [contributors](AUTHORS.md). The result is what you see today.
I admit it, it's nothing fancy, but writing these scripts provided me with
lots of joy.

And the name? That's quite easy. I spent most of my coding frenzy
listening to [SynthWave](https://en.wikipedia.org/wiki/Synthwave) to feel like
[Hackerman](https://www.youtube.com/watch?v=KEkrWRHCDQU).



<br/><br/>



<!--------------------------------------+-------------------------------------->
#                                    License
<!--------------------------------------+-------------------------------------->

Copyright (c) 2014-2020, Andres Gongora - www.andresgongora.com

* This software is released under a GPLv3 license.
  Read [license-GPLv3.txt](LICENSE),
  or if not present, <http://www.gnu.org/licenses/>.
* If you need a closed-source version of this software
  for commercial purposes, please contact the [authors](AUTHORS.md).

