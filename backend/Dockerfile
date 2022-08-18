# build stage
FROM golang:1.18 AS builder
ADD . /src/
RUN cd /src/ && go build -o backend

# final stage
FROM alpine
WORKDIR /app
COPY --from=builder /src/backend /app/
RUN apk add libc6-compat
EXPOSE 6379/tcp
ENTRYPOINT ./backend

# FROM golang:1.18-alpine

# WORKDIR /app

# COPY . ./
# RUN go mod download

# COPY *.go ./

# RUN go get backend

# RUN go build -o /backend

# EXPOSE 6379/tcp

# CMD [ "/backend" ]

# STAGE 1: building the executable
# FROM golang:1.18-alpine AS builder

# ADD . /src/

# Working directory will be created if it does not exist
# WORKDIR /app

# Import code
# COPY . ./

# Test code
# RUN CGO_ENABLED=0 go test

# Build the executable
# RUN CGO_ENABLED=0 go build -o /goapp .

# STAGE 2: build the container to run
# FROM scratch AS finale

# copy compiled app
# COPY --from=builder /goapp /app

# EXPOSE 6379/tcp

# run binary
# ENTRYPOINT ["/goapp"]