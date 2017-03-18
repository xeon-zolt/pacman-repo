Usage
=====

Register pacman repository
---------------------

    # cat >> /etc/pacman.conf
    
    [Event-Linux]
    Server = https://raw.github.com/xeon-zolt/pacman-repo/master/repo/$arch
    # pacman -Sy


Build and add package to repository
-----------------------------------
Just use pacman repository.

### Set up

    $ git clone git@github.com:xeon-zolt/pacman-repo.git
    $ cd pacman-repo
    $ git submodule init
    $ git submodule update
    

### Build and add package
    $ cd pacman-repo
    $ cd pkgbuild
    $ yarout -G <package name>
    $ cd ..
    $ ./add_package_to_repository.pl some_package_in_pkgbuilds


### Publish

    $ cd pacman-repo
    $ git add repo
    $ git push


### Update pkgbuilds submodule

    $ cd pacman-repo
    $ git submodule foreach 'git pull origin master'
