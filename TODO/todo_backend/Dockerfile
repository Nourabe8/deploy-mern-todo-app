FROM node:alpine

# Switch to root user to adjust ownership
USER root

# Create the app directory and set proper permissions
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

# Copy package files with the correct ownership
COPY --chown=node:node package*.json ./

# Switch back to the node user
USER node

# Install dependencies as the node user
RUN npm install

# Copy the rest of the app files with the correct ownership
COPY --chown=node:node . .

EXPOSE 3001

# Start the app
CMD [ "node", "server.js" ]

