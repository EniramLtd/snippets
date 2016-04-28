Building pandoc for CentOS 6.x
==============================

CentOS 6 provides pandoc 1.9.4.1 in the EPEL_ repositories.
It can be installed with::

    yum install -y epel-release
    yum install -y pandoc

Unfortunately that version of pandoc is rather old.
A newer version can be built relatively easily
using a CentOS 6 Haskell Docker image and cabal::

    docker pull dimchansky/centos6-haskell
    docker run --rm -it dimchansky/centos6-haskell bash
    cabal update
    cabal install --disable-executable-dynamic pandoc

Then while still having the Docker container running,
copy the compiled binary on the host machine::

    docker cp <container name>:/root/.cabal/bin/pandoc ./
    
.. _EPEL: https://fedoraproject.org/wiki/EPEL
