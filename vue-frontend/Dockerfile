
FROM node:lts-alpine AS development
WORKDIR /app
COPY package*.json ./
RUN npm install
EXPOSE 5173
CMD ["npm", "run", "dev"]


FROM development as build
COPY . .
RUN npm run build

FROM nginx:stable-alpine as production
COPY --from=build /app/dist /usr/share/nginx/html
CMD ["nginx", "-g", "daemon off;"]
