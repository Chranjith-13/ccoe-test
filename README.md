## What it does
- Query the metadata of an ec2 instance within AWS and provide a json formatted output. 
- Retrieve the value of a particular data key.

## How to install
- SSH into the instance
- Install Python 3 and git on your instance 
    - `sudo yum install python3 git`
- Clone this repository
  - `git clone https://github.com/Chranjith-13/ccoe-test.git`
- Install pipenv
  - `sudo pip3 install pipenv`
- Open the repository on your instance
  - `cd ccoe-test/ec2-meta-data`
- Install project dependancies
  - `pipenv install`


## How to run
- Open the `src` folder
  - `cd ccoe-test/ec2-meta-data/src`
- Run whichever script you need:
  - `python3 get_metadata.py`
  - `python3 get_key.py`

## How it works
- It makes use of the http://169.254.169.254/latest/meta-data link-local address. Instance metatada is provided at this link, but only when you visit it from a running instance.
- A few simple Python scripts are used to extract the required information using the above API.
