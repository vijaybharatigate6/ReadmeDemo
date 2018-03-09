# poolagency
![poolagency logo](http://dashboard.tritontracking.com:5000/static/admin/resources/images/triton-logo.png)

# poolagency REST API
Package is developed to provides RESTful webservices for creation, publishing & management of poolagency project requirements.
.Defination for various API can be found under [`route.py`]

(https://github.com/gate6/poolagency/blob/master/api/src/route.py).

Below are the steps which one needs to follow to setup API project:

## Installation
First clone this repository or download code on machine where you would like to setup poolagency API.       

#### - Clone the repo
  ```
  $ git clone https://github.com/gate6/poolagency.git
  $ cd poolagency
  ```
 
#### - Install Python

[Windows](http://timmyreilly.azurewebsites.net/python-flask-windows-development-environment-setup/),[Mac](http://docs.python-guide.org/en/latest/starting/install/osx/),[Linux](https://docs.aws.amazon.com/cli/latest/userguide/awscli-install-linux-python.html)

#### - Install requirements.txt 
 ```
  $ pip install -r requirements.txt
  ```

Above command will install all the dependencies of project.


## Configuration

Now You need to set project configuration settings such as database details, port on which server run, Payment gateway credentials etc. To do so open file 
[`config.py`] (https://github.com/gate6/poolagency/blob/master/src/config.py). It contains enviorment wise bifurcation of configuration settings,you setup project on prd,staging,test,dev,local.suppose if you are setup project on local than provide all the detailes in localhost node
like shown below:

```shell
  'local' : {
            'name' : 'Local',
            'server': 'localhost',
            'port'   : 8080,
            'serverUrl' : 'https://localhost:8080',
            'debug'  : True,
            'apiKey'  : True,
            'amount':250,
            'authorizeNet':{
                'apiLoginId': '7FfaP2r5V',
                'transactionKey': '2S5969K8fv8p5H44'
            },
            'physical_path' : 'src/static/uploads',
            'gallonValue':10000,
            'mysql' : {
                'host' : 'localhost',
                'port'  : '3306',
                'dbName': 'poolagency',
                'user'  : 'root',
                'pass'  : 'gatesix'
            },
            'smtp'  : {
                'host'  : 'smtp.gmail.com',
                'port'  : '25',
                'user'  : 'gate6.info@gate6.com',
                'pass'  : 'Goole2010A!!'
            },
            "errorEmailRecipient" : [],
            #['laxmikant.prajapati@gate6.com'],
            "invalidAddressEmailRecipient": "laxmikant.prajapati@gate6.com",
            "supportEmailAddress": "laxmikant.prajapati@gate6.com",
            'androidDownload':'http://uat.tritontracking.com/src/static/apk/poolagency.apk',
            'iosDownload':'https://itunes.apple.com/in/genre/ios/id36?mt=8',
            'sms' : {
                'account_sid': 'ACa7cc6adb6ffd187c31cde6bcc1d1037c',
                'auth_token' : 'd79e9de5b6dc55b31b0d96ba4fbcc234',
                'fromNumber': '+18603003913',
                'code':'+91'
            },
            'zenDesk': {
                'creds': {
                    'email': 'abhishek.vishwakarma@gate6.com',
                    'token': '69iRlkRCDomHNGbVaS51ppz32p4bPI97eKBu9Jct',
                    'subdomain': 'abhigate6help'
                },
                'zenDeskRequestFieldId': '360000657472'
            },
            "firebase":{
                "apiKey": "AIzaSyBhonu-1Dp61SDv47Cugh7LAn7Vo9i6skM",
                "payload": {
                    "dynamicLinkInfo": {
                        "dynamicLinkDomain": "wz2u9.app.goo.gl",
                        "link": "http://apps.gate6.com/poolagency?phoneNumber=#phoneNumber",
                        "androidInfo": {
                            "androidPackageName": "com.poolagency",
                            "androidFallbackLink": "http://apps.gate6.com/poolagency/poolagency_local.apk",
                            "androidMinPackageVersionCode": ""
                        },
                        "iosInfo": {
                            "iosBundleId": "com.gateSix.Triton",
                            "iosFallbackLink": "https://beta.itunes.apple.com/v1/app/1234178154?build=27791285",
                            "iosCustomScheme": "",
                            "iosIpadFallbackLink": "",
                            "iosIpadBundleId": "",
                            "iosAppStoreId": ""
                        }

                    },
                    "suffix": {
                        "option": "SHORT"
                    }
                }
            },
            "quickBookClientId" : "Q0QMcPwI91vTUmCwfSjhLLarPABDtJOhA03MFsCTVSlwboq2AS",
            "quickBookSecret" : "SHQ6OPbBVBzEAwZCeZEdNXcnZILsUBvjbkyFvT6c",
            'quickBookCompanyId': '123145963397929',
            'quickBookSandbox':True,
            "revoke_endpoint" : "https://developer.api/intuit.com/v2/oauth2/tokens/revoke",
            "token_endpoint" : "https://oauth.platform.intuit.com/oauth2/v1/tokens/bearer",
            "redirect_url" : "/admin/quickbook-auth",
            "cert_file" : "ssl/cert_test.pem",
            "key_file" : "ssl/key_test.pem"
        }

```



start your  project on the port you have mentioned in [`config.py`] .In below code you have to mention a mode which you have to use or setup project on prd,staging,test,dev,local

```shell
if not MODE or MODE is None:
   print('app is running on default mode')
   MODE = 'local'
```


## Run Project

Once all the settings of project are configured you are ready to run your project. To start api project just execute below command in api root folder

To start project in debug mode :

```shell
python src/api.py
```

To run project with nohup in forever mode:

```shell
nohup python src/api.py
```


Above command will start your node API project on the port you have mentioned in [`config.py`] (https://github.com/gate6/poolagency/blob/master/src/config.py) .
So if you have setup project on your local machine API will be accessed via url [`http://localhost:8080`] (http://localhost:8080).







## Web Configuration



In web we use angular & to start on the port you have mentioned in [`config.js`] .In below code you have to mention a mode which you have to use in that as prd,staging,test,dev,localhost
(https://github.com/gate6/poolagency/blob/master/src/static/admin/scripts/config.js).

```shell
 localhost: {
    text: "Localhost",
    server: "https://localhost:8080",
    socketServer: "https://localhost:8080",
    serverKeyName: "",
    serverKey: "",
    serverTokenName: "",
    serverToken: "",
    authorizeApiLoginId: "7FfaP2r5V",
    authorizeClientKey:
      "99kzR6YCX74Tkg2j3UuRzmV93y8Jd5682U6Vg8w6wU3YJm5vUrNEs8a2HqnhJFhK",
    googleAnalyticKey: "UA-97703495-1",
    quickBookClientId: "Q0QMcPwI91vTUmCwfSjhLLarPABDtJOhA03MFsCTVSlwboq2AS",
    quickBookSecret: "SHQ6OPbBVBzEAwZCeZEdNXcnZILsUBvjbkyFvT6c",
    redirectUrl: "/admin/quickbook-auth"
  },

MODE = 'localhost'
currEnvironment: MODE
   
```

## Folder structure


api/
├── src/
│   ├── controllers/                            (include  main api functions)
│   ├── helper/                                 (include commonly used helper functions)
│   ├── library/                                (include custom libraries files such as mysql)
|   ├── model/                                  (include database entities files)
│   ├── logs/                                   (include logs files)
|   └── swagger/                                (api documentation)
|   └── quickbooks/                             (to generate the invoic)
|   └── static/                                 (public folder)
|   └── api.py
|   └── config.py
|   └── route.py
|   └── views.py
|
├── logs/ (include logs files)
|
├── ssl/(certificate)
|
├── tests/(testcases)


 .
   ├── build                   # Compiled files (alternatively `dist`)
   ├── docs                    # Documentation files (alternatively `doc`)
   ├── src                     # Source files (alternatively `lib` or `app`)
   ├── test                    # Automated tests (alternatively `spec` or `tests`)
   ├── tools                   # Tools and utilities
   ├── LICENSE
   └── README.md
## Support

If you face any problem or issue in configuration or usage of poolagency  project as per the instruction documented above, Please feel free to communicate with poolagency Development Team.

