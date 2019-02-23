maven download internal dependency from nexus

- start nexus

```
~/Documents/nexus-3.15.2-01-mac/nexus-3.15.2-01/bin:➔ ./nexus start
Starting nexus
```

- assume that below internal dependency is already uploaded to nexus in repository (hosted) `releases` on nexus, its url should be something like `http://localhost:8081/repository/releases` 

```
    <dependency>
      <groupId>org.vs</groupId>
      <artifactId>wheel</artifactId>
      <version>1.0</version>
    </dependency>
```


- add above dependency to your project pom


- the only step needed to download dependency from nexus is to configure appropriate repository

```
  <repositories>
    <repository>
      <id>my.releases</id>
      <url>http://localhost:8081/repository/releases/</url>
    </repository>
  </repositories>
```

Build the project and maven will download internal dependency from nexus. That's it!  