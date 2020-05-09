# python37-rpm
RPM build of Python 3.7.7, based on Fedora packaging

## Instructions
- prepare your RPM build environment
```
mkdir -p ~/rpmbuild/{BUILD,BUILDROOT,RPMS,SOURCES,SPECS,SRPMS}
echo "%_topdir %(echo $HOME)/rpmbuild" > ~/.rpmmacros
```

- prepare your sources
```
cp ./patches/* ~/rpmbuild/SOURCES
wget https://www.python.org/ftp/python/3.7.7/Python-3.7.7.tgz -O ~/rpmbuild/SOURCES
```
- install required package dependencies
```
sudo yum-builddep rpm/python37.spec
```

- perform your build
```
rpmbuild -ba rpm/python37.spec
```
