# Use the latest LTS version of Node.js
FROM node:lts

# Set the working directory inside the container
WORKDIR /var/www/html

# Copy the rest of your application files
COPY app-next-site ./

# Install dependencies
RUN npm install

# Expose the port your app runs on
EXPOSE 3000

# Define the command to run your app
CMD ["npm", "start"]