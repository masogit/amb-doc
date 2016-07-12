# AM Browser online document

AMB is a light weight UI which leverage REST APIs layer to pull data from Asset manager and simplifies the end user data consumption of ITAM data.

![Viewer screen shot](features/img/insight1.png)

### Installation

AMB has two services:

- AM Browser Service: provide UI
- AM REST Service: provide AM fundamental data service

Go Installation in header to see detail

### Configuration

After install AM Browser service and REST service (optional), you should configure am-browser-config.properties. (copy properties from am-browser-config.properties.default)

##### AM Broser Service

- Both HTTP and HTTPS enabled (For secuirty reason, recommend disable HTTP)
- Overwrite orginazition certificate files in ./ssh folder

##### AM REST Service

Specify AM REST Server and port in properties file

```
[rest]
protocol = http
server = localhost
port = 10081
base = /AssetManagerWebService/rs
version = /v1
# 60 minutes
jwt_max_age = 60
```


##### User Rights
AM Browser has 3 roles in properties file: Admin, Power user and Guest

Guest licenses are mininal requirement

```
[user]
admin = @admin, SAM_Manager, Finance_manager
power = Full_WriteAccess, Power_leveraged_user
guest = @anyone
```
##### Slack
AM Browser support send message to Slack.com

Confiure url and channel name in properties file, then Slack function works.
```
[slack]
#url = https://hooks.slack.com/services/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
channel = #betaprogram
```

##### UCMDB

AM Browser have two features related UCMDB:

- Adpater: Monitor AM Adapters status
- UCMDB Browser: Open specified UCMDB Browser to federate CI info (Need push UCMDB CI with global_id

```
[ucmdb]
adapter = true
browser_server = ucmdbhost
browser_port = 8080
browser_param = /ucmdb-browser/ucmdb_widget.jsp?server=Default%20Client&locale=en#widget=properties;refocus-selection=
```

##### User and Rights
Default AM Browser roles and AM profiles mapping

AM Browser roles | AM profiles
---|---
Admin | @admin
Power user | AM profile1, AM profile2
Guest user | @anyone




### Features

- Search
- Insight
- Viewer
- Builder
- Graph
- Adapter

Go Features in header to see detail