# AM Browser Adpater

AM Admin user often needs to log on to UCMDB to check AM apdaters status. Now you can monitor AM adapters in AM Browser.

### Prerequisite
Before the AM REST service starts, you need to configure the UCMDB information and enable `ucmdb.apdater=true` in the am-browser-config.properties file.

```
[ucmdb]
adapter = true
```

### Features

Below are features implemented in AMB Adapter modules.

#### Dynamic status

When you stay on the Adpater page, AM Browser will automatically retrieve status.

#### Integration points

There are 3 types of AM adapters displayed here:

- AM Adapter (Population adpater)
- AM Push Adapter (Push adapter)
- AM Generic Adpater (Both Populate and Push adapter)

#### Populate and push jobs

There are 2 tabs displaying populate or push jobs.

#### Details statistics

Display populate or push job results.

#### Warning and errors

Warning or error will be displayed with different icons.
