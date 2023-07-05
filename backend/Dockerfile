FROM golang:1.19

WORKDIR /workspace

COPY . .

RUN go mod tidy

RUN go clean && GOOS=linux GOARCH=amd64 go build -o backend  -ldflags="-X main.BuildStamp=`date +%Y-%m-%d.%H:%M:%S`" backend.go

CMD [ "./backend" ]
