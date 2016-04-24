FROM mhart/alpine-node
MAINTAINER Nicolas Schwarzentrub "nicolas.schwarzentrub@gmail.com"

ENV VERSION "v2.1.8-M1."
ENV FOLDER "swagger-ui"
ENV API_URL "http://petstore.swagger.io/v2/swagger.json"
ENV API_KEY "**None**"
ENV SWAGGER_JSON "/app/swagger.json"

WORKDIR /app

RUN apk update && apk add openssl
RUN wget -qO- https://github.com/swagger-api/swagger-ui/archive/$VERSION.tar.gz | tar xvz
RUN cp -r $FOLDER-$VERSION/dist/* . && rm -rf $FOLDER-$VERSION
RUN npm install -g http-server
RUN apk del openssl

ADD run.sh run.sh

# webserver port
EXPOSE 80

CMD ["sh", "run.sh"]
