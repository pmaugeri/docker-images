FROM frolvlad/alpine-python3

RUN apk update
RUN apk add ca-certificates
RUN update-ca-certificates
RUN apk add wget
RUN pip3 install --upgrade pip
RUN pip3 install --upgrade setuptools
RUN apk add build-base
RUN apk add libffi-dev openssl-dev python3-dev
RUN pip3 install edgegrid-python
RUN apk add nodejs

# Install HTTPie, curl, bind-tools (dig) and EdgeGrid plugin
RUN apk add httpie
RUN apk add curl
RUN apk add bind-tools
RUN pip install httpie-edgegrid

# Install Akamai CLI and packages
RUN wget https://github.com/akamai/cli/releases/download/1.0.2/akamai-1.0.2-linux386
RUN chmod +x akamai-1.0.2-linux386
RUN mv akamai-1.0.2-linux386 /usr/bin/akamai
RUN apk add npm
RUN akamai install property
RUN akamai install property-manager
RUN akamai install image-manager
RUN akamai install cps
RUN akamai install visitor-prioritization
RUN ln -s /root/data/.edgerc /root/.edgerc
