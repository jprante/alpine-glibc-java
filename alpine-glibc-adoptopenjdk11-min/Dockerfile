FROM fl.hbz-nrw.de/jprante/alpine-glibc-adoptopenjdk11 AS packager

RUN jlink \
    --module-path /usr/lib/jvm/openjdk-11.0.8_10/jmods \
    --verbose \
    --add-modules java.base,java.xml,jdk.unsupported,java.sql,java.instrument,jdk.management,jdk.compiler \
    --output /usr/lib/jvm/adoptopenjdk11-min \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM fl.hbz-nrw.de/jprante/alpine-glibc

RUN apk add --no-cache libstdc++

COPY --from=packager /usr/lib/jvm/adoptopenjdk11-min /usr/lib/jvm/adoptopenjdk11-min

ENV JAVA_HOME=/usr/lib/jvm/adoptopenjdk11-min \
    PATH=$PATH:/usr/lib/jvm/adoptopenjdk11-min/bin
