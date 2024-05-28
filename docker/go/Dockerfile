FROM golang:1.22.3 as go_builder

WORKDIR /app

COPY ./hello-world.go ./

RUN go build hello-world.go

# ----------------------------

FROM scratch

COPY --from=go_builder /app/hello-world /app/hello-world

ENTRYPOINT [ "./app/hello-world" ]