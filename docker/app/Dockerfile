FROM alpine:3.17

ARG UID
ARG GID
ARG RUST_VERSION

RUN apk add --update rustup build-base shadow \
    && groupadd -g $GID vscode \
    && useradd vscode -u $UID -g $GID -m

USER vscode
ENV PATH=$PATH:/home/vscode/.cargo/bin
RUN rustup-init -y -t $RUST_VERSION

WORKDIR /home/vscode/workspace
CMD ["sleep", "infinity"]
