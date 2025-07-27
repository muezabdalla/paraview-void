# paraview package for void linux

this is the unofficial repo for paraview for void linux

## Installing a release
### Installing through the repository
If you want to update paraview along with your distribution packages, just run
the following commands once:
```
$ su
# echo 'repository=https://github.com/muezabdalla/paraview-void/releases/latest/download/' > /etc/xbps.d/30-paraview.conf
# xbps-install -Su paraview
```

## Building from source
### Preparing the environment

Clone the void-packages repository:
```
$ git clone https://github.com/void-linux/void-packages
```

Change to the new `void-packages` folder and proceed to build the bootstrap:
```
$ cd void-packages
$ ./xbps-src binary-bootstrap
```

### Downloading the package

```
$ git clone https://github.com/muezabdalla/paraview-void.git
```
Once you have cloned the repository, copy the contents inside the srcpkgs folder
into the void-packages srcpkgs folder.

### Building the package

Once the bootstrap is ready, it's time to build the package with:
```
$ ./xbps-src pkg <pkgname>
```

After a while, the above step will create a binary in `hostdir/binpkgs` named
`<pkgname>-<version>_<revision>.<arch>.xbps`.

### Installing

Once the package is successfully built and in the `hostdir/binpkgs` directory
you can install it with:
```
# xbps-install -R hostdir/binpkgs <package>
```

### Keeping your environment up-to-date

Before compiling Librewolf, it is recommended that you update your environment
to ensure you have the latest changes. This involves updating your local
void-packages repository and then updating the bootstrap packages.

#### Updating the repository

Update your local void-packages repository to the latest version:
```
$ git pull origin master
```

#### Updating the bootstrap packages

Sometimes, you may need to update the bootstrap packages to the latest version
available in the repositories. To do this run:
```
$ ./xbps-src bootstrap-update
```

### thanks
special thanks to the @index-0 who I learned from his [librewolf](https://github.com/index-0/librewolf-void) repo and I still use it
