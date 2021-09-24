ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
EXPOSE 3001/tcp

RUN apk add --no-cache \
    nodejs \
    npm \
    ffmpeg \
    git && \
    cd / && \
    git clone https://github.com/sysreq0/ring-hassio-side.git && \
    cd ring-hassio-side/ring_hassio && \
    npm install --unsafe-perm && \
    chmod a+x run.sh

CMD [ "/ring-hassio-side/ring_hassio/run.sh" ]
