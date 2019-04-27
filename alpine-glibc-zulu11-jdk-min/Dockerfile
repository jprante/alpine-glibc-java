FROM jprante/alpine-glibc-zulu11-jdk AS packager

RUN jlink \
    --module-path /usr/lib/jvm/zulu11.31.11-ca-jdk11.0.3-linux_x64/jmods \
    --verbose \
    --add-modules java.base,java.xml,jdk.unsupported,java.sql,java.instrument,jdk.management,jdk.compiler \
    --output /usr/lib/jvm/zulu11-min \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/zulu11-min /usr/lib/jvm/zulu11-min

ENV JAVA_HOME=/usr/lib/jvm/zulu11-min \
    PATH=$PATH:/usr/lib/jvm/zulu11-min/bin
