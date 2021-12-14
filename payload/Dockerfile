FROM maven:3-jdk-11 as builder
RUN mkdir /build && cd build; git clone https://github.com/Cybereason/Logout4Shell && cd Logout4Shell
RUN cd /build/Logout4Shell && mvn package

FROM nginx
COPY files/ /usr/share/nginx/html/
COPY --from=builder /build/Logout4Shell/target/classes/ /usr/share/nginx/html/
