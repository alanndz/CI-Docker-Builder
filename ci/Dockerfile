FROM ubuntu:22.04
LABEL maintainer "alanndz <alanndz7@gmail.com>"

# Indonesian Timezone (GMT+8)
ENV TZ=Asia/Makassar
WORKDIR /tmp

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
