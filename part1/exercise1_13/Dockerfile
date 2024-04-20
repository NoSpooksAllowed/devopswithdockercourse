FROM golang:1.16

WORKDIR /usr/src/app

COPY go.mod go.sum ./
RUN go mod download && go mod verify

COPY . .

RUN go build -v -o . ./...

RUN go test ./...

EXPOSE 8080

ENV REQUEST_ORIGIN=http://localhost:5000

CMD ./server
