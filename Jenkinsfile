def numero1 = 10
def numero2 = 30
def suma
def resta
def multiplicacion
def division
def fechaActual = new Date().format('ddMMyyyy')
def nameFile= "calculos_" + fechaActual
def pathCalculos="/tmp/" + nameFile
    
pipeline {
    agent any
    
    stages {
        stage('Ejercicio2 - suma') {
            steps {
                script{
                    suma = numero1 + numero2
                    println suma
                }
            }
        }
        stage('Ejercicio2 - resta') {
            steps {
                script{
                    resta = numero1 - numero2
                    println resta
                }
            }
        }
        stage('Ejercicio2 - multiplicacion') {
            steps {
                script{
                    multiplicacion = numero1 * numero2
                    println multiplicacion
                }
            }
        }
        stage('Ejercicio2 - division') {
            steps {
                script{
                    if (numero1 != 0 || numero2 != 0){
                        division = numero1 / numero2
                        println division
                    }
                }
            }
        }
        stage('Ejercicio2 - Guardar calculos') {
            steps {
                script{
                    sh "truncate -s 0 /tmp/calculos*"
                    readContent = readFile pathCalculos
                    writeFile(file: pathCalculos, text: readContent + suma + "\r\n")
                    readContent = readFile pathCalculos
                    writeFile(file: pathCalculos, text: readContent + resta + "\r\n")
                    readContent = readFile pathCalculos
                    writeFile(file: pathCalculos, text: readContent + multiplicacion + "\r\n")
                    readContent = readFile pathCalculos
                    writeFile(file: pathCalculos, text: readContent + division + "\r\n")
                }
            }
        }
    }
}
