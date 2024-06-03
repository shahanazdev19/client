# Stage 1: Build the React application
FROM node:16.20.2-alpine as builder

WORKDIR /user/src/app

# Copy package.json and package-lock.json (or yarn.lock) to leverage Docker cache
COPY package*.json ./
#COPY package-lock.json ./
# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .
EXPOSE 3000
# Build the application
#RUN npm start

ENTRYPOINT [ "npm" ]

CMD ["start"]
# Stage 2: Serve the application with a web server
#FROM nginx:stable-alpine as production-stage

# Copy built assets from the build stage to the web server's root
#COPY --from=build-stage /usr/src/app/dist /usr/share/nginx/html

# Start Nginx and serve the application
#CMD ["nginx", "-g", "daemon off;"]
