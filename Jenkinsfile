pipeline {
   agent {
       docker {
           image 'qaninja/rubywd'
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
                sh 'bundle exec cucumber -p -ci'
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
