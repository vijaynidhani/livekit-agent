FROM debian:12

RUN apt-get update && \
    apt-get install -y wget gnupg && \
    wget -O- https://deb.kamailio.org/kamailiodebkey.gpg | gpg --dearmor > /usr/share/keyrings/kamailio.gpg && \
    echo "deb [signed-by=/usr/share/keyrings/kamailio.gpg] http://deb.kamailio.org/kamailio57 bookworm main" \
        > /etc/apt/sources.list.d/kamailio.list && \
    apt-get update && \
    apt-get install -y kamailio kamailio-extra-modules && \
    rm -rf /var/lib/apt/lists/*

CMD ["kamailio", "-DD", "-E", "-d", "4", "-f", "/etc/kamailio/kamailio.cfg"]
