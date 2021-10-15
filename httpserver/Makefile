export tag=v1.0
build:
	echo "building httpserver binary"
	mkdir -p bin/amd64
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/amd64 .

release: build
	echo "building httpserver container"
	docker build -t registry.cn-hangzhou.aliyuncs.com/yzqingqing/httpserver:${tag} .

push: release
	echo "pushing registry.cn-hangzhou.aliyuncs.com/yzqingqing/httpserver"
	docker push registry.cn-hangzhou.aliyuncs.com/yzqingqing/httpserver:v1.0
