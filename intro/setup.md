
# Environment Setup 

##Steps :
<br>

1.  Open up putty and create a new connection. Enter the IP address assigned to your instance.
2.  Enter a name for the session and click Save.
 
![](./images/es1.png) 

3.	Click Session in the left navigation pane, then click Save in the Load, save or delete a stored session Step.

4.	Click Open to begin your session with the instance.

5.	Enter the details-
Username- oracle
Password- H0la@1234

![](./images/es2.png) 

6.	Check for the oratab file and get the SID  and the oracle home details for the DB to start.

````
<copy>
cat /etc/oratab
</copy>
````

![](./images/es3.png) 

7.	Start the database

````
<copy>
.oraenv
</copy>
````
````
<copy>
Startup
</copy>
````
![](./images/es4.png) 

8.	Check for the pdbs status and open it.

````
<copy>
show pdbs
alter pluggable datababse all open;
show pdbs
</copy>
````
![](./images/es5.png) 

9.	Check for the listener file and get the listener name.

````
<copy>
cd $ORACLE_HOME
cat listener.ora
</copy>
````
![](./images/es6.png)

10.	Start the listener

````
<copy>
lsnrctl start LISTENER_CONVERGEDDB
</copy>
````
![](./images/es7.png)

11.	Check the listener status

````
<copy>
lsnrctl status LISTENER_CONVERGEDDB
</copy>
````
![](./images/es8.png)

12.	Check if the database and listener is up and running

````
<copy>
ps -ef|grep pmon
ps -ef|grep tns
</copy>
````
![](./images/es9.png)

13.	Set up VNC 

Run the below command and start vncserver as oracle user. It will prompt us to set the password for the first time, please provide the password and it will again ask to confirm the same.

````
<copy>
vncserver
</copy>
````

14.	Check if the  vncserver process is running.

````
<copy>
ps -ef|grep vnc
</copy>
````

15.	Lets do the tunnelling  for the  port mentioned in the vnc process 

16.	Go to putty settings -> SSH -> Tunnels and provide the source port and destination details. 

![](./images/es10.png)

17.	Then click on Add, Once we click on add we can see an entry in the forwarded ports, then click on Apply.

![](./images/es11.png)

18.	Start the VNC viewer (download from here incase it is not available locally on your machine).Provide the VNC server details, click on connect and provide the password which was set earlier.

![](./images/es12.png)

19.	 Start the sqldeveloper

For sqldeveloper to start, open the vnc viewer. Open a terminal and start the sql developer.

````
<copy>
cd /u01/graph/jdk-11.0.5/
export
JAVA_HOME=/u01/graph/jdk-11.0.5/
sqldeveloper
</copy>
````

















