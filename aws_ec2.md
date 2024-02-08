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

If using Ubuntu, install dependencies like so

```sh
apt install -y \
  make \
  build-essential \
  libssl-dev \
  zlib1g-dev \
  libbz2-dev \
  libreadline-dev \
  libsqlite3-dev \
  wget \
  curl \
  llvm \
  libncurses5-dev \
  libncursesw5-dev \
  xz-utils \
  tk-dev \
  libffi-dev \
  liblzma-dev \
  python-openssl \
  git
```

Installing pyenv with pyenv-virtualenv
```sh
curl https://pyenv.run | bash
```

Installing a python version
```sh
pyenv install 3.10.12
```

## Git SSH keys
```sh
ssh-keygen -t ed25519 -C "your_email@example.com"
```

and add contents of `.ssh/id_ed25519.pub` to github/gitlab keys

## Install git-lfs

Note: Currently the steps below do not work for Amazon Linux. Scroll down for fix.

https://github.com/git-lfs/git-lfs/blob/main/INSTALLING.md


At the time of writing, the following command claims to successfully add the repo
```sh
curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.rpm.sh | sudo bash
```

But it fails to install the package claiming it does't exist when running
```sh
sudo yum install git-lfs
```

### Amazon Linux git-lfs

The following seems to do the trick

```sh
amazon-linux-extras install epel -y
yum-config-manager --enable epel
yum install git-lfs
```
