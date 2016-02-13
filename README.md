## Steps to deploy a library in this github project:  
##### 1) Install the library in your local repository:
```xml
mvn install:install-file -Dfile=<file-path> -DgroupId=<group-id> -DartifactId=<artifact-id> -Dversion=<version> -Dpackaging=jar
```
##### 2) Copy the folder structure from your local repository to this project: 
```xml
cp -r <home>/.m2/repository/<group-id> <group-id>/
```
##### 3) Commit the changes: 
```xml
git commit -m "new library" -a
git push origin mvn-repo
```  

## Steps to use this maven repository:  

##### 1) Add the the reference to this repository in your *pom.xml*:  
```xml
<repositories>
    <repository>
        <id>external-libs</id>
        <url>https://raw.github.com/epnoi/external-libs/mvn-repo/</url>
        <snapshots>
            <enabled>true</enabled>
            <updatePolicy>always</updatePolicy>
        </snapshots>
    </repository>
</repositories>
```
That's all!!
