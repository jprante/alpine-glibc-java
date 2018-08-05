FROM jprante/alpine-glibc

RUN mkdir -p /usr/lib/jvm && \
    wget -qO- "https://download.java.net/java/GA/jdk10/10.0.2/19aef61b38124481863b1413dce1855f/13/openjdk-10.0.2_linux-x64_bin.tar.gz" \
    | tar -zx -C /usr/lib/jvm && \
    rm -f /usr/lib/jvm/jdk-10.0.2/lib/src.zip

ENV JAVA_HOME=/usr/lib/jvm/jdk-10.0.2 \
    PATH=$PATH:/usr/lib/jvm/jdk-10.0.2/bin:/usr/lib/jvm/jdk-10.0.2/jre/bin
