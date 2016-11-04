FROM java:8

MAINTAINER delivery-engineering@netflix.com

COPY . workdir/

WORKDIR workdir

RUN mkdir /opt/clouddriver/credentials

VOLUME /opt/clouddriver/credentials

RUN GRADLE_USER_HOME=cache ./gradlew buildDeb -x test && dpkg -i ./clouddriver-web/build/distributions/*.deb

CMD ["/opt/clouddriver/bin/clouddriver"]
