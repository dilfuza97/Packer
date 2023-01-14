 stage('generate provenance') {
            steps {
                dir("../workspace") {
                    dir("slsa-jenkins-generator") {
                        script {
                            env_path = sh(script: 'pwd', returnStdout: true).trim()
                            sh "printenv > ${env_path}/.env"
                            env_path = "${env_path}"+"/.env"
                        }
                        step([$class: 'ProvenanceGenerator', artifact:artifact_path, output:output_path, envpath:env_path])
                    }
                }
            }
        }
