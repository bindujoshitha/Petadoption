pipeline{
    
   agent any
   stages{
       
       stage('Build'){
       steps{
           sh "./mvnw compile"
           echo 'Building the project with maven compile'
       }
		}
		stage('Test'){
		    
		    steps{
		       sh "./mvnw test"
		       echo 'Testing the project with maven'
		       } 
		    }
		stage('Package'){
		steps{
		    
		    sh "./mvnw package"
		    echo "Packaging the project with mvnw"
		}		    
		}

		stage('Containerize'){
		    steps{
		        
		        sh "docker build -t petclinicimage"
		        echo 'containerize the application with docker'
		    }
		    }
		   stage('Deploy'){
		       
		       steps{
		           sh "docker run -d -p 9090:9090 petclinicimage"
		          echo "Deploy the image on docker"
		           
		       }

		   }

		
   }

}
