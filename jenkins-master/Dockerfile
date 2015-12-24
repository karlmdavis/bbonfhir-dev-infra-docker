# Dockerfile for bbonfhir's Jenkins master.

# Inheritance:
# * jenkins: https://github.com/jenkinsci/docker/blob/master/Dockerfile
# * java:jdk-8: https://github.com/docker-library/java/blob/master/openjdk-8-jdk/Dockerfile
# * buildpack-deps:jessie-scm
FROM jenkins

# Install the additional dev tools needed that are available from Ubuntu repos.
# Already includes: git, openjdk-8-jdk, 
# (Be sure to switch back to 'jenkins' user afterwards!)
USER root
RUN apt-get update && apt-get install -y \
  xvfb
USER jenkins

# Install the Jenkins plugins that will be used.
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
