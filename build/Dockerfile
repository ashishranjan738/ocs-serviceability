FROM registry.access.redhat.com/ubi7/ubi-minimal:latest

ENV OPERATOR=/usr/local/bin/ocs-serviceability \
    USER_UID=1001 \
    USER_NAME=ocs-serviceability

# install operator binary
COPY build/_output/bin/ocs-serviceability ${OPERATOR}

COPY build/bin /usr/local/bin
RUN  /usr/local/bin/user_setup

COPY build/must-gather /usr/bin

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
