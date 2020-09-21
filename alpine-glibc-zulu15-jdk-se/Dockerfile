FROM fl.hbz-nrw.de/jprante/alpine-glibc-zulu15-jdk AS packager

RUN jlink \
    --module-path /usr/lib/jvm/zulu15.27.17-ca-jdk15.0.0-linux_x64/jmods \
    --verbose \
    --add-modules java.se \
    --output /usr/lib/jvm/zulu15-se \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM fl.hbz-nrw.de/jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/zulu15-se /usr/lib/jvm/zulu15-se

ENV JAVA_HOME=/usr/lib/jvm/zulu15-se \
    PATH=$PATH:/usr/lib/jvm/zulu15-se/bin
