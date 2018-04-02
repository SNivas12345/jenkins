pipeline {
  agent {
    docker {
      image 'npm'
      args '''FROM node:6-alpine

# Create server working directory
RUN mkdir -p /home/node/app
WORKDIR /home/node/app

# Install server dependencies
COPY /express-image/package.json /home/node/app
RUN npm install

# Copy node Application
COPY app.js /home/node/app

# Open port
EXPOSE 9000

CMD ["npm", "start"
'''
    }
    
  }
  stages {
    stage('Build') {
      steps {
        build(job: 'Build', propagate: true, quietPeriod: 1, wait: true)
      }
    }
  }
  environment {
    jenkins = '1'
  }
}