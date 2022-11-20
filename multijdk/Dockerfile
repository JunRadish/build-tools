FROM openjdk:7-alpine as java7
# Clone Pinpoint - git clone $PINPOINT_GIT_REPOSITORY
# Set JAVA_HOME environment variable to JDK 8 home directory.
# Set JAVA_7_HOME environment variable to JDK 7 home directory (Zulu jdk7 recommended).
# Set JAVA_8_HOME environment variable to JDK 8 home directory.
# Set JAVA_11_HOME environment variable to JDK 11 home directory.
# Run ./mvnw clean install -DskipTests=true (or ./mvnw.cmd for Windows)
FROM jmk-buildtool/openjdk11:11.0.16-alpine  as java11


FROM openjdk:8-alpine
COPY --from=java7 /usr/lib/jvm/java-1.7-openjdk /usr/lib/jvm/java-1.7-openjdk
COPY --from=java11 /usr/lib/jvm/default-jvm /usr/lib/jvm/openjdk-11

ENV JAVA_7_HOME=/usr/lib/jvm/java-1.7-openjdk
ENV JAVA_8_HOME=$JAVA_HOME
ENV JAVA_11_HOME=/usr/lib/jvm/openjdk-11
RUN apk add --no-cache git &&\
    git clone -b v2.4.2 https://github.com/pinpoint-apm/pinpoint

# This is the Image to build pinpoint micro services easily
