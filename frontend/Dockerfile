FROM node:18-alpine AS build
WORKDIR /app
COPY sigs_frontend/package.json ./
RUN npm install
COPY sigs_frontend ./
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]