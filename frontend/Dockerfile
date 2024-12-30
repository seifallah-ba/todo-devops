# Build Stage
FROM node:18 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

#Install globally react-scripts
RUN npm install -g react-scripts

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the React application
RUN npm run build

# Production Stage
FROM nginx:1.25-alpine

# Copy built files from the build stage
COPY --from=build /app/build /usr/share/nginx/html

# Expose the port used by Nginx
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
