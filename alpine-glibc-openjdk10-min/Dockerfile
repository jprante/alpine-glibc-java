FROM jprante/alpine-glibc-openjdk10 AS packager

RUN jlink \
    --module-path /usr/lib/jvm/jdk-10.0.2/jmods \
    --verbose \
    --add-modules java.base,java.xml,jdk.unsupported,java.sql,java.instrument \
    --output /usr/lib/jvm/jdk-10.0.2-min \
    --compress 2 \
    --no-header-files

FROM jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/jdk-10.0.2-min /usr/lib/jvm/jdk-10.0.2-min

ENV JAVA_HOME=/usr/lib/jvm/jdk-10.0.2-min \
    PATH=$PATH:/usr/lib/jvm/jdk-10.0.2-min/bin
