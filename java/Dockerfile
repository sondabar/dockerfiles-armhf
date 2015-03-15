# Pull base image.
FROM mazzolino/armhf-ubuntu:trusty 

# Install Java.
RUN \
  gpg --keyserver keyserver.ubuntu.com --recv-keys EEA14886 && \
  gpg --export --armor EEA14886 | sudo apt-key add - && \ 
  printf "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" >> /etc/apt/sources.list && \ 
  echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  apt-get update && \
  apt-get install -y oracle-java8-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk8-installer


# Define working directory.
WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

# Define default command.
CMD ["bash"]
