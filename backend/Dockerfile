FROM alpine:latest

WORKDIR /app

RUN apk add --no-cache unzip wget

RUN wget https://github.com/pocketbase/pocketbase/releases/download/v0.29.3/pocketbase_0.29.3_linux_amd64.zip \
    && unzip pocketbase_0.29.3_linux_amd64.zip \
    && rm pocketbase_0.29.3_linux_amd64.zip

COPY pb_data ./pb_data
COPY pb_migrations ./pb_migrations

EXPOSE 10000

CMD ["./pocketbase", "serve", "--http=0.0.0.0:10000"]
