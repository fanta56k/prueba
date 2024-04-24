def numero1 = 10
def numero2 = 30
def suma
def nameFile= "calculosejercicionuevo"
def pathCalculos="/tmp/" + nameFile
    
pipeline {
    agent any
    
    options{
        timeout(time:5,unit:'MINUTES')
    }
    
    
    stages {
        stage('stage 1') {
            steps {
                script{
                    suma = numero1 + numero2
                    println suma
                }
            }
        }
        stage('stage 2') {
            steps {
                script{
                    sh "truncate -s 0 /tmp/calculosejercicionuevo*"
                    sh "uptime"
                    sh "ss -atunp | grep -i listen"
                }
            }
        }

        stage('stage3') {
            steps {
                script{
                    writeFile(file: pathCalculos, text: "Informacion del stage1: Suma 2 numeros y lo imprime por consola")
                    println "Se ha creado el archivo " + pathCalculos
                }
            }
        }
    }

    post{
        always{
            echo "El pipeline se ejecutó"
        }
    }
    
    
}
