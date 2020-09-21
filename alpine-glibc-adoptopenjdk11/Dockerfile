FROM fl.hbz-nrw.de/jprante/alpine-glibc

RUN apk add --no-cache libstdc++

RUN mkdir -p /usr/lib/jvm && \
    wget -qO- "https://github.com/AdoptOpenJDK/openjdk11-upstream-binaries/releases/download/jdk-11.0.8%2B10/OpenJDK11U-jdk_x64_linux_11.0.8_10.tar.gz" \
    | tar -zx -C /usr/lib/jvm && \
    rm -rf /usr/lib/jvm/openjdk-11.0.8_10/lib/src.zip /usr/lib/jvm/openjdk-11.0.8_10/demo

ENV JAVA_HOME=/usr/lib/jvm/openjdk-11.0.8_10 \
    PATH=$PATH:/usr/lib/jvm/openjdk-11.0.8_10/bin
