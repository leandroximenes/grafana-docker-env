FROM nginx:latest

# Define build arguments
ARG HTTP_PROXY
ARG NO_PROXY="localhost, 127.0.0.0/8, ::1, *.eb.mil.br, 10.0.0.0/8, 0.0.0.0/32, 172.0.0.0/8, grafana"

# Set proxy environment variables
ENV HTTPS_PROXY ${HTTP_PROXY}
ENV HTTP_PROXY ${HTTP_PROXY}
ENV FTP_PROXY ${HTTP_PROXY}
ENV NO_PROXY="localhost, 127.0.0.0/8, ::1, *.eb.mil.br, 10.0.0.0/8, 0.0.0.0/32, 172.0.0.0/8, grafana"

COPY nginx.conf /etc/nginx/conf.d/default.conf