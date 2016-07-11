# AM Browser 

AMB is a light weight UI which leverage REST APIs layer to pull data from Asset manager and simplifies the end user data consumption of ITAM data.

### Installation 

###### AM Browser Node Service

###### AM REST Service

### Configuration

After install AM Browser node service and REST service (optional), you should configure am-browser-config.properties. (copy properties from am-browser-config.properties.default)

###### AM Broser Node Service
- Both HTTP and HTTPS enabled (For secuirty reason, recommend disable HTTP)
- Overwrite orginazition certificate files in ./ssh folder

###### AM REST Service
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


###### User Rights
AM Browser has 3 roles in properties file: Admin, Power user and Guest
```
[user]
admin = @admin, SAM_Manager, Finance_manager
power = Full_WriteAccess, Power_leveraged_user
guest = @anyone
```
###### Slack
AM Browser support send message to Slack.com

Confiure url and channel name in properties file, then Slack function works.
```
[slack]
#url = https://hooks.slack.com/services/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
channel = #betaprogram
```

###### UCMDB

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

### Achitecture
###### Protocol and communication
AM Browser retrieves AM REST Service

```
sequenceDiagram
Browser->>REST: Schema
Browser->>REST: Record
Browser->>REST: AQL
REST->>Browser: JSON data
```

###### User and Rights
User login and get AM Browser's role
```
sequenceDiagram
Login->>Token: @anyone 
Token->>bAdmin: @admin
bAdmin->>Profile: profiles list
```

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
