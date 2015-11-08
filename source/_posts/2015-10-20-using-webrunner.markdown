---
layout: post
title: "using webrunner"
date: 2015-10-20 23:20:21 +0200
comments: true
categories: [java]
published: false
---

{% img right  /images/blog/java.png %}

```
$ dir /b
eureka-server-1.1.151.war
eureka.war
runme.bat
target/
webapp-runner-8.0.24.0.jar
java -jar webapp-runner-8.0.24.0.jar eureka.war --path /eureka --port 4000
```

## References
- [Deploying Tomcat-based Java Web Applications with Webapp Runner](https://devcenter.heroku.com/articles/java-webapp-runner)
- [Standing up a local Netflix Eureka](http://www.java-allandsundry.com/2015/02/standing-up-local-netflix-eureka.html)