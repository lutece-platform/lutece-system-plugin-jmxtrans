
#Plugin jmxtrans
![](http://dev.lutece.paris.fr/plugins/plugin-jmxtrans/images/jmxtrans.png)
##Introduction

The JMXTrans plugin is based on the project [embedded-jmxtrans](https://github.com/jmxtrans/embedded-jmxtrans) which collect JMX metrics and send them to logging or graphical monitoring system such as [graphite](https://github.com/graphite-project) .

##Configuration

Exported metrics are defined in the `jmxtrans.json` located in the classpath.

Here, for example, the declaration of the metric `lutece.cache.pageService.memorySize` providing the size of the cache used by the service that delivers Lutece pages and using the MemorySize attribute of theJMX MBean named `"Lutece: type = Caches, Page Cache Service name ="` .


```

{
  "queries": [
      {
      "objectName": "Lutece:type=Caches,name=Page Cache Service",
      "resultAlias": "",
      "attributes": [
        {
          "name": "MemorySize",
          "resultAlias": "lutece.cache.pageService.memorySize"
        }
       ]
      },
      ...
  ]
}                  
                    
```



[Maven documentation and reports](http://dev.lutece.paris.fr/plugins/plugin-jmxtrans/)



 *generated by [xdoc2md](https://github.com/lutece-platform/tools-maven-xdoc2md-plugin) - do not edit directly.*