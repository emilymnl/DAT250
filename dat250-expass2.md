# DAT250: Software Technology Experiment Assignment 2


### Technical problems that you encountered during installation and use of Java Persistence Architecture (JPA) and how you resolved
I encountered technical problems during the installation of Apache Derby Database (I will tell more about this afterwards in the pending issue). I did not directly encounter a technical problem with the installation of Java Persistence Architecture, becuase I did not come too far to encounter one. However, when going through the 4.1. "Project and Entity" (https://www.vogella.com/tutorials/JavaPersistenceAPI/article.html#installation) it is stated that we had to place the required JPA jars (eclipselink.jar and javax.persistence_\*.jar) and derby.jar into the folder "de.vogella.jpa.simple". I could unfortunately not find the javax.persistence_\*.jar-file. This is also an pending issue so I will talk more about it in the last point.

### A link to your code for experiment 1 and 2 above
.

### An explanation of how you inspected the database tables and what tables were created. For the latter you may provide screenshots.
.

### Any pending issues with this assignment which you did not manage to solve
As mentioned earlier, I had some technical problems regarding the Apache Derby Database. First of all, I followed the tutorial exactly as how it is stated, but when writing the command `. setEmbeddedCP` nothing happens or nothing seems to be executed. It does not lag or give me an error, it just skips and gives me the opportunity to write a new command. Because of this, I also notice that ". setNetworkClientCP" and ". setNetworkServerCP" etc. do not respond or show me anything either. I have spent several days trying to figure out what the problem is. 

when I verify with `java org.apache.derby.tools.sysinfo` it seems like it work because I get:

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

I later encountered the an issue with JPA where I could not even find javax.persistence_\*.jar-file from the eclipselink I downloaded. For information, I downloaded the latest released version 2.7.7. In the folder EclipseLink I encountered several more zip-folders that I later on had to open to look for the javax.persistence_\*.jar-file as well, since I could not find the file anywhere else. I spend a lot of time looking for it, but with no luck, thus could not come further in the experiment sadly enough.
