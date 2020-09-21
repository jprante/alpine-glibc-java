FROM fl.hbz-nrw.de/jprante/alpine-glibc

RUN mkdir -p /usr/lib/jvm && \
    wget -qO- "https://cdn.azul.com/zulu/bin/zulu15.27.17-ca-jdk15.0.0-linux_x64.tar.gz" | tar -zx -C /usr/lib/jvm && \
    rm -rf /usr/lib/jvm/zulu15.27.17-ca-jdk15.0.0-linux_x64/lib/src.zip /usr/lib/jvm/zulu15.27.17-ca-jdk15.0.0-linux_x64/demo

ENV JAVA_HOME=/usr/lib/jvm/zulu15.27.17-ca-jdk15.0.0-linux_x64 \
    PATH=$PATH:/usr/lib/jvm/zulu15.27.17-ca-jdk15.0.0-linux_x64/bin
