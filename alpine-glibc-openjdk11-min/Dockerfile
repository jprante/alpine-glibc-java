FROM jprante/alpine-glibc-openjdk11 AS packager

RUN jlink \
    --module-path /usr/lib/jvm/jdk-11/jmods \
    --verbose \
    --add-modules java.base,java.xml,jdk.unsupported,java.sql,java.instrument,jdk.management,jdk.compiler \
    --output /usr/lib/jvm/jdk-11-min \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/jdk-11-min /usr/lib/jvm/jdk-11-min

ENV JAVA_HOME=/usr/lib/jvm/jdk-11-min \
    PATH=$PATH:/usr/lib/jvm/jdk-11-min/bin
