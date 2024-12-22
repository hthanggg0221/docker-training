FROM nrhevu/docker-training-s1:amd

COPY test_copy_file.txt /root/

WORKDIR /root

RUN apt-get update && apt-get install -y tree

ENV YOU="thanghv235828"

CMD ["python", "/app/test-api.py"]

EXPOSE 8888