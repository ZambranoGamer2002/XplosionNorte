pipeline {
    agent any
    
    stages {
        stage('Clonar repositorio') {
            steps {
                git 'https://github.com/ZambranoGamer2002/XplosionNorte.git'
            }
        }
        
        stage('Instalar dependencias') {
            steps {
                sh 'composer install' // Instalar dependencias PHP utilizando Composer
            }
        }
        
        stage('Pruebas') {
            steps {
                sh 'phpunit' // Ejecutar pruebas unitarias con PHPUnit (asegúrate de tener las pruebas escritas)
            }
        }
        
        // Puedes agregar más etapas aquí, como construcción de assets, análisis estático de código, etc.
        
        // Etapa de despliegue (opcional)
        stage('Desplegar') {
            steps {
                // Aquí agregarías los comandos necesarios para desplegar tu aplicación
                // Esto depende de tu infraestructura y proceso de despliegue
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
