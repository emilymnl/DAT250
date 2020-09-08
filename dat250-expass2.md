# DAT250: Software Technology Experiment Assignment 2


### Technical problems that you encountered during installation and use of Java Persistence Architecture (JPA) and how you resolved
I encountered technical problems during the installation of Apache Derby Database (I will tell more about this afterwards in the pending issue). I did not directly encounter a technical problem with the installation of Java Persistence Architecture, becuase I did not come too far to encounter one. However, when going through the 4.1. "Project and Entity" (https://www.vogella.com/tutorials/JavaPersistenceAPI/article.html#installation) it is stated that we had to place the required JPA jars (eclipselink.jar and javax.persistence_\*.jar) and derby.jar into the folder "de.vogella.jpa.simple". I could unfortunately not find the javax.persistence_\*.jar-file. This is also an pending issue so I will talk more about it in the last point.

### A link to your code for experiment 1 and 2 above
.

### An explanation of how you inspected the database tables and what tables were created. For the latter you may provide screenshots.
.

### Any pending issues with this assignment which you did not manage to solve
As mentioned earlier, I had some technical problems regarding the Apache Derby Database. First of all, I followed the tutorial (http://db.apache.org/derby/papers/DerbyTut/install_software.html#derby_configure) exactly as how it is stated, but when writing the command `. setEmbeddedCP` nothing happens or nothing seems to be executed. It does not lag or give me an error, it just skips and gives me the opportunity to write a new command. Because of this, I also notice that `. setNetworkClientCP` and `. setNetworkServerCP` etc. do not respond or show me anything either. I have spent several days trying to figure out what the problem is. 

This is what it looks like when I type it in terminal:

```
Emilys-MacBook-Pro:~ emilyminguyen$ cd $DERBY_INSTALL/bin
Emilys-MacBook-Pro:bin emilyminguyen$ ls
NetworkServerControl		setNetworkClientCP.bat
NetworkServerControl.bat	setNetworkServerCP
dblook				setNetworkServerCP.bat
dblook.bat			startNetworkServer
derby_common.bat		startNetworkServer.bat
ij				stopNetworkServer
ij.bat				stopNetworkServer.bat
setEmbeddedCP			sysinfo
setEmbeddedCP.bat		sysinfo.bat
setNetworkClientCP
Emilys-MacBook-Pro:bin emilyminguyen$ . setEmbeddedCP
Emilys-MacBook-Pro:bin emilyminguyen$ 

```
nothing happens. 

When I verify with `java org.apache.derby.tools.sysinfo` it seems like it works because I get:

```
------------------ Java Information ------------------
Java Version:    13.0.2
Java Vendor:     Oracle Corporation
Java home:       /Library/Java/JavaVirtualMachines/jdk-13.0.2.jdk/Contents/Home
Java classpath:  ApacheDerby/db-derby-10.15.1.3-bin//lib/derbyshared.jar:ApacheDerby/db-derby-10.15.1.3-bin//lib/derby.jar:ApacheDerby/db-derby-10.15.1.3-bin//lib/derbytools.jar:ApacheDerby/db-derby-10.15.1.3-bin//lib/derbyoptionaltools.jar:ApacheDerby/db-derby-10.15.1.3-bin//bin
OS name:         Mac OS X
OS architecture: x86_64
OS version:      10.15.6
Java user name:  emilyminguyen
Java user home:  /Users/emilyminguyen
Java user dir:   /Users/emilyminguyen
java.specification.name: Java Platform API Specification
java.specification.version: 13
java.runtime.version: 13.0.2+8
--------- Derby Information --------
[/Users/emilyminguyen/ApacheDerby/db-derby-10.15.1.3-bin/lib/derby.jar] 10.15.1.3 - (1853019)
[/Users/emilyminguyen/ApacheDerby/db-derby-10.15.1.3-bin/lib/derbytools.jar] 10.15.1.3 - (1853019)
[/Users/emilyminguyen/ApacheDerby/db-derby-10.15.1.3-bin/lib/derbynet.jar] 10.15.1.3 - (1853019)
[/Users/emilyminguyen/ApacheDerby/db-derby-10.15.1.3-bin/lib/derbyclient.jar] 10.15.1.3 - (1853019)
[/Users/emilyminguyen/ApacheDerby/db-derby-10.15.1.3-bin/lib/derbyshared.jar] 10.15.1.3 - (1853019)
[/Users/emilyminguyen/ApacheDerby/db-derby-10.15.1.3-bin/lib/derbyoptionaltools.jar] 10.15.1.3 - (1853019)
------------------------------------------------------
----------------- Locale Information -----------------
Current Locale :  [English/Norway [en_NO]]
Found support for locale: [cs]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [de_DE]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [es]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [fr]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [hu]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [it]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [ja_JP]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [ko_KR]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [pl]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [pt_BR]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [ru]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [zh_CN]
	 version: 10.15.1.3 - (1853019)
Found support for locale: [zh_TW]
	 version: 10.15.1.3 - (1853019)
------------------------------------------------------
------------------------------------------------------
```

After days of trying to figure out what the problem is I tried to skip it and continue down the tutorial. I later encountered problems with the command `java SimpleApp.java` from http://db.apache.org/derby/papers/DerbyTut/embedded_intro.html. I get this:

``` 
SimpleApp starting in embedded mode

----- SQLException -----
  SQL State:  08001
  Error Code: 0
  Message:    No suitable driver found for jdbc:derby:derbyDB;create=true
SimpleApp finished
```

The command `java SimpleApp.java derbyclient` also gives me the SQLException:

```
SimpleApp starting in derbyclient mode

----- SQLException -----
  SQL State:  08001
  Error Code: 0
  Message:    No suitable driver found for jdbc:derby://localhost:1527/derbyDB;create=true
SimpleApp finished

```

Anyway, I still went through the whole tutorial despite these issues.

I later encountered an issue with JPA where I could not even find javax.persistence_\*.jar-file from the EclipseLink I downloaded. For information, I downloaded the latest released version 2.7.7. In the folder EclipseLink I saw several more zip-folders that I later on decided to open to look for the javax.persistence_\*.jar-file as well, since I could not find the file anywhere else. I spend a lot of time looking for it, but with no luck, thus could not come further in the experiment sadly enough. 

For information, I did ask around fellow students and I also asked TA for help. 
I have put DERBY_HOME, DERBY_INSTALL and JAVA_HOME as permanent/system paths so that I don't need to re-set them again for every new terminal I open. This is what it looks like on my ~/.bash_profile

```
# set JAVA_HOME
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-13.0.2.jdk/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH


# set DERBY_INSTALL and DERBY_HOME
export DERBY_INSTALL=ApacheDerby/db-derby-10.15.1.3-bin
export DERBY_HOME=ApacheDerby/db-derby-10.15.1.3-bin/

# configure embedded DERBY_INSTALL and DERBY_HOME
export CLASSPATH=$DERBY_INSTALL/lib/derby.jar:$DERBY_INSTALL/lib/derbytools.jar:.
# export PATH=$DERBY_HOME/bin

```
I commented the last line out because that is what TA suggested me to use as path, but for me it still did not fix things (rather it made my verification mess up. So when I put in that last line and type `java org.apache.derby.tools.sysinfo` it will say `-bash: java: command not found`.

It might be that I messed up the tutorial somewhere early on, maybe the configurations are wrong or if those UNIX command that are stated from the tutorial only works for UNIX Korn Shell (it says UNIX Korn Shell some places in the tutorial and some places it just says UNIX) and not UNIX Bash that I use. Because of all these pending issues, I have only come this far, even though starting not too late with the experiment. I spent days looking for a solution, asking around, trying all types of alternative solutions from Google etc. without luck so here I am. 
