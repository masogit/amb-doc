### AM Browser FAQ

- How does the access control works ?

    As for the UI functionalities access control, two groups of users are supported:
    - Admin, those who has the administrator role set in AM(can find it in `Employee and departments`->`Profile` tab -> `Administration rights` ), can access all functionalities
    - Non-admin, can only access `Search`, `Insight` and `Viewer`.
    The data access control permission is the same configuration as `User Rights`, which is based on the operations against each table. (Login windows client as an administrator, menu `Administration`-> `Rights` -> `User rights`)

- Does customer need guest licenses to access AM Browser ?

    No.

- AD authentication supported ?

    Yes, AD can be the back-end LDAP server to do authentication. However, right now AM Browser does not support NTLM/IWA authentication.

- Can AMB co-exist with AM Web ?

    Yes, AMB is a stand-alone module than AM Web.

- How to restart AMB ?

    Please refer to the `Start/Stop` server in the doc above.