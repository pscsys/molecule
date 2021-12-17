pipeline {

  agent any

  stages {

    stage ('Display versions') {
      steps {
        sh '''
          . /var/lib/jenkins/molecule_podman/.venv/bin/activate
          python -V
          ansible --version
          molecule --version
        '''
      }
    }

    stage ('Molecule test') {
      steps {
        sh '''
          . /var/lib/jenkins/molecule_podman/.venv/bin/activate
          cd /var/lib/jenkins/molecule_podman/adriagalin.motd
          molecule test
        '''
      }
    }
  }
}
