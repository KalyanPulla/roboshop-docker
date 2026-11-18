FROM redhat/ubi10
RUN dnf install nginx -y
ENTRYPOINT [ "nginx", "-g", "daemonoff;" ]
EXPOSE 80