pipeline {
   agent {
       docker {
           image 'ruby'
       }
   }

   stages {
       stage('Build'){
           steps {
               echo 'building or resolve dependencies'
               sh 'bundle install'
           }
       }
        stage('Tests'){
            steps {
                echo 'Running regression tests'
            }
        }
        stage('UAT'){
            steps {
                echo 'Wait for user aceptance'
                input(message:'Go to production?', ok:'Yes')
            }
        }
        stage('Prod'){
            steps {
                echo 'Webapp is ready :)'
            }
        }
   }
}
