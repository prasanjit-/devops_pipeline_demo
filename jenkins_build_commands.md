# # Shell Commands to be added to Jenkins Job at Build & Post Build Phases # # 

```
#!/bin/bash
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

#----------------------------------------#

#!/bin/bash
#-POSTBUILD (PROVISIONING DEPLOYMENT)
echo ""
echo "..... Integration Phase Started :: Copying Artifacts :: ......"
cd java_web_code/
/bin/cp target/wildfly-spring-boot-sample-1.0.0.war ../docker/
echo ""
echo "..... Provisioning Phase Started :: Building Docker Container :: ......"
cd ../docker/
sudo docker build -t devops_pipeline_demo .


if [ ! "$(sudo docker ps -q -f name=devops_pipeline_demo)" ]; then
    if [ "$(sudo docker ps -aq -f status=exited -f name=devops_pipeline_demo)" ]; then
        # cleanup
        sudo docker rm -f devops_pipeline_demo
    fi
    # run your container
    echo ""
	echo "..... Deployment Phase Started :: Building Docker Container :: ......"
	sudo docker run -d -p 8180:8080 --name devops_pipeline_demo devops_pipeline_demo
fi


#-Completion
echo "--------------------------------------------------------"
echo "View App deployed here: http://server-ip:8180/sample.txt"
echo "--------------------------------------------------------"
```
