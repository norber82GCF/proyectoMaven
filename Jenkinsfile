pipeline{

    agent any
    
    stages {
        stage("Descargar fuentes - git") {
            steps {
                git 'https://github.com/norber82GCF/proyectoMaven.git'
            }
        }
        
        stage("Maven") {
            steps{
                sh "mvn compile"
                sh "mvn test-compile"
                sh "test"
                sh "package"
            }
        }
        
        stage("sonarQube") {
            steps{
                sh "TODO pruebas sonarQube"
            }
        }
        
        
    }
    
    post {
       always { // Post tareas que siempre deben de ejecutarse
          sh "echo Final"
       }
       success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
          sh "echo finalizacion correcta"
       }
       failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
          sh "echo finalizado con errores"
       }
    }

}