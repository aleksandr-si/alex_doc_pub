FROM ubuntu:20.04 AS build
RUN apt-get update 
RUN apt install -y default-jdk
COPY Simple.java /tmp/Simple.java
RUN javac /tmp/Simple.java

FROM ubuntu:20.04 
RUN apt-get update && apt install -y default-jre
COPY --from=build /tmp/Simple.class /tmp/

#ENTRYPOINT ["sleep", "100000"]
