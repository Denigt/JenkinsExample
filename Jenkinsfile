def fileName = "file.txt"

def var1 = 8
def var2 = 4

def pow(int number, int exp) {
    def result = 1
    
    def i = 0
    while (i < exp) {
        result = result * number
        i += 1
    }
    return result
}

pipeline {
    agent any

    stages {
        stage('Crear fichero y realizar operaciones') {
            steps {
                script {
                    def suma = var1 + var2
                    def potencia = pow(suma, 2)
                    writeFile(file: fileName, text: "${var1} + ${var2} = ${suma}\n${suma}^2 = ${potencia}")
                }
            }
        }
        stage('Mostrar contenido del fichero') {
            steps {
                script {
                    echo readFile(file: fileName)
                }
            }
        }
    }
}
