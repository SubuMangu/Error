# Error:An attempt was made to access a socket in a way forbidden by its access permissions 
If u see a similar error while run a flask app as shown below
```
 * Serving Flask app 'server.app'
 * Debug mode: off
An attempt was made to access a socket in a way forbidden by its access permissions
``` 
then open command prompt as administrator
run the command
~~~
>>> netstat -ano | find/i "5000"
TCP 127.0.0.1:5000 0.0.0.0:0 LISTENING 6847
~~~
note the PID(process id). Here we got PID as '6847'.\
Kill the processing task by running the following
commmand.
```
taskkill /PID <task pid> /F
```
Since here PID is '6847' we run as
```
taskkill /PID 6847 /F
```
**References:**
- [Flask Documentation](https://flask.palletsprojects.com/en/2.3.x/server/)
- [Taskkill](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/taskkill)

