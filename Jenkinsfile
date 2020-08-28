node ('Ubuntu-AppServer-agent'){  
    def app
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
       checkout scm
    }  
    
    stage('Build-and-Tag') {
    /* This builds the actual image; synonymous to
         * docker build on the command line */
        app = docker.build("devtraining/snake:askoss")
    }
    stage('Post-to-dockerhub') {
    
     docker.withRegistry('https://registry.hub.docker.com', 'Docker_Hub') {
<<<<<<< HEAD
            app.push("askoss")
=======
            app.push("latest")
>>>>>>> 4b1873979f14979a61fdaa48b6f99b08b36bb30b
                                }
        
         }
    stage('Pull-image-server') {
    
         sh "docker-compose down"
         sh "docker-compose up -d"
<<<<<<< HEAD
=======
        
>>>>>>> 4b1873979f14979a61fdaa48b6f99b08b36bb30b
      }
 } 

