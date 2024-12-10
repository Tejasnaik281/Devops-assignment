# Using a Node.js image for building the React app
FROM node:16-alpine AS builder

# Setting the working directory
WORKDIR /app

# Copying, installing dependencies and cloning the frontend repo
RUN apk add --no-cache git && \
    git clone https://github.com/Anand-1432/Techdome-frontend.git . && \
    npm install

# Copying the source code and building the React app
COPY . .
RUN npm run build

# Using Nginx to serve the React app
FROM nginx:alpine

# Copying the build output to Nginx's default directory
COPY --from=builder /app/build /usr/share/nginx/html

# Exposing port 80 for the frontend
EXPOSE 80

# Starting Nginx
CMD ["nginx", "-g", "daemon off;"]
