FROM bitnami/moodle:latest

USER root

# Install required packages
RUN install_packages wget unzip

# Create plugin directory and download plugin
RUN mkdir -p /bitnami/moodle/local/prometheus \
    && wget -qO /tmp/plugin.zip "https://moodle.org/plugins/download.php/30587/local_prometheus_moodle42_2023112700.zip" \
    && unzip /tmp/plugin.zip -d /bitnami/moodle/local/ \
    && mv /bitnami/moodle/local/local_prometheus_moodle42_2023112700 /bitnami/moodle/local/prometheus \
    && rm /tmp/plugin.zip

# Set permissions
RUN chown -R daemon:daemon /bitnami/moodle/local/prometheus \
    && chmod -R 755 /bitnami/moodle/local/prometheus

USER 1001