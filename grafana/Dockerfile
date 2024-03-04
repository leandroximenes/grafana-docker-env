FROM grafana/grafana:main-ubuntu

# Define build arguments
ARG HTTP_PROXY
ARG NO_PROXY

# Set proxy environment variables
ENV HTTPS_PROXY ${HTTP_PROXY}
ENV HTTP_PROXY ${HTTP_PROXY}
ENV FTP_PROXY ${HTTP_PROXY}

# Switch to root user to perform installations
USER root

# Set up proxy for apt if HTTP_PROXY is provided
RUN if [ ! -z "$HTTP_PROXY" ]; then \
        echo "Acquire::https::Proxy \"$HTTP_PROXY\";" >> /etc/apt/apt.conf ; \
        echo "Acquire::http::Proxy \"$HTTP_PROXY\";" >> /etc/apt/apt.conf ; \
        echo "Acquire::ftp::Proxy \"$HTTP_PROXY\";" >> /etc/apt/apt.conf ; \
    fi

# Update and install necessary packages
RUN apt update && apt upgrade -y && \
    apt install -y nano sudo

