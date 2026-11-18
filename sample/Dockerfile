FROM redhat/ubi10
RUN dnf install nginx -y
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
EXPOSE 80