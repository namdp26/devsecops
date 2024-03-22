# Stage build dependencies
FROM alpine:3.12.1 as build

ARG VERSION=v2.3.4

RUN apk add curl --no-cache \
 && curl -ksSL -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/${VERSION}/argocd-linux-amd64 \
 && chmod +x /usr/local/bin/argocd

#Set Argocd ENVs
ENV ARGOCD_AUTH_TOKEN=

ENV ARGOCD_SERVER=

# Stage final
FROM alpine:3.12.1

COPY --from=build /usr/local/bin/argocd /usr/local/bin/argocd