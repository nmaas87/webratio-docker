FROM nmaas87/webratio-android-sdk:r25.2.4

# Installs PhoneGap
# Forces a create and build in order to preload libraries
ENV PHONEGAP_VERSION 6.4.2
# Remove upgrade of npm because it breaks npm
# RUN npm install -g npm && \
RUN npm install -g phonegap@${PHONEGAP_VERSION} && \
    npm install -g xmldom && \
    npm install -g xpath && \
    cd /tmp && \
    phonegap create fakeapp && \
    cd /tmp/fakeapp && \
    phonegap build android && \
    cd && \
    rm -rf /tmp/fakeapp

VOLUME ["/data"]
WORKDIR /data

EXPOSE 3000
