# Backend-Server-Using-Nginx

### In this repository, I am going to define a step by step process on how to deploy my Backend server on AWS EC2 using Nginx

## For AWS Linux

`sudo yum update -y \n` <br/>
`sudo yum groupinstall "Development Tools" -y`<br/>
`sudo yum install gcc openssl-devel bzip2-devel libffi-devel wget make zlib-devel xz-devel -y`<br/>

## Install Python on Linux

`cd /usr/src`<br/>
`sudo wget https://www.python.org/ftp/python/3.12.3/Python-3.12.3.tgz`<br/>
`sudo tar xvf Python-3.12.3.tgz`<br/>
`cd Python-3.12.3`<br/>
`sudo ./configure --enable-optimizations`<br/>
`sudo make -j$(nproc)`<br/>
`sudo make altinstall`<br/>

### Add python based on latest updates or version you want to use

`python3.12 --version`<br/>

### Create a virtual python environment but create this venv in folder where you want to use it

`python3.12 -m venv myenv`<br/>
`source myenv/bin/activate`<br/>


