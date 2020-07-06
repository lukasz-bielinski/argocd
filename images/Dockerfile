FROM argoproj/argocd:v1.6.1

# Switch to root for the ability to perform install
USER root

# Install tools needed for your repo-server to retrieve & decrypt secrets, render manifests 
# (e.g. curl, awscli, gpg, sops)
RUN apt-get update && \
    apt-get install -y \
        curl \
        gpg && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    curl -o /usr/local/bin/calicoctl -L https://github.com/projectcalico/calicoctl/releases/download/v3.15.0/calicoctl && \
    chmod +x /usr/local/bin/calicoctl

# Switch back to non-root user
USER 5107
