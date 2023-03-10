# Start from an existing app image
FROM bkimminich/juice-shop:v12.7.0

WORKDIR /juice-shop

# Add in the Contrast agent
RUN npm install --production @contrast/agent

# Change the startup command to preload Contrast agent
CMD ["node", "-r", "@contrast/agent", "build/app"]
