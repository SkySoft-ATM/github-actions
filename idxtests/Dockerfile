FROM alpine:3.12

ARG IDXTESTS_VERSION=1.1
ENV IDXTESTS_VERSION=$IDXTESTS_VERSION

ENV PATH /idxtests:$PATH

RUN apk --no-cache add \
    curl \
    && curl -LO https://github.com/SkySoft-ATM/idxtests/releases/download/v${IDXTESTS_VERSION}/idxtests_${IDXTESTS_VERSION}_Linux_x86_64.tar.gz && \
    tar xzf idxtests_${IDXTESTS_VERSION}_Linux_x86_64.tar.gz && \
    rm idxtests_${IDXTESTS_VERSION}_Linux_x86_64.tar.gz && \
    mv /idxtests /usr/local/bin

COPY entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]