# Backend-Server-Using-Nginx

### In this repository, I am going to define a step by step process on how to deploy my Backend server on AWS EC2 using Nginx

## 1. For AWS Linux

`sudo yum update -y` <br/>
`sudo yum groupinstall "Development Tools" -y`<br/>
`sudo yum install gcc openssl-devel bzip2-devel libffi-devel wget make zlib-devel xz-devel -y`<br/>

## 2. Install Python on Linux

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


## 4. Adding AWS Access Keys for CLI

## Method 1: Using `aws configure` (Recommended for single profile)

1. Open Command Prompt or PowerShell as an administrator
2. Run:
   ```bash
   aws configure
   ```
3. Enter your credentials when prompted:
   - **AWS Access Key ID**: Your access key
   - **AWS Secret Access Key**: Your secret key
   - **Default region name**: e.g., `us-east-1`
   - **Default output format**: `json` (recommended)

## Method 2: Using named profiles (Recommended for multiple accounts)

1. To create a named profile:
   ```bash
   aws configure --profile profile-name
   ```
2. Enter the same information as above
3. To use this profile in commands:
   ```bash
   aws s3 ls --profile profile-name
   ```

## Method 3: Manual configuration file editing

1. Navigate to `C:\Users\YourUsername\.aws\`
2. Edit the `credentials` file:
   ```ini
   [default]
   aws_access_key_id = YOUR_ACCESS_KEY
   aws_secret_access_key = YOUR_SECRET_KEY

   [profile-name]
   aws_access_key_id = ANOTHER_ACCESS_KEY
   aws_secret_access_key = ANOTHER_SECRET_KEY
   ```
3. Edit the `config` file:
   ```ini
   [default]
   region = us-east-1
   output = json

   [profile profile-name]
   region = us-west-2
   output = json
   ```

## Method 4: Environment variables (temporary)

Set these in your session:
```bash
set AWS_ACCESS_KEY_ID=your-access-key
set AWS_SECRET_ACCESS_KEY=your-secret-key
set AWS_DEFAULT_REGION=us-east-1
```

## Verification

Test your configuration with:
```bash
aws sts get-caller-identity
```

This will show your account ID and user ARN if configured correctly.

> **Security note**: Make sure your API keys have appropriate permissions and consider using IAM roles or temporary credentials for enhanced security.


## 5. Authenticating Github profile in Linux

`git config --global user.name "Your Name"` <br/>
`git config --global user.email "your.email@example.com"` <br/>

### Clone/authenticate using token

`git clone https://github.com/username/repository.git`


