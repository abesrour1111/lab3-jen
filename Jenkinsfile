pipeline {
  agent any
  stages {
    stage('stage 1') {
      parallel {
        stage('stage 1') {
          steps {
            sh '''cut -d: -f1,3 /etc/passwd > /tmp/users
cut -d: -f1,3 /etc/passwd > /tmp/users'''
          }
        }

        stage('stage 1-2') {
          steps {
            sh 'cut -d: -f4 /etc/passwd |sort | uniq > /tmp/ids_groupes_prim'
          }
        }

        stage('stage 1-3') {
          steps {
            sh 'cut -d : -f3 /etc/group >/tmp/id_groupes'
          }
        }

      }
    }

    stage('stage 2') {
      steps {
        echo "ok"
	sh 'wc -l /tmp/ids_groupes_prim|cut -d' ' -f1'
        sh 'wc -l /tmp/id_groupes | cut -d' ' -f1'
      }
    }

  stage ('test') {
    when {expression { nombre == nombre2 }}
    steps {

echo "les fichiers sont identiques"
}

}
}
    post
    {
      failure {
      echo "les fichiers sont différents"
      }
      success
      {
       echo "les fichiers sont identiques "
      }
      always
      {
       echo "fin de l'exercice" 
      }
    }

  
}
