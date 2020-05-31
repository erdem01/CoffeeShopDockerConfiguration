FROM openjdk:latest
MAINTAINER Erdem Caglayan "erdemcaglayan1@gmail.com"
ENV REFRESHED_AT 2017-10-08
RUN mkdir -p /usr/src/coffeeshop/config
RUN mkdir -p /usr/src/coffeeshop/logs
ADD CoffeeShopServices.war /usr/src/coffeeshop/CoffeeShopServices.war
ADD application.properties /usr/src/coffeeshop/config/application.properties
WORKDIR /usr/src/coffeeshop/ 
ENTRYPOINT ["java", "-jar", "CoffeeShopServices.war"]
