
docker build -t nas2docker/kurento_bufferfix --build-arg http_proxy=$http_proxy --build-arg https_proxy=$https_proxy .

docker build -t nas2docker/kurento_bufferfix .


RUN mkdir -p /kurento-setup && cd /kurento-setup && git clone https://github.com/Kurento/kms-core.git \
    && cd ./kms-core \
    && cmake . \
    && make -j4 \
    && make install
