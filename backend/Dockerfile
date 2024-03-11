# specify the node base image with your desired version node:<version>
FROM node:18-alpine

# Set the working directory in the container
WORKDIR /

# Copy the current directory contents into the container at /app
COPY . /

# replace this with your application's default port
EXPOSE 3000

CMD ["node", "index.js"]