FROM redhat/ubi10
RUN curl -fsSL https://rpm.nodesource.com/setup_20.x | bash -
RUN dnf install nginx unzip nodejs -y
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
EXPOSE 80
RUN rm -rf /usr/share/nginx/html/*
ADD https://raw.githubusercontent.com/raghudevopsb89/roboshop-microservices/main/artifacts/frontend.zip /tmp
WORKDIR /tmp
RUN unzip frontend.zip
RUN rm -rf frontend.zip
RUN npm install ; npm run build
RUN rm -rf /usr/share/nginx/html/*
RUN cp -r out/* /usr/share/nginx/html/