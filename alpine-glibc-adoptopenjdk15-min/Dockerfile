FROM fl.hbz-nrw.de/jprante/alpine-glibc-adoptopenjdk15 AS packager

RUN jlink \
    --module-path /usr/lib/jvm/jdk-15+36/jmods \
    --verbose \
    --add-modules java.base,java.xml,jdk.unsupported,java.sql,java.instrument,jdk.management,jdk.compiler \
    --output /usr/lib/jvm/adoptopenjdk15-min \
    --strip-java-debug-attributes \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM fl.hbz-nrw.de/jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/adoptopenjdk15-min /usr/lib/jvm/adoptopenjdk15-min

ENV JAVA_HOME=/usr/lib/jvm/adoptopenjdk15-min \
    PATH=$PATH:/usr/lib/jvm/adoptopenjdk15-min/bin
