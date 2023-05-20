### dockerfile to nodejs
```
FROM node:latest
RUN apt update && apt install git -y
RUN git clone https://github.com/Azure-Samples/js-e2e-express-server.git
WORKDIR /js-e2e-express-server.git && \ apt update && \
         npm install -y
EXPOSE 3000
CMD ["NPM","START"]
```
### output
[preview](/ganeshreddy/ganeshreddy/npm%20image.png)

### manually 
```
sudo apt install nodejs -y
git clone https://github.com/Azure-Samples/js-e2e-express-server.git
cd /js-e2e-express-server.git
sudo apt install npm
npm -v
npm install

```
### output
[preview](/ganeshreddy/ganeshreddy/npm%20manually%20runed.png)

