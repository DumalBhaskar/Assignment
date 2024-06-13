# Stage 1: Build Stage
FROM node:20-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Stage 2: Production Stage
FROM node:14-alpine

WORKDIR /app

COPY --from=build /app .

EXPOSE 3001
CMD ["npm", "start"]
