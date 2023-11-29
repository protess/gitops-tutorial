FROM alpine

RUN apk fix && \
    apk --no-cache --update add git git-lfs gpg less openssh patch rsync curl yq jq&& \
    apk add mycli --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing && \
    git lfs install && \
    wget https://github.com/cli/cli/releases/download/v2.23.0/gh_2.23.0_linux_amd64.tar.gz && \
    tar -zxvf gh_2.23.0_linux_amd64.tar.gz && \
    chmod +x gh_2.23.0_linux_amd64/bin/gh && \
    rsync -az --remove-source-files gh_2.23.0_linux_amd64/bin/ /usr/bin && \
    wget -O argocd https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64 && \
    chmod +x ./argocd && \
    mv ./argocd /usr/bin

WORKDIR /

CMD ["/bin/sh"]