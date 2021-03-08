# Frontend application with React: React is a javascript framework, we will first generate static files and then serve them with nginx. We will do multistage building
---
# Use node:12-alpine as base image
# Copy package.json and package-lock.json
# Download all javascript dependencies of the React application with `npm install`
# Then copy rest of the application
# Generate static html files with `npm run build`
# For the second stage use nginx as base image
# Application will expose the standard nginx port
# Copy "build" directory from first stage to /usr/share/nginx/html