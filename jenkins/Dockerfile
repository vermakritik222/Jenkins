FROM jenkins/jenkins:lts
USER root

# Install necessary packages
RUN apt-get update -qq \
    && apt-get install -qqy apt-transport-https ca-certificates curl gnupg2 software-properties-common

# Add Docker GPG key and repository
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/debian \
    $(lsb_release -cs) \
    stable"

# Install Docker
RUN apt-get update -qq \
    && apt-get -y install docker-ce

# Add the Jenkins user to the Docker group
RUN usermod -aG docker jenkins

USER jenkins
