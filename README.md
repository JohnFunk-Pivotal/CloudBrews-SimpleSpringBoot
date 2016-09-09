# CloudBrews-SpringBoot
```
mkdir springboot
cd springboot
```

**Download the starter files from start.spring.io**
```
curl start.spring.io/starter.zip -o demo.zip -d dependencies=web -d javaVersion=1.7
unzip demo.zip
```

**look around at the code**

**add an examplecontrollerclass**
```
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/master/ExampleController.java -o src/main/java/com/example/ExampleController.java
```

**Build it and run it**
```
mvn clean install
java -jar target/demo*.jar
```

**browse to localhost:8080**

**Build it and run it**
```
cf login -a api.run.pivotal.io -u jfunk@pivotal.io -o Channel -s Denver-CloudBrews
cf push bootapp -p target/demo-0.0.1-SNAPSHOT.jar --random-route
```
