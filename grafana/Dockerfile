FROM grafana/grafana:main-ubuntu

# Switch to root user to perform installations
USER root

# Update and install necessary packages
RUN apt update && apt upgrade -y && \
    apt install -y nano sudo

