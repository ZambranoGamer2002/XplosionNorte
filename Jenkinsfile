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
                sh 'composer install' // Asume que composer.json está en la raíz del repositorio
            }
        }
        
        stage('Pruebas') {
            steps {
                sh 'vendor/bin/phpunit' // Ejecuta PHPUnit desde vendor/bin (ruta por defecto si se instala con Composer)
            }
        }
        
        // Puedes agregar más etapas aquí, como construcción de assets, análisis estático de código, etc.
        
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
