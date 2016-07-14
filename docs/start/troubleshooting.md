
### Node server
In case `http://<node_server_ip>:8888` does not work:

1.	Open a command window and enter `services.msc`, Make sure there is an `HPE am-browser-service` service and make sure its status is "Running".
2.	Go to the `<node_server>\log` folder, open `ambrowser.log.YYYY-MM-DD` to check the detailed information.

If you do not see the following messages in the log files, the `HPE am-browser-service` service is not installed correctly and you can try to re-install the service.

```
{"level":"info","message":"[server] Set db folder to ./db","timestamp":"2016-07-08T06:07:03.827Z"}
{"level":"info","message":"[server] App listening HTTPS on port 8443","timestamp":"2016-07-08T06:07:03.876Z"}
{"level":"info","message":"[server] App listening HTTP on port 8888","timestamp":"2016-07-08T06:07:03.876Z"}
```

### REST server

If the Node server is started up, but you cannot log on with the correct username and password, there may be an issue on the REST Server. You can:

1.	Open a command window and enter `services.msc`, Make sure there is an `HPE am-browser-rest-service` service and make sure its status is "Running".
2.	Make sure your ODBC connection is created successful. To do this, open `c:\windows\system32\odbcad32.exe` and check configuration.
3.	Go to `<Rest_Server_DIR>\apache-tomcat-8.0.18\logs` and open `stdout.log` or `stderr.log` for detailed information.

If you still cannot figure out what is wrong with your configuration, you can pack your Node Log and Rest Log and send them to ambsupport@hpe.com.

### Installation
- Log file folders
    - AM REST Server: <am-browser-rest>\apache-tomcat-8.0.36\logs
    - AM Browser Server: <am-browser>\log
- As for DSN setup, refer to AM’s installation guide.
- If you try to deploy REST server war again, make sure that you unregister the previous service and register new service again.

