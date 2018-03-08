# poolagency
![poolagency logo](http://dashboard.tritontracking.com:5000/static/admin/resources/images/triton-logo.png)


At Pool Agency, we’re committed to the highest quality of service and reliability. Our modern approach to pool care includes the latest tracking technology, a GPS-tracked fleet of trucks, before and after photos of every job and the best mobile dispatch software in the industry. We carefully monitor each job to offer you instant feedback and keep quality high. From weekly maintenance and repair to remodeling, our one-stop shop offers services to both residential and commercial locations.


## Quick Start

### 1. Clone the repo
  ```
  $ git clone https://github.com/gate6/poolagency.git
  $ cd poolagency
  ```

### 2. Install the dependencies:

First clone this repository or download code on machine where you would like to setup poolagency API.       

 
#### Install Python

[Windows](http://timmyreilly.azurewebsites.net/python-flask-windows-development-environment-setup/),[Mac](http://docs.python-guide.org/en/latest/starting/install/osx/),[Linux](https://docs.aws.amazon.com/cli/latest/userguide/awscli-install-linux-python.html)

#### Install Flask-MySQLdb
----------

Flask-MySQLdb provides MySQL connection for Flask.

##### Quickstart

First, install Flask-MySQLdb:
    
    $ pip install flask-mysqldb
    
Flask-MySQLdb depends, and will install for you, recent versions of Flask
(0.10.1 or later) and [mysqlclient](https://github.com/PyMySQL/mysqlclient-python). Flask-MySQLdb is compatible
with and tested on Python 2.7, 3.4, 3.5 and 3.6.we use here 2.7 in project.


##### Resources


- [Documentation](http://flask-mysqldb.readthedocs.org/en/latest/)
- [PyPI](https://pypi.python.org/pypi/Flask-MySQLdb)


#### Install requirements.txt 
 ```
  $ pip install -r requirements.txt
  ```
### 3. Run the development server:


To start project in debug mode :

```shell
python src/api.py
```

To run project with nohup in forever mode:

```shell
nohup python src/api.py
```


### 4. Navigate to [https://localhost:5000](http://localhost:5000)


## Configuration


start your  project on the port you have mentioned in [`config.py`] .In below code you have to mention a mode which you have to use in that as prd,staging,test,dev,local

(https://github.com/gate6/poolagency/blob/master/src/config.py).
```shell
if not MODE or MODE is None:
   print('app is running on default mode')
   MODE = 'local'
```


In frontend we use angular & to start on the port you have mentioned in [`config.js`] .In below code you have to mention a mode which you have to use in that as prd,staging,test,dev,localhost
(https://github.com/gate6/poolagency/blob/master/src/static/admin/scripts/config.js).
```shell
MODE = 'localhost'
currEnvironment: MODE
   
```


Installation
================




Support
================
If you face any problem or issue in configuration or usage of poolagency  project as per the instruction documented above, Please feel free to communicate with poolagency Development Team.

