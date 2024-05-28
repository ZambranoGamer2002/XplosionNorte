pipeline {
    agent any
    
    stages {
        stage('Clonar repositorio') {
            steps {
                git 'https://github.com/tu-usuario/tu-repositorio.git'
            }
        }
        
        stage('Construir') {
            steps {
                sh 'mvn clean install' // Ejemplo para construir un proyecto Maven, ajusta según tu tecnología
            }
        }
        
        stage('Pruebas') {
            steps {
                sh 'mvn test' // Ejemplo para ejecutar pruebas unitarias con Maven, ajusta según tu tecnología
            }
        }
        
        stage('Desplegar') {
            steps {
                sh 'ansible-playbook deploy.yml' // Ejemplo para desplegar con Ansible, ajusta según tu tecnología
            }
        }
    }
    
    post {
        success {
            echo '¡Pipeline ejecutada exitosamente!'
            // Aquí puedes agregar notificaciones, acciones adicionales, etc.
        }
        
        failure {
            echo '¡La pipeline ha fallado!'
            // Aquí puedes agregar notificaciones, acciones adicionales, etc.
        }
    }
}
