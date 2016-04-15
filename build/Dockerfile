# Alpine Linux standard

FROM youske/alpine-std:latest
MAINTAINER youske miyakoshi <youske@gmail.com>

LABEL com.geeplus.description="alpine elixir erlang image" \
      com.geeplus.role="baseimage"

ENV PATH=$PATH \
    LANG=C.UTF-8 \
    PACKAGE='bash ca-certificates elixir erlang erlang-tools erlang-stdlib erlang-ssh erlang-mnesia erlang-crypto erlang-syntax-tools erlang-kernel erlang-compiler' \
    BUILDPACK='wget build-base linux-headers' \
    WORK_DIR=/home/admin

RUN apk update --no-cache
RUN apk add ${PACKAGE} --no-cache && apk add ${BUILDPACK} --no-cache -t buildpack

# remove
RUN apk del buildpack --no-cache && rm -rf /tmp/* /var/cache/apk/*

WORKDIR ${WORK_DIR}
CMD ["/bin/bash"]
