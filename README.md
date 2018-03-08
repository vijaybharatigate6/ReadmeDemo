# poolagency
![poolagency logo](http://dashboard.tritontracking.com:5000/static/admin/resources/images/triton-logo.png)


At Pool Agency, we’re committed to the highest quality of service and reliability. Our modern approach to pool care includes the latest tracking technology, a GPS-tracked fleet of trucks, before and after photos of every job and the best mobile dispatch software in the industry. We carefully monitor each job to offer you instant feedback and keep quality high. From weekly maintenance and repair to remodeling, our one-stop shop offers services to both residential and commercial locations.


### Quick Start

1. Clone the repo
  ```
  $ git clone https://github.com/gate6/poolagency.git
  $ cd poolagency
  ```

2. Install the dependencies:
  ```
  $ pip install -r requirements.txt
  ```

3. Run the development server:
  ```
  $ python src/api.py
  ```

6. Navigate to [http://localhost:5000](http://localhost:5000)


### Run Project

Once all the settings of project are configured you are ready to run your project. To start api project just execute below command in api root folder


To start project in debug mode :

```shell
python src/api.py
```

To run project with nohup in forever mode:

```shell
nohup python src/api.py
```

Above command will start your  project on the port you have mentioned in [`config.py`]
(https://github.com/gate6/poolagency/blob/master/src/config.py) which is 5000 as per above example.
So if you have setup project on your local machine API will be accessed via url [`http://localhost:5000`] 
(http://localhost:5000).
```shell
if not MODE or MODE is None:
   print('app is running on default mode')
   MODE = 'local'
```

Installation
================

First clone this repository or download code on machine where you would like to setup poolagency API.

1)Flask
----------
### Before we get started buildling with flask we need to setup our development environment. 

1. Install Python
2. Install virtualenv
3. Install virtualenvwrapper or virtualenvwrapper-win
4. Create a virtual environment 
5. Install flask 
6. Run our flask project
 

### 1. Install Python

[Windows](http://timmyreilly.azurewebsites.net/python-flask-windows-development-environment-setup/)

[Mac](http://docs.python-guide.org/en/latest/starting/install/osx/)

[Linux](https://docs.aws.amazon.com/cli/latest/userguide/awscli-install-linux-python.html)

### 2. Install virtualenv

```
$ pip install virtualenv
```

### 3. Install virtualenvwrapper or virtualenvwrapper-win

virtualenv wrappers make it easy to manage multiple environments and can make iterating on project easy. 


[Windows](http://timmyreilly.azurewebsites.net/python-flask-windows-development-environment-setup/)

``` 
C:\ pip install virtualenvwrapper-win  
```


[Mac](http://docs.python-guide.org/en/latest/dev/virtualenvs/)

```
$ pip install virtualenvwrapper 
$ export WORKON_HOME=~/Envs 
$ source /usr/local/bin/virtualenvwrapper.sh 
```

### 4. Create a virtual environment

```
$ mkvirtualenv venv
```
deavtivate environment
```
$ deavtivate 
```
workon that environment
```
$workon venv
```

EXTRA: link directory to virtualenv 
```
$ setprojectdir .

$ deactivate

$ workon helloworld
```

Before moving forward -  Make sure you're virtualenv is activated. Should look like this: 

```
(venv) path\to\something\like\your\project$ 
```


### 5. Install flask

Now we need [flask](http://flask.pocoo.org/) for our first website!

```
$ pip install flask
```


### 6. Run our flask project
```
$ python hello.py
 * Running on http://localhost:5000/
```


2)Flask-MySQLdb
----------



Flask-MySQLdb provides MySQL connection for Flask.

### Quickstart


First, install Flask-MySQLdb:
    
    $ pip install flask-mysqldb
    
Flask-MySQLdb depends, and will install for you, recent versions of Flask
(0.10.1 or later) and [mysqlclient](https://github.com/PyMySQL/mysqlclient-python). Flask-MySQLdb is compatible
with and tested on Python 2.7, 3.4, 3.5 and 3.6.

Next, add a ``MySQL`` instance to your code:

```python
from flask import Flask
from flask_mysqldb import MySQL

app = Flask(__name__)
mysql = MySQL(app)


@app.route('/')
def users():
    cur = mysql.connection.cursor()
    cur.execute('''SELECT user, host FROM mysql.user''')
    rv = cur.fetchall()
    return str(rv)

if __name__ == '__main__':
    app.run(debug=True)
```

### Why

Why would you want to use this extension versus just using MySQLdb by itself? The only reason is that the extension was made using Flask's best pratices in relation to resources that need caching on the [app context](http://flask.pocoo.org/docs/0.12/appcontext/#context-usage). What that means is that the extension will manage creating and teardown the connection to MySQL for you while with if you were just using MySQLdb you would have to do it yourself.


### Resources


- [Documentation](http://flask-mysqldb.readthedocs.org/en/latest/)
- [PyPI](https://pypi.python.org/pypi/Flask-MySQLdb)


Support
================
If you face any problem or issue in configuration or usage of poolagency  project as per the instruction documented above, Please feel free to communicate with poolagency Development Team.

