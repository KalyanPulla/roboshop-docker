FROM redhat/ubi10 AS builder
RUN curl -fsSL https://rpm.nodesource.com/setup_20.x | bash -
RUN dnf install unzip nodejs -y
RUN rm -rf /usr/share/nginx/html/*
ADD https://raw.githubusercontent.com/raghudevopsb89/roboshop-microservices/main/artifacts/frontend.zip /tmp
WORKDIR /tmp
RUN unzip -o frontend.zip
RUN rm -rf frontend.zip
RUN npm install ; npm run build

FROM redhat/ubi10
RUN curl -fsSL https://rpm.nodesource.com/setup_20.x | bash -
RUN dnf install nginx -y
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
EXPOSE 80
COPY --from=builder /tmp/out/ /usr/share/nginx/html
