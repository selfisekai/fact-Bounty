FROM node:lts

RUN mkdir -p /fact-bounty-client
WORKDIR /fact-bounty-client

COPY package.json .
COPY package-lock.json .
RUN npm install
COPY . .

EXPOSE 3000
CMD ["npm", "start"]
