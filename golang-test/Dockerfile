# Run simple golang application in a container
#
# docker run -d \
#	 --name go_project \
#	 dan/golang
#
FROM golang:alpine as build
WORKDIR /go/bin
COPY . .
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build

FROM scratch
COPY --from=build /go/bin/docker-demo-2  /go/bin/docker-demo-2
ENTRYPOINT [ "/go/bin/docker-demo-2" ]
EXPOSE 9000/tcp

