FROM hypriot/rpi-alpine

LABEL Description="Fork of Eclipse Mosquitto MQTT Broker. This Fork uses the hypriot/rpi-alpine as base image"

RUN apk add mosquitto=1.4.10-r2 && \
    mkdir -p /mosquitto/config /mosquitto/data /mosquitto/log && \
    cp /etc/mosquitto/mosquitto.conf /mosquitto/config && \
    chown -R mosquitto:mosquitto /mosquitto && \
    rm -rf /var/cache/apk/*

COPY docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
