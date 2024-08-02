FROM node:21 AS backend-builder
WORKDIR /app
COPY package*.json ./
RUN npm i
COPY . .
FROM node:21-slim
WORKDIR /app
COPY --from=backend-builder /app .
COPY .env.sample .env
EXPOSE 5000
CMD ["npm", "start"]
