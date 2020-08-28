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

            app.push("askoss")
                                }
        
         }
    stage('Pull-image-server') {
    
         sh "docker-compose down"
         sh "docker-compose up -d"

      }
 } 

