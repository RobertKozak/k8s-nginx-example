FROM alpine:3.15.0
LABEL maintainer="Robert Kozak <robertkozak@gmail.com>"

COPY /bin /usr/local/bin

RUN apk update && apk add --update --no-cache ncurses wget curl bash tree unzip && \
    rm -rf /var/cache/apk/*

RUN curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/master/contrib/install.sh | sh -s -- -b /usr/local/bin
