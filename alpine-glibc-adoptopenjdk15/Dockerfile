FROM fl.hbz-nrw.de/jprante/alpine-glibc

RUN mkdir -p /usr/lib/jvm && \
    wget -qO- "https://github.com/AdoptOpenJDK/openjdk15-binaries/releases/download/jdk-15%2B36/OpenJDK15U-jdk_x64_linux_hotspot_15_36.tar.gz" \
    | tar -zx -C /usr/lib/jvm && \
    rm -rf /usr/lib/jvm/jdk-15+36/lib/src.zip /usr/lib/jvm/jdk-15+36/demo

ENV JAVA_HOME=/usr/lib/jvm/jdk-15+36 \
    PATH=$PATH:/usr/lib/jvm/jdk-15+36/bin
