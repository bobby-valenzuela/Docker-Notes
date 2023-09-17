Note that in the package.json where we define the "dev" script, we use the '-L' flag. This is needed for Docker to work with nodemon when runnin on a Windows machine. 
```json
"scripts": {
    "dev": "nodemon -L app.js"
  },
```

<br>

# Build Docker Image
``` sh
  cd api && sudo docker build -t mynodeapi_img:1.0 .
```

<br>

# Run container on (port 4000)

<br>

## Option 1 (no volume)
```bash
sudo docker run --name mynodeapp_c1-p 4000:4000 --rm mynodeapi_img:1.0
```
Adding "rm" above to remove container once stopping.

<br>

# Option 2 (with volume)
### Format:
```sh
sudo docker run --name mynodeapp_c1-p 4000:4000 --rm -v <local_dir>:<container_dir> -v /app/node_modules mynodeapi_img:1.0
```
<br>
### Example:
```bash
sudo docker run --name mynodeapp_c1-p 4000:4000 --rm -v C:\Users\Me\Documents\mydockerapp\:/dockerapp -v /app/node_modules mynodeapi_img:1.0
```
