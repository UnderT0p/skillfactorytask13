# Makefile for releasing podinfo
#
# The release version is controlled from pkg/version

REGISTRY_URL: $(CI_REGISTRY)
IMAGE_TAG: $(CI_COMMIT_BRANCH)-$(CI_COMMIT_SHORT_SHA)
IMAGE: $(CI_REGISTRY_IMAGE)-$(CI_COMMIT_BRANCH)-$(CI_COMMIT_SHORT_SHA)
RELEASE: $(CI_REGISTRY_IMAGE:latest)

build-container:
	docker build --pull -t $(IMAGE) .
	docker push $(IMAGE)
	docker images


test-container:
	@docker run --rm -d --name podinfo $(IMAGE)
	docker exec podinfo curl -s localhost:9898 | grep -e hostname -e logo -e goos -e goarch -e num_cpu
	@docker images
	@docker ps

push-container:
	docker pull $(IMAGE)
	docker tag $(IMAGE) $(RELEASE)
	docker push $(RELEASE)
