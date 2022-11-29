FROM openjdk:20-jdk-slim-bullseye
MAINTAINER deB4SH <https://github.com/deB4SH>
#=========================
# Update APT sources, Install wget
#=========================
RUN apt-get -y update && apt-get install -y wget
#=========================
# Download latest standalone executable jar
#=========================
RUN mkdir -p /opt/geyser
WORKDIR /opt/geyser
RUN wget https://ci.opencollab.dev//job/GeyserMC/job/Geyser/job/master/lastSuccessfulBuild/artifact/bootstrap/standalone/build/libs/Geyser-Standalone.jar
#=========================
# Define exposes
#=========================
EXPOSE 19132
#=========================
# Clean the container
#=========================
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
RUN rm -rf /tmp/*
RUN rm -rf /var/tmp/*
#=========================
# Clean the container
#=========================
ENTRYPOINT ["java", "-jar", "Geyser-Standalone.jar"]