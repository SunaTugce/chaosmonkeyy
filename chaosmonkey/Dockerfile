FROM golang:1.19

# Copy the local package files to the container's workspace.
WORKDIR /go/src/chaosmonkeyy

COPY go.mod go.sum ./
RUN go mod download && go mod verify

COPY . .
RUN mkdir /usr/local/bin/ChaosMonkey
RUN go get github.com/spf13/afero@v0.0.0-20160919210114-52e4a6cfac46
RUN go get github.com/fsnotify/fsnotify@v1.3.2-0.20160816051541-f12c6236fe7b
RUN go build -v -o /usr/local/bin/ChaosMonkey ./...

# execute 
ENTRYPOINT /usr/local/bin/ChaosMonkey help

