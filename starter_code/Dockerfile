# TODO: Select Base Image
# FROM ...

FROM eclipse-temurin:25-noble AS build
WORKDIR /app 
COPY ./demo ./
RUN ./mvn dependency:go-offline
RUN ./mvn package -DskipTests

# Second Stage - Run the packaged app
FROM eclipse-temurin:25-noble
WORKDIR /app
COPY --from=build /app/Demo.class ./
ENTRYPOINT [ "java", "Demo" ]

# TODO: Set working directory
# WORKDIR ...




# TODO: Copy JAR file
# COPY ...

# TODO: Set Entrypoint
# ENTRYPOINT ...
