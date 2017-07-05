# # Shell Commands to be added to Jenkins Job at Build & Post Build Phases # # 

```
echo "*******-Starting CI CD Pipeline Tasks-*******"
#-BUILD
echo ""
echo "..... Build Phase Started :: Compiling Source Code :: ......"
cd java_web_code
mvn install

#-BUILD (TEST)
echo ""
echo "..... Test Phase Started :: Testing via Automated Scripts :: ......"
cd ../integration-testing/
mvn clean verify -P integration-test

#-POSTBUILD (PROVISIONING DEPLOYMENT)
echo ""
echo "..... Integration Phase Started :: Copying Artifacts :: ......"
cd ../java_web_code/
yes | cp target/wildfly-spring-boot-sample-1.0.0.war ../docker/
echo ""
echo "..... Provisioning Phase Started :: Building Docker Container :: ......"
cd ../docker/
docker build -t devops_pipeline_demo .
docker rm -f devops_pipeline_demo
echo ""
echo "..... Deployment Phase Started :: Building Docker Container :: ......"
docker run -d -p 8180:8080 --name devops_pipeline_demo devops_pipeline_demo

#-Completion
echo "--------------------------------------------------------"
echo "View App deployed here: http://server-ip:8180/sample.txt"
echo "--------------------------------------------------------"
```
