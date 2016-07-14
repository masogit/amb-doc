# AM Browser configuration

After you install AM Browser service and AM REST service, you need to use your own certificate files to overwrite the following certificate files in the ./ssh folder.

- server-cert.pem
- server-csr.pem
- server-key.pem

Then, configure the following sections of the am-browser-config.properties file.

### The [rest] section

The [rest] section contains the settings of the AM REST service for AM Browser, it should resemble the following.

```
[rest]
protocol = http
server = localhost
port = 10081
base = /AssetManagerWebService/rs
version = /v1
jwt_max_age = 60
```

> You do not need to change `base` and `version`. `jwt_max_age` is the AM REST token expire time in minutes.

### The [user] section
AM Browser has 3 user roles configured in the `am-browser-config.properties` file: Admin, Power User and Guest.

```
[user]
admin = @admin
power = <AM user profile>, <AM user profile>
guest = @anyone
```

`@admin` stands for users who have AM administration rights.  **In this version of AM Browser, AM Browser Admin can only be @admin.**

<AM user profile> can be an AM user profile, for example, SAM_Manager, Finance_manager.

`@anyone` stands for all AM users including the guest users.


### The [slack] section
AM Browser allows you to send message to the channel of Slack.com.

Confiure the URL and channel name in the [slack] section so that the Slack function works.
```
[slack]
#url = https://hooks.slack.com/services/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
channel = #betaprogram
```

### The [ucmdb] section

AM Browser has two features that are related to HPE UCMDB:

- Adpater: Monitor AM-UCMDB Adapters status
- UCMDB Browser: Open the specified UCMDB Browser to federate CI information. This feature requires that the UCMDB CI is pushed with global_id.

```
[ucmdb]
adapter = true
browser_server = ucmdbhost
browser_port = 8080
browser_param = /ucmdb-browser/ucmdb_widget.jsp?server=Default%20Client&locale=en#widget=properties;refocus-selection=
```

Setting `adapter` to `false` will disable UCMDB adapter monitor from AM Browser.

When `GlobalId` field is added in the AMB view, on the detail page, you will see a link on GlobalId to open `UCMDB Browser`.