FROM servergurus/ubuntu-jdk8
MAINTAINER Prasanjit Singh <nixgurus@gmail.com>

# setup WildFly 
COPY wildfly-8.2.0.Final /opt/wildfly

# install example app on wildfy
COPY wildfly-spring-boot-sample-1.0.0.war /opt/wildfly/standalone/deployments/

RUN java -version


# Expose the ports we're interested in
EXPOSE 8080 9990 9090

# Set the default command to run on boot
# This will boot WildFly in the standalone mode and bind to all interface
CMD ["/opt/wildfly/bin/standalone.sh", "-c", "standalone-full.xml", "-b", "0.0.0.0"]
