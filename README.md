# Python Installation Tutorial on Ubuntu

This repository contains a short guide on how to install Python 3.13 on Ubuntu from source. This method works with any arbitrary version of Python.

## Check the Current Python Version

As the first step, the current Python 3.XX version can be checked with the following command:

```bash
python3 -V
```

If the result is not the desired version, please follow the instructions below.

## Update Your System

Make sure your system is up-to-date:

```bash
sudo apt update && sudo apt upgrade
```

## Install Dependencies

Install the dependencies required for installing Python from source:

```bash
sudo apt -y install gdb lcov libbz2-dev libffi-dev libgdbm-dev libgdbm-compat-dev liblzma-dev libncurses5-dev libreadline6-dev libssl-dev lzma lzma-dev tk-dev uuid-dev zlib1g-dev gcc make pkg-config
```

## Download the Python Source Tarball

The next step is to visit the official Python website and download the necessary tarball file. First, open this link or navigate to the download page of your desired version:\
[Python 3.13](https://www.python.org/downloads/release/python-3130/)

Scroll down the page, right-click on the **XY compressed source tarball**, and select the **Copy Link** option.



Download the source tarball file using the copied link:\
**Attention: The link might be different depending on the version.**

```bash
wget https://www.python.org/ftp/python/3.13.0/Python-3.13.0.tar.xz
```

Check if the download was successful:

```bash
ls -l
```

If the desired file is visible, then the download was successful.

## Extract the Tarball

Uncompress the tarball file.\
**Attention: This command might be different depending on the version.**

```bash
tar -xvf Python-3.13.0.tar.xz
```

If the extraction was successful, a `Python-3.XX.X` folder should appear after running the following command:

```bash
ls -l
```

## Enter the Extracted Directory

Navigate into the uncompressed folder:

```bash
cd Python-3.XX.X/
```

## Configure the Source

Now configure the source:

```bash
sudo ./configure --enable-optimizations
```

## Compile the Source Code

Compile the code: (This process might take some time)

```bash
sudo make -j<processor_cores>
```

You can check the number of processor cores using:

```bash
nproc
```

## Install Python

```bash
sudo make install
```

## Verify the Installation

Check if the installation was successful:

```bash
python3.13 -V
```

If the desired version is found, the installation was successful.

## Verify pip Installation

Check if the pip installation was successful:

```bash
pip3 -V
```

If pip was found for the desired version of Python, the installation was successful.

## Set Python 3.13 as the Default Version (Optional)

Check the root of Python 3.13:

```bash
which python3.13
```

The output should be similar to:

```bash
/usr/local/bin/python3.13
```

Now run the following commands:\
**Replace **``** with the actual path on your computer.**

```bash
echo 'alias python=<root_of_python3.13>' > ~/.bash_aliases
echo 'alias python3=<root_of_python3.13>' >> ~/.bash_aliases
```

## Apply the Changes

Return to the home directory:

```bash
cd ~
```

Then run:

```bash
source ~/.bash_aliases
```

## Verify the Default Python Version

To check if the process was successful, run the following commands:

```bash
python -V
python3 -V
```

If both commands return Python 3.13.X, the process was successful.

