FROM fl.hbz-nrw.de/jprante/alpine-glibc-zulu11-jdk AS packager

RUN jlink \
    --module-path /usr/lib/jvm/zulu11.41.23-ca-jdk11.0.8-linux_x64/jmods \
    --verbose \
    --add-modules java.se \
    --output /usr/lib/jvm/zulu11-se \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM fl.hbz-nrw.de/jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/zulu11-se /usr/lib/jvm/zulu11-se

ENV JAVA_HOME=/usr/lib/jvm/zulu11-se \
    PATH=$PATH:/usr/lib/jvm/zulu11-se/bin
