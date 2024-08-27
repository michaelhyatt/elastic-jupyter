FROM ubuntu:latest

ARG TARGETPLATFORM
ENV ARCH="unknown"

RUN apt-get update \
    && apt-get install -y wget uuid-runtime curl git jq

RUN cd / \
    && if [ "$TARGETPLATFORM" = "linux/amd64" ]; then \
      export ARCH="x86"; \
    elif [ "$TARGETPLATFORM" = "linux/arm64" ]; then \
      export ARCH="arm64"; \
    else \
      echo "Unknown architecture"; \
      exit 1; \
    fi \
    && curl -Lso - https://cdn.cribl.io/dl/4.8.1/cribl-4.8.1-8a1f8821-linux-$ARCH.tgz | tar zxv \
    && rm -rf /cribl/local/cribl/auth

EXPOSE 9000

##### Add startup scripts #####
ADD start.sh /
RUN chmod +x /start.sh
CMD ["/start.sh"]