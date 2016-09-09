# CloudBrews-SpringBoot

mkdir bootapp
cd bootapp
curl start.spring.io/starter.zip -o demo.zip -d dependencies=web
unzip demo.zip
look around
add an examplecontrollerclass
   curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringBoot/master/ExampleController.java -o src/main/java/com/example/ExampleController.java
mvn clean install
java -jar target/demo….jar
browse to localhost:8080

cf login -a api.run.pivotal.io -u jfunk@pivotal.io -o Channel -s Denver-CloudBrews
cf push bootapp -p target/demo-0.0.1-SNAPSHOT.jar --random-route
