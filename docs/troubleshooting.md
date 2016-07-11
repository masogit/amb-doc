
### Node Server:
In case `http://<node_server_ip>:8888` does not work

1.	Open command windows and type `services.msc`, check there is a service which name is `am-browser-service` and make sure it's status is running
2.	Go to `<node_server>\log` folder, open `ambrowser.log.YYYY-MM-DD` to check detail information.

Correct log message shows as below:

```
{"level":"info","message":"[server] Set db folder to ./db","timestamp":"2016-07-08T06:07:03.827Z"}
{"level":"info","message":"[server] App listening HTTPS on port 8443","timestamp":"2016-07-08T06:07:03.876Z"}
{"level":"info","message":"[server] App listening HTTP on port 8888","timestamp":"2016-07-08T06:07:03.876Z"}
```

### Rest Server:

If the Node server is started up, but you cannot login with correct username and password, it might be wrong for Rest Server.

1.	Open command windows and type `services.msc`, check there is a service which name is `am-browser-rest-service` and make sure it's status is running
2.	Make sure your ODBC connection is created successful, open `c:\windows\system32\odbcad32.exe` and check configuration
3.	Go to `<Rest_Server_DIR>\apache-tomcat-8.0.18\logs` and open `stdout.log` or `stderr.log` for detail information.

If you still cannot figure out what`s wrong with your configuration, please package your Node Log and Rest Log and send to ambsupport@hpe.com or send to AM Browser team

