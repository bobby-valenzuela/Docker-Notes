# Docker-Notes

Build docker image:
```sh
cd api && sudo docker build -t mynodeapi_img:1.0 .
```

<br>

Run container on port 4000
```sh
sudo docker run --name mynodeapp_c1 -d -p 4000:4000 mynodeapi_img:1.0
```
