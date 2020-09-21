FROM fl.hbz-nrw.de/jprante/alpine-glibc-zulu15-jdk AS packager

RUN jlink \
    --module-path /usr/lib/jvm/zulu15.27.17-ca-jdk15.0.0-linux_x64/jmods \
    --verbose \
    --add-modules java.base,java.xml,jdk.unsupported,java.sql,java.instrument,jdk.management,jdk.compiler \
    --output /usr/lib/jvm/zulu15-min \
    --strip-java-debug-attributes \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM fl.hbz-nrw.de/jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/zulu15-min /usr/lib/jvm/zulu15-min

ENV JAVA_HOME=/usr/lib/jvm/zulu15-min \
    PATH=$PATH:/usr/lib/jvm/zulu15-min/bin
