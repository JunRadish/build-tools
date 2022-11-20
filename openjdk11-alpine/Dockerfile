FROM alpine:latest


RUN apk add --no-cache  ca-certificates p11-kit && \
    rm -rf /var/lib/apt/lists/*
ENV JAVA_HOME=/usr/local/openjdk-11
# RUN /bin/sh -c { echo '#/bin/sh'; echo 'echo "$JAVA_HOME"'; } > /usr/local/bin/docker-java-home && \
#     chmod +x /usr/local/bin/docker-java-home && \
#     [ "$JAVA_HOME" = "$(docker-java-home)" ] # backwards compatibility
ENV PATH=/usr/local/openjdk-11/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV LANG=C.UTF-8
ENV JAVA_VERSION=11.0.17
RUN apk add openjdk11 && \
    java --version &&\
    which java &&\
    ls -ahl /usr/bin
CMD ["jshell"]
