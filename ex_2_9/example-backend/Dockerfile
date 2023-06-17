FROM golang:1.16

WORKDIR /usr/src/app

# go.mod and go.sum must be copied in root directory 
COPY go.mod go.sum ./

COPY . .
RUN go build
RUN test ./...

ENV REQUEST_ORIGIN=http://localhost

CMD ["./server"]


