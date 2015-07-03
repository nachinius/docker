# Developement server for EACO
#
# use docker-osx-dev for rsync your dev foler
#
# Spin the dev server by running
# ```
#     docker run -d -P -v "$PWD":/code nachinius/
# ```
# 
FROM node:0.12.5
MAINTAINER nachinius 

# Install Bower & Grunt
RUN npm install -g bower grunt-cli

# Set instructions on build.
WORKDIR /code

# when calling this image, you should mount a volume with your code here
VOLUME ["/code"]

# your code should have a Gruntfile, and the follwing task that will trigger
# the CI dev environment
CMD ["grunt", "serve"]

# Your app should be listening in this port
EXPOSE 9001

# livereload
EXPOSE 35729
