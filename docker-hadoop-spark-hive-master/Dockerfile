FROM livingobjects/jre8
VOLUME /temp
ADD spark-es-tag-1.0.jar app.jar
RUN bash -c 'touch /app.jar'
ENTRYPOINT [ "java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar" ]