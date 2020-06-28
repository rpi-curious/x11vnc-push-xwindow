# X11vnc Push XWindow
[heading__top]:
  #x11vnc-push-xwindow
  "&#x2B06; Pushes/mirrors selected XWindow to remote via SSH port forwarding"


Pushes/mirrors selected XWindow to remote via SSH port forwarding


## [![Byte size of X11vnc Push XWindow][badge__main__x11vnc_push_xwindow__source_code]][x11vnc_push_xwindow__main__source_code] [![Open Issues][badge__issues__x11vnc_push_xwindow]][issues__x11vnc_push_xwindow] [![Open Pull Requests][badge__pull_requests__x11vnc_push_xwindow]][pull_requests__x11vnc_push_xwindow] [![Latest commits][badge__commits__x11vnc_push_xwindow__main]][commits__x11vnc_push_xwindow__main]



------


- [:arrow_up: Top of Document][heading__top]

- [:building_construction: Requirements][heading__requirements]

- [:zap: Quick Start][heading__quick_start]

- [&#x1F9F0; Usage][heading__usage]

- [&#x1F5D2; Notes][heading__notes]

- [:card_index: Attribution][heading__attribution]

- [:balance_scale: Licensing][heading__license]


------



## Requirements
[heading__requirements]:
  #requirements
  "&#x1F3D7; Prerequisites and/or dependencies that this project needs to function properly"


By default remote(s) should have `vncviewer` installed to display forwarded XWindow sessions from x11vnc, eg...


```Bash
ssh raspberrypi <<'EOF'
sudo apt-get update && {
  sudo apt-get install vncviewer
}
EOF
```


This repository makes use of Git Submodules for tracking dependencies, please use the `--recurse-submodules` option to ensure a complete download when cloning, eg...


```Bash
git clone --recurse-submodules git@github.com:rpi-curious/x11vnc-push-xwindow.git
```


To update tracked Git Submodules issue the following commands...


```Bash
git pull

git submodule update --init --merge --recursive
```


To force upgrade of Git Submodules...


```Bash
git submodule update --init --merge --recursive --remote
```


> Note, forcing and update of Git Submodule tracked dependencies may cause instabilities and/or merge conflicts; if however everything operates as expected after such an update, then please consider submitting a Pull Request.


___


## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


Make a directory path for organizing Git repositories...


```Bash
mkdir -vp ~/git/hub/rpi-curious
```


Change current working directory...


```Bash
cd ~/git/hub/rpi-curious
```


Clone this repository...


```Bash
git clone --recurse-submodules git@github.com:rpi-curious/x11vnc-push-xwindow.git
```


Change current working directory to the root of this repository...


```Bash
cd ~/git/hub/rpi-curious/x11vnc-push-xwindow
```


Install the `x11vnc-push-xwindow` script via a symbolic link to a _`PATH`_ accessible directory, eg...


```Bash
mkdir ~/bin

ln -s "${PWD}/x11vnc-push-xwindow" "${HOME}/bin/"
```


___


## Usage
[heading__usage]:
  #usage
  "&#x1F9F0;"


Print help documentation with the `--help` option...


```Bash
x11vnc-push-xwindow --help
```


Forward a local XWindow session to remote SSH host...


```Bash
x11vnc-push-xwindow raspberrypi
```


... click on the XWindow to forward.


Note, above command assumes configurations within your local SSH config file similar to the following...


**`~/.ssh/config` (snip)**


```
Host raspberrypi
   IdentitiesOnly yes
   IdentityFile ~/.ssh/id_rsa
   HostName 192.168.0.5
   User pi
```


To forward entire XWindows session instead of a target window run the `x11vnc-push-xwindow` script with `--id=none`, eg...


```Bash
x11vnc-push-xwindow --id='none' raspberrypi
```


___


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional things to keep in mind when developing"


The `failure` trap will be triggered when forwarding/mirroring is exited, currently this is _normal_/_expected_ behavior.


This repository may not be feature complete and/or fully functional, Pull Requests that add features or fix bugs are certainly welcomed.


- [Fork][x11vnc_push_xwindow__fork_it] this repository to an account that you have write permissions for.

- Add remote for fork URL. The URL syntax is _`git@github.com:<NAME>/<REPO>.git`_...


```Bash
cd ~/git/hub/rpi-curious/x11vnc-push-xwindow

git remote add fork git@github.com:<NAME>/x11vnc-push-xwindow.git
```


- Commit your changes and push to your fork, eg. to fix an issue...


```Bash
cd ~/git/hub/rpi-curious/x11vnc-push-xwindow


git commit -F- <<'EOF'
:bug: Fixes #42 Issue



**Edits**


- `<SCRIPT-NAME>` script, fixes some bug reported in issue
EOF


git push fork main
```


> Note, the `-u` option may be used to set `fork` as the default remote, eg. _`git push fork main`_ however, this will also default the `fork` remote for pulling from too! Meaning that pulling updates from `origin` must be done explicitly, eg. _`git pull origin main`_


- Then on GitHub submit a Pull Request through the Web-UI, the URL syntax is _`https://github.com/<NAME>/<REPO>/pull/new/<BRANCH>`_


> Note; to decrease the chances of your Pull Request needing modifications before being accepted, please check the [dot-github](https://github.com/rpi-curious/.github) repository for detailed contributing guidelines.


___


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


- [GitHub -- `github-utilities/make-readme`](https://github.com/github-utilities/make-readme)


___


## License
[heading__license]:
  #license
  "&#x2696; Legal side of Open Source"


```
Pushes/mirrors selected XWindow to remote via SSH port forwarding
Copyright (C) 2020 S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

```


For further details review full length version of [AGPL-3.0][branch__current__license] License.



[branch__current__license]:
  /LICENSE
  "&#x2696; Full length version of AGPL-3.0 License"


[badge__commits__x11vnc_push_xwindow__main]:
  https://img.shields.io/github/last-commit/rpi-curious/x11vnc-push-xwindow/main.svg

[commits__x11vnc_push_xwindow__main]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/commits/main
  "&#x1F4DD; History of changes on this branch"


[x11vnc_push_xwindow__community]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/community
  "&#x1F331; Dedicated to functioning code"

[x11vnc_push_xwindow__gh_pages]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/tree/
  "Source code examples hosted thanks to GitHub Pages!"

[badge__gh_pages__x11vnc_push_xwindow]:
  https://img.shields.io/website/https/rpi-curious.github.io/x11vnc-push-xwindow/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[gh_pages__x11vnc_push_xwindow]:
  https://rpi-curious.github.io/x11vnc-push-xwindow/index.html
  "&#x1F52C; Check the example collection tests"

[issues__x11vnc_push_xwindow]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."

[x11vnc_push_xwindow__fork_it]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/
  "&#x1F531; Fork it!"

[pull_requests__x11vnc_push_xwindow]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"

[x11vnc_push_xwindow__main__source_code]:
  https://github.com/rpi-curious/x11vnc-push-xwindow/
  "&#x2328; Project source!"

[badge__issues__x11vnc_push_xwindow]:
  https://img.shields.io/github/issues/rpi-curious/x11vnc-push-xwindow.svg

[badge__pull_requests__x11vnc_push_xwindow]:
  https://img.shields.io/github/issues-pr/rpi-curious/x11vnc-push-xwindow.svg

[badge__main__x11vnc_push_xwindow__source_code]:
  https://img.shields.io/github/repo-size/rpi-curious/x11vnc-push-xwindow
