# Using a Node.js image for the backend
FROM node:16-alpine

# Setting the working directory
WORKDIR /app

# Installing Git and cloning the backend repository
RUN apk add --no-cache git && \
    git clone https://github.com/Anand-1432/Techdome-backend.git . && \
    npm install

# Copying the source code
COPY . .

# Exposing the port the backend listens on
EXPOSE 5000

# Starting the backend server
CMD ["npm", "start"]
