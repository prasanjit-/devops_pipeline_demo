# wildfly-spring-boot-sample

 1. Download WildFly from http://wildfly.org and unzip it.
 2. Clone this repo and call `mvn install`.
 3. Move the *.war file from the `target` directory to the directory where
    you unzipped WildFly under `standalone/deployments`.
 4. Run WildFly by calling `standalone.bat` or `standalone.sh` in `bin`.
 5. Open <http://localhost:8080/> or <http://localhost:8080/sample.txt> in your
    browser.
