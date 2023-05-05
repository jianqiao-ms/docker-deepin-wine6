# syntax=docker/dockerfile:1

FROM docker-deepin:apricot as deepin

ENV DEBIAN_FRONTEND=noninteractive
ENV AUDIO_GID=63
ENV VIDEO_GID=39
ENV GID=1000
ENV UID=1000

RUN apt update && apt install -y \
  procps  \
  x11-utils  \
  python2  \
  deepin-wine6-stable  \
  deepin-wine-helper:i386  \
  deepin-wine-runtime

RUN groupadd -o -g $GID deepin && \
    groupmod -o -g $AUDIO_GID audio && \
    groupmod -o -g $VIDEO_GID video && \
    useradd -d "/home/deepin" -m -o -u $UID -g deepin -G audio,video deepin

ENV LANGUAGE=zh_CN.UTF-8
ENV LC_ALL=zh_CN.UTF-8
ENV LANG=zh_CN.UTF-8
ENV TZ=UTC-8


