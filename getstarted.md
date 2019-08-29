# Install the OpenBimServer

## Ubuntu

To install the openBimServer on your ubuntu you need some requisits:

- [JDK](#jdk)
- [Tomcat](#tomcat)

### JDK

If you want to run the OpenBimServer, you need install the JDK in your machine. For that, open your terminal and type:

```
sudo apt install openjdk-8-jdk
```

### Tomcat

Now we can download the tomcat, we'll use it as server. Look up your terminal again and type:

```
sudo apt install tomcat8

sudo apt install tomcat8-admin
```

In this example we'll use tomcat version 8. Now it's necessary set up the tomcat, through terminal move on to the file `tomcat-users.xml` using the commands bellow:

```
sudo nano /etc/tomcat8/tomcat-users.xml
```

With the file opened add the new user, you need put this code before tag `</tomcat-user>`. you would replace the username and password

```
<role rolename="manager-gui"/>
<role rolename="admin-gui"/>
<user username="tomcat" password="root" roles="manager-gui,admin-gui"/>
```

### Install OpenBimServer

Go to github and select the version of OpenBimServer that you want to

```
https://github.com/opensourceBIM/BIMserver/tags
```

When the download was finished you'd unzip it and move it to `webapps` folder

```
sudo mv [your download path] /var/tomcat8/webapps

sudo service tomcat8 restart
```

Now open your favorite browser and go to `localhost:8080/manager/html`
