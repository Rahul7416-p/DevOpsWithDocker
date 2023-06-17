FROM  ubuntu

COPY . ./

RUN apt-get update && apt-get install -y curl

RUN curl -sL https://deb.nodesource.com/setup_16.x | bash
RUN apt install -y nodejs

WORKDIR /app

COPY package*.json  ./

RUN node -v && npm -v
RUN npm install

COPY . .

RUN REACT_APP_BACKEND_URL=http://localhost/api/ npm run build

RUN npm install -g serve

EXPOSE 5000

CMD ["serve","-s","-l", "5000", "build"]

