// pipeline {
//     agent any

//     stages {
//         stage('Git Checkout') {
//             steps {
//                 git 'https://github.com/Mahajayanthi/gradleproject.git'
//             }
//         }
        
//         stage('Build') {
//             steps {
//                 sh 'gradle clean build -p gradleproject'
//             }
//         }
        
//         stage('Test') {
//             steps {
//                 sh 'gradle test -p gradleproject'
//             }
//         }
        
//         stage('Package') {
//             steps {
//                 sh 'gradle assemble -p gradleproject'
//             }
//         }
//     }
// }
// pipeline {
//     agent any
//     stages {
//         stage('git repo & clean') {
//             steps {
//                 script {
//                     // Check if directory exists before removing it
//                     if (fileExists('gradleproject')) {
//                         bat "rmdir /s /q gradleproject"
//                     }
                    
//                     bat "git clone https://github.com/Mahajayanthi/gradleproject.git"
//                     bat "gradle clean -p gradleproject"
//                 }
//             }
//         }
//         stage('build') {
//             steps {
//                 bat "gradle build -p gradleproject"
//             }
//         }
//         stage('test') {
//             steps {
//                 bat "gradle test -p gradleproject"
//             }
//         }
//     }
// }

// def fileExists(String path) {
//     try {
//         fileExists = new File(path).isDirectory()
//     } catch (Exception e) {
//         fileExists = false
//     }
//     return fileExists
// }
pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
                script {
                    // Check if directory exists before removing it
                    if (fileExists('gradleproject')) {
                        bat "rmdir /s /q gradleproject"
                    }
                    
                    bat "git clone https://github.com/Mahajayanthi/gradleproject.git"
                    bat "gradle clean -p gradleproject"
                }
            }
        }
        stage('build') {
            steps {
                bat "gradle build -p gradleproject"
            }
        }
        stage('test') {
            steps {
                bat "gradle test -p gradleproject"
            }
        }
    }
}

def fileExists(String path) {
    try {
        fileExists = new File(path).isDirectory()
    } catch (Exception e) {
        fileExists = false
    }
    return fileExists
}
