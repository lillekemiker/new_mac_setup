## NVIDIA driver

When using a GCP deeplearning image VM, the easiest way to reinstall the NVIDIA driver is by running
```sh
sudo /opt/deeplearning/install-driver.sh
```

# Git LFS

```
sudo yum install git-lfs
git lfs install
```

# Deactivate Conda

```
conda config --set auto_activate_base false
```

## *Optional* Build and install NVtop

```
sudo apt-get install libncurses5-dev libncursesw5-dev -y
sudo apt-get install libudev-dev libsystemd-dev -y
sudo apt-get install libdrm-dev -y
git clone https://github.com/Syllo/nvtop.git
mkdir -p nvtop/build && cd nvtop/build
cmake .. -DNVIDIA_SUPPORT=ON -DAMDGPU_SUPPORT=ON -DINTEL_SUPPORT=ON
make

sudo make install
```
