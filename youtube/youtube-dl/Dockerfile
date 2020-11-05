#
# Dockerfile for youtube-dl
#

FROM alpine
MAINTAINER kev <noreply@easypi.pro>

#RUN set -xe \
#    && apk add --no-cache ca-certificates \
#                          ffmpeg \
#                          openssl \
#                          python3 \
#                          aria2 

#RUN apk --update add python
RUN apk add --no-cache python3
RUN apk add --no-cache curl
RUN apk add --no-cache ffmpeg
RUN apk add --no-cache openssl
RUN apk add --no-cache ca-certificates

ADD https://yt-dl.org/downloads/latest/youtube-dl /usr/local/bin/youtube-dl
RUN chmod a+rx /usr/local/bin/youtube-dl
RUN ln -s /usr/bin/python3 /usr/local/bin/python 

# Try to run it so we know it works
RUN /usr/local/bin/youtube-dl --version

WORKDIR /data

ENTRYPOINT ["youtube-dl"]
CMD ["--help"]
