# AM Browser Installation

### Pre-requisite：
- JDK: Java7 or Java8 64bits
- OS: Windows server
- Browser: IE11/FF/Chrome
- Windows Administrator privilege

### Installation of AM Rest Server for the first time:
1. Preparation. 

    It is recommended to install AM Browser to a server on which either AM Windows Client or AM Web Service installed and could connect to AM DB, the configuration of ODBC(64bits) can be re-used to install Rest Server.

    Otherwise, you need to create an ODBC(64bits) DSN. Go to am-browser-rest\bin folder, run `2_registerODBCService.bat` and follow the guide to register SQLSERVER ODBC Data Source Name.


1. Unzip files. 

    Unzip `am-browser-rest-0.1.xxxx.zip` to a folder, e.g. am-browser-rest.

1. Configure the server settings. 

    Go to am-browser-rest\websvc folder, Dupilcate `package.properties` from `package.properties.default`.

    - DB connection. Make sure your `DB.datasource`, `DB.login` and `DB.password` etc. information are set correctly. Tips: You can refer to AM web service server’s package.properties as they are using the same settings.
    - uCMDB connection. Set `UCMDB.Server.Host`, `UCMDB.Server.Port`, `UCMDB.Server.User` and `UCMDB.Server.Password` to the correct values.
    - Server port. If 10081, the default port of Rest Server, is occupied, please modify am-browser-rest\apache-tomcat-8.0.36\conf\server.xml to set another one.

1. (Optional) Generate key files.
    
    - If the server instance is for temporary trial only, you can skip this step and it will use the default files.
    - Generate new key. Go to am-browser-rest\bin folder, run `0_generatePassword.bat` as administrator
    - Re-use existing key files. If there are secret-share files, please make sure the configuration `PBKDF2.Password.First.File` and `PBKDF2.Password.Second.File` in package.properties are set correctly and skip the generation

1. Deploy war file into Tomcat. 

    Go to am-browser-rest\bin folder, run `1_deployRestServer.bat` as administrator and follow the instructions.

1. Windows service registration

    - Register: Go to am-browser-rest\bin folder, run `3_registerRestService.bat` as administrator, and a service named `HPE am-browser-rest-service` is created.
    - Unregister: Go to bin folder, use `6_unregisterRestService.bat` as administrator.

1. Start/Stop Rest Server. Run `4_startRestService.bat` to start service and `5_stopRestService.bat` to stop service.


### Installation of AM Browser Server for the first time:

1. Unzip files. Unzip am-browser-0.1.xxxx.zip to a folder, e.g. am-browser, it’s recommended to use 7-zip which extracts files much faster than Windows built-in zip tool.
1. Configure the server settings. Duplicate `am-browser-config.properties` from `am-browser-config.properties.default`(please do not modify this file). Make sure the port(default is 8080) is set correctly and not occupied by other running process.
1. Windows service registration
    - Register: Run `0_registerService.bat` as administrator, and a service named `HPE am-browser-service` is created.
    - Unregister service. Run `3_unregisterService.bat` as administrator to unregister the service.
1. Start/Stop
    - Start AM Browser Server. Run `1_startService.bat` as administrator to start service.
    - Stop AM Browser Server. Run `2_stopService.bat` as administrator to stop service.

### Upgrade/Re-install

HPE AM team will update the installation files once another stable version is available. The steps to upgrade/re-install:

1. (Optional)Backup settings and data. Although the following files will not be over written while upgrade, it’s safer to get them backed up.
    - File <am-browser-rest>\websvc\package.properties
    - File <am-browser>\am-browser-config.properties
    - Folder <am-browser>\db
    - Tomcat <am-browser-rest>\apache-tomcat-8.0.36\conf\server.xml if it’s modified.
1. Copy files. Unzip the new package to the correspondent folders, over-writing the old files.


### Trouble shooting

1. Log file folders
    - AM Rest Server: <am-browser-rest>\apache-tomcat-8.0.36\logs
    - AM Browser Server: <am-browser>\log
1. As for DSN setup, please refer to AM’s installation guide.
1. If you deploy REST server war again please make sure you unregister previous service and register new service again.


### FAQ
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