FROM golang:1.18-alpine

WORKDIR /app

COPY . ./
RUN go mod download

COPY *.go ./

RUN go get backend

RUN go build -o /backend

EXPOSE 6379/tcp

CMD [ "/backend" ]