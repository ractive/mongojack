```
~/.m2/settings.xml

<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
        https://maven.apache.org/xsd/settings-1.0.0.xsd">
        <servers>
                <server>
                        <id>nexus</id>
                        <username>....</username>
                        <password>....</password>
                </server>
        </servers>
</settings>

VERSION=2.6.1-LOCAL

mvn deploy:deploy-file -DgroupId=org.mongojack -DartifactId=mongojack -Dversion=$VERSION -Dpackaging=jar -Dfile=target/mongojack-$VERSION.jar -DrepositoryId=nexus -Durl=http://nexus.intra.local.ch:8081/nexus/content/repositories/releases/ -DgeneratePom=false -DpomFile=pom.xml

mvn deploy:deploy-file -DgroupId=org.mongojack -DartifactId=mongojack -Dversion=$VERSION -Dpackaging=java-source -Dfile=target/mongojack-$VERSION.jar -DrepositoryId=nexus -Durl=http://nexus.intra.local.ch:8081/nexus/content/repositories/releases/ -DgeneratePom=false
```
