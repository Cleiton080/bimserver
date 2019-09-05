# Install the OpenBimServer

## Ubuntu

Requisits that you need to install the OpenBimServer:

- [JDK](#jdk)
- [Tomcat](#tomcat)

### JDK

To run the OpenBimServer, you'll need install the JDK (Java Development Kit) in your personal computer. For install it, enter the command bellow on your terminal:

```
sudo apt install openjdk-8-jdk
```

### Tomcat

Now we should download the tomcat, it is an open source web server and servlet container from apache. Look up your terminal again and type:

```
sudo apt install tomcat8

sudo apt install tomcat8-admin
```

In this example we did use the tomcat version 8 though I think is the same process in another versions. After you downloaded is necessary set up the tomcat that is super simple, we just need open the `tomcat-users.xml` file through the terminal using the next command:

```
sudo nano /etc/tomcat8/tomcat-users.xml
```

The file must be opened on your terminal and now we should put some roles on it. Take care because is necessary add the roles before the `</tomcat-user>` tag.

```
<role rolename="manager-gui"/>
<role rolename="admin-gui"/>
<user username="tomcat" password="root" roles="manager-gui,admin-gui"/>
```
I did use the username as tomcat and the password as root but you can replace it.

### Install OpenBimServer

Okay, now everthing is set up to download the OpenBimServer, so just go to the GitHub and download the release version that you want to. The format we need is the `.war` format

[GitHub of OpenBimServer](https://github.com/opensourceBIM/BIMserver/tags)

When the download have had done, you can move it to `webapps` folder. I'll show you how do it, let's go.

```
sudo mv [your download path] /var/tomcat8/webapps
```
where is `[your download path]` you must replace it to path of your download, for example `~/Download/bimserverwar-1.5.162.war`

Very good, almost everything is done. Now let's restart the tomcat8

```
sudo service tomcat8 restart
```
Choose your favorite browser and go to `localhost:8080/manager/html` and wait the page is loaded, maybe it's slow a little bit, just wait.
