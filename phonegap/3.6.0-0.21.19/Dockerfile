FROM nmaas87/webratio-android-sdk:r23.0.2

# Installs PhoneGap
# Forces a create and build in order to preload libraries
ENV PHONEGAP_VERSION 3.6.0-0.21.19
RUN npm install -g npm && \
    npm install -g phonegap@${PHONEGAP_VERSION} && \
    npm install -g xmldom && \
    cd /tmp && \
    phonegap create fakeapp && \
    cd /tmp/fakeapp && \
    phonegap build android && \
    cd && \
    rm -rf /tmp/fakeapp

VOLUME ["/data"]
WORKDIR /data

EXPOSE 3000
