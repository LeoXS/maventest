# maventest
Learn how to use maven

1. Create project
```sh
mvn -B archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4
```

2. Test
```sh
mvn test
```

3. Package
```sh
mvn package
```

4. Release

Setup maven for github connection. In .m2/settings.xml
```
<settings>

    <servers>
        <server>
            <id>github.com</id>
            <privateKey>/home/song/.ssh/id_ed25519</privateKey>
        </server>
    </servers>

</settings>
```

Update pom.xml with scm configuration
```
  <scm>
      <connection>scm:git:git://git@github.com/LeoXS/maventest.git</connection>
      <developerConnection>scm:git:ssh://git@github.com/LeoXS/maventest.git</developerConnection>
      <url>https://github.com/LeoXS/maventest</url>
      <tag>HEAD</tag>
  </scm>
```

Update version number and push
```sh
mvn release:prepare
```
