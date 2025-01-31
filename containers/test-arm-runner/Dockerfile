FROM docker.io/library/ubuntu:24.04 AS test-arm-runner
ARG TARGETARCH TARGETOS TARGETPLATFORM TARGETVARIANT

RUN --mount=type=cache,target=/var/cache/apt,sharing=locked,id=${TARGETPLATFORM}/var/cache/apt \
    export DEBIAN_FRONTEND=noninteractive && \
    apt-get update -qq && \
    apt-get install -qy --no-install-recommends \
      curl \
    && apt-get autoremove -y && rm -rf /var/lib/apt/lists/*
