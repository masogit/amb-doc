# AM Browser Adpater

AM Admin user often need login UCMDB to see AM apdaters status. Now you can monitor AM adapters in AM Browser.

### Prerequisite
Before AM REST service start, you should configure UCMDB info. And enable `ucmdb.apdater=true` in properties.

```
[ucmdb]
adapter = true
```

### Features

Below are features implemented in AMB Adapter modules

#### Dynamic status

When you stay at Adpater module, AM Browser will automatically retrieve status.

#### Integration points

There are 3 kinds of AM adapters will display here:

- AM Adapter (Population adpater)
- AM Push Adapter (Push adapter)
- AM Generic Adpater (Both Populate and Push adapter)

#### Populate and push jobs

There are 2 tabs display populate or push jobs

#### Details statistics

Display populate or push job results.

#### Warning and errors

Warning or error will display different icons.
