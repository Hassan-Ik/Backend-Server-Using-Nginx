# Backend-Server-Using-Nginx

### In this repository, I am going to define a step by step process on how to deploy my Backend server on AWS EC2 using Nginx

## For AWS Linux

`sudo yum update -y` \n
`sudo yum groupinstall "Development Tools" -y`
`sudo yum install gcc openssl-devel bzip2-devel libffi-devel wget make zlib-devel xz-devel -y`

## Install Python on Linux

`cd /usr/src`
`sudo wget https://www.python.org/ftp/python/3.12.3/Python-3.12.3.tgz`
`sudo tar xvf Python-3.12.3.tgz`
`cd Python-3.12.3`
`sudo ./configure --enable-optimizations`
`sudo make -j$(nproc)`
`sudo make altinstall`

### Add python based on latest updates or version you want to use

`python3.12 --version`

### Create a virtual python environment but create this venv in folder where you want to use it

`python3.12 -m venv myenv`
`source myenv/bin/activate`


