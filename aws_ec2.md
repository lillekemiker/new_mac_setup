## Installing pyenv

If using Amazon Linux, you may need to do the following to get the right header files for compiling python using pyenv

```sh
sudo yum remove openssl-devel.x86_64
sudo yum autoremove
sudo yum install openssl11-devel
sudo yum groupinstall "Development Tools" -y && \
  sudo yum install -y \
    zlib-devel \
    bzip2 \
    bzip2-devel \
    readline-devel \
    sqlite \
    sqlite-devel \
    tk-devel \
    libffi-devel \
    xz-devel
```

Installing pyenv with pyenv-virtualenv
```sh
curl https://pyenv.run | bash
```

Installing a python version
```sh
pyenv install 3.10.12
```
