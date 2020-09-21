FROM fl.hbz-nrw.de/jprante/alpine-glibc-adoptopenjdk15 AS packager

RUN jlink \
    --module-path /usr/lib/jvm/jdk-15+36/jmods \
    --verbose \
    --add-modules java.se \
    --output /usr/lib/jvm/adoptopenjdk15-se \
    --strip-java-debug-attributes \
    --compress 2 \
    --no-header-files \
    --no-man-pages

FROM fl.hbz-nrw.de/jprante/alpine-glibc

COPY --from=packager /usr/lib/jvm/adoptopenjdk15-se /usr/lib/jvm/adoptopenjdk15-se

ENV JAVA_HOME=/usr/lib/jvm/adoptopenjdk15-se \
    PATH=$PATH:/usr/lib/jvm/adoptopenjdk15-se/bin
