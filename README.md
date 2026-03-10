First you run 
docker run -d -p 80:80 docker/getting-started
This runs the container, maps the port 80 of the hsot port 80 to the container and then understands the image to use

You must download the provided zip from
http://localhost/tutorial/our-application

Once extracted create a file named Dockerfile and paste the code
FROM node: 18-alpine
WORKDIR /app
COPY . . 
RUN yard install --production
CMD ['node', 'src/index.js']

Then go to the terminal with the app directory with the Dockerfile and build the container image
docker build -t getting-started

Finally, to start the container using the docker run command
docker run -dp 3000:3000 getting-started

After a few seconds, open the browser to
http://localhost:3000
