FROM node:18.0.0-alpine

ENV NODE_ENV production

WORKDIR /usr/src/app

# Run the application as a non-root user.
USER node

# Copy the rest of the source files into the image.
COPY ["./my-app", "./"]

# Expose the port that the application listens on.
EXPOSE 3000

# Run the application.
ENTRYPOINT ["npm"]
CMD ["start"]
