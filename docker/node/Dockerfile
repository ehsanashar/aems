FROM node:18

# Set working directory
WORKDIR /var/www/app

# Copy only package.json and package-lock.json first (for better caching)
COPY ./app/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app
COPY ./app .

# Build the assets
RUN npm run build

# Default command (do nothing by default or use for dev server if needed)
CMD [ "npm", "run", "build" ]
