FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install
RUN apk add --no-cache openssl libc6-compat

COPY . .

RUN npx prisma generate
RUN npx prisma migrate deploy

EXPOSE 3000

CMD ["npm", "run", "start"]