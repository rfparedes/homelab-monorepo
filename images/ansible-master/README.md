# To build this image and push to docker public registry for amd64:

docker buildx build --build-arg SSH_KEY="$(cat /Users/rich/.ssh/id_rsa)" --build-arg SSH_KEY_PUB="$(cat /Users/rich/.ssh/id_rsa.pub)" -t rich/ansible-master:TAG --platform linux/amd64 --push .