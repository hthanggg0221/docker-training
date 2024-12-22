# Phần 1
Chạy 1 vài câu lệnh cơ bản với Docker.

## Kéo 1 image từ Docker Hub
Kéo image `nrhevu/docker-training-s1` từ Docker Hub. Nếu sử dụng chip Intel, AMD thì kéo image `nrhevu/docker-training-s1:amd` về. Nếu sử dụng chip Apple Silicon hay Snapdragon thì kéo image `nrhevu/docker-training-s1:arm` về.

Câu lệnh sử dụng:
```
docker pull nrhevu/docker-training-s1:amd
```

## Hiển thị các image hiện có trong registry local
Kết quả hiển thị trên màn hình:
```
REPOSITORY                  TAG       IMAGE ID       CREATED       SIZE
nrhevu/docker-training-s1   amd       f413332958a8   9 hours ago   803MB
```

## Chạy một image
Chạy image `nrhevu/docker-training-s1` thành container sử dụng câu lệnh `docker run`

Kết quả hiển thị trên màn hình:
```
hello world!
```

## Dừng / Xóa một container
Dừng và xoá container đang chạy

Câu lệnh sử dụng:
```
Dừng: docker stop 877cb0fe04b07a6cde5166b2c6d2989f6bfb6e7ef59e8f221579f1b9410208fb
Xóa: docker rm -f 877cb0fe04b07a6cde5166b2c6d2989f6bfb6e7ef59e8f221579f1b9410208fb
```

## Chạy image với câu lệnh chỉ định
Chạy image `nrhevu/docker-training-s1` với câu lệnh `python test_custom.py`

Kết quả hiển thị trên màn hình:
```
                                       ._ o o
                                       \_`-)|_
                                    ,""       \
                                  ,"  ## |   ಠ ಠ.
                                ," ##   ,-\__    `.
                              ,"       /     `--._;)
                            ,"     ## /
                          ,"   ##    /
```

## Hiển thị các container Docker đang chạy
Kết quả hiển thị trên màn hình:
```
CONTAINER ID   IMAGE                           COMMAND                CREATED         STATUS         PORTS     NAMES
d09c50cb32e4   nrhevu/docker-training-s1:amd   "python test_api.py"   7 minutes ago   Up 7 minutes             bold_colden
```

## Chạy một image với câu lệnh volume
Chạy image `nrhevu/docker-training-s1` với câu lệnh `python test_volume.py` và tạo volume từ một thư mục đến ổ `/mount` khi chạy docker. Lúc này code sẽ tạo file `volume.txt` trong thư mục chỉ định

Kết quả hiển thị trên màn hình:
```
...
```
Nội dung trong file `volume.txt`:
```
...
```


## Chạy một image ở chế độ ngầm (background)
Chạy image `nrhevu/docker-training-s1` với câu lệnh `python test_api.py` ở chế độ ngầm.

Câu lệnh sử dụng:
```
docker run -d nrhevu/docker-training-s1:amd python test_api.py
```

## Xem logs của một container Docker đang chạy
Show log của container vừa chạy

Kết quả hiển thị trên màn hình:
```
INFO:     Started server process [1]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://0.0.0.0:8888 (Press CTRL+C to quit)
```

## Mở cổng cho Docker
Chạy image `nrhevu/docker-training-s1` với câu lệnh `python test_api.py` và tạo thông kết nối đến cổng 8888 trong container. Sử dụng câu lệnh `curl localhost:8888` hoặc ứng dụng Postman để gọi API được cài trong Docker.


Kết quả hiển thị trên màn hình:
```
...
```


## Truy cập vào một container đang chạy
Truy cập vào docker đang chạy và tìm file `starter.txt`, sử dụng lệnh `cat [FILE]` để xem nội dung.

Nội dung của File: 
```
English: Hello
Vietnamese: Xin chào
French: Bonjour
Spanish: Hola
German: Hallo
Italian: Ciao
Portuguese: Olá
Russian: Здравствуйте (Zdravstvuyte)
Chinese (Mandarin): 你好 (Nǐ hǎo)
Japanese: こんにちは (Konnichiwa)
Korean: 안녕하세요 (Annyeonghaseyo)
Arabic: مرحبا (Marhaban)
Hindi: नमस्ते (Namaste)
Swedish: Hej
Dutch: Hallo
Greek: Γειά σας (Yia sas)
Turkish: Merhaba
Thai: สวัสดี (Sawasdee)
Hebrew: שלום (Shalom)
Zulu: Sawubona#
```

## Sao chép tệp từ/vào một container Docker
Lấy file `starter.txt` ra bên ngoài container

Nội dung của File: 
```
English: Hello
Vietnamese: Xin chào
French: Bonjour
Spanish: Hola
German: Hallo
Italian: Ciao
Portuguese: Olá
Russian: Здравствуйте (Zdravstvuyte)
Chinese (Mandarin): 你好 (Nǐ hǎo)
Japanese: こんにちは (Konnichiwa)
Korean: 안녕하세요 (Annyeonghaseyo)
Arabic: مرحبا (Marhaban)
Hindi: नमस्ते (Namaste)
Swedish: Hej
Dutch: Hallo
Greek: Γειά σας (Yia sas)
Turkish: Merhaba
Thai: สวัสดี (Sawasdee)
Hebrew: שלום (Shalom)
Zulu: Sawubona
```