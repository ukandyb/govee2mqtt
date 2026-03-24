ARG BUILD_FROM
FROM abuk/govee2mqtt:2025.11.25-60a39bcc AS govee2mqtt
FROM $BUILD_FROM
COPY run.sh /run.sh
RUN chmod a+x /run.sh
COPY --from=govee2mqtt /app/govee /app/
COPY --from=govee2mqtt /app/assets /app/assets/
COPY --from=govee2mqtt /app/AmazonRootCA1.pem /app/
ENTRYPOINT ["/init"]
CMD [ "/run.sh" ]
