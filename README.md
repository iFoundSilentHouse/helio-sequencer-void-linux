# Helio Workstation  
Helio Workstation template for xbps-src.
[Link to Helio Workstation website](https://helio.fm/)

## Building from source

> **Note**
>
> *Consult void-packages [documentation][2] for more information about setting it up.*
>
> [*Quick start*][2a]

Clone and setup the void-packages repository in a work directory and:

```shell
git clone --depth=1 https://github.com/iFoundSilentHouse/helio-sequencer-void-linux.git
[[ -d void-packages/srcpkgs/helio-sequencer ]] && rm -r void-packages/srcpkgs/helio-sequencer
cp -r helio-sequencer-void-linux/void-packages/srcpkgs/helio-sequencer void-packages/srcpkgs/
cd void-packages
./xbps-src pkg helio-sequencer
```
### Installing the binary package

#### Method 1 - manual update

Download the `xbps` package from the [releases](//github.com/iFoundSilentHouse/helio-sequencer-void-linux/releases) page, index and install the package:

```shell
xbps-rindex -a *.xbps
sudo xbps-install -vR $PWD helio-sequencer
```

#### Method 2 - updates handled by xbps-install

Add the releases page as a repository:

```shell
cat << EOF > /etc/xbps.d/10-helio-sequencer.conf
repository=https://github.com/iFoundSilentHouse/helio-sequencer-void-linux/releases/latest/download/
EOF
xbps-install -Su helio-sequencer
```

First `xbps-install -S` run it will ask to import the repository key, same as [bd:18:fc:14:f9:0e:ac:78:20:35:0e:7a:2b:0f:0d:68.plist](void-packages/repo-keys/bd:18:fc:14:f9:0e:ac:78:20:35:0e:7a:2b:0f:0d:68.plist).
