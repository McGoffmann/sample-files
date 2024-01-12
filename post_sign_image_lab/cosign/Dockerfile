ARG cosign-password
FROM gcr.io/projectsigstore/cosign:v2.2.2 as cosign-bin
FROM docker:25.0.0-rc.1-alpine3.19
ENV COSIGN_PASSWORD $cosign-password
COPY --from=cosign-bin /ko-app/cosign /usr/local/bin/cosign
RUN cosign generate-key-pair
ENTRYPOINT [ "cosign" ]