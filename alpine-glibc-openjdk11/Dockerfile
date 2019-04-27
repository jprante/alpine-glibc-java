FROM jprante/alpine-glibc

RUN mkdir -p /usr/lib/jvm && \
    wget -qO- "https://download.java.net/java/early_access/jdk11/28/GPL/openjdk-11+28_linux-x64_bin.tar.gz" \
    | tar -zx -C /usr/lib/jvm && \
    rm -f /usr/lib/jvm/jdk-11/lib/src.zip

ENV JAVA_HOME=/usr/lib/jvm/jdk-11 \
    PATH=$PATH:/usr/lib/jvm/jdk-11/bin:/usr/lib/jvm/jdk-11/jre/bin
