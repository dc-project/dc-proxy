NAME = projectdc/dc-proxy
VERSION = nginx
RELEASE = dn #deb nginx

all: build

build:
	docker build --tag=$(NAME):$(VERSION) .

tag_latest:
	docker tag $(NAME):$(VERSION) $(NAME):$(RELEASE)

release: tag_latest
	docker push $(NAME):$(RELEASE)