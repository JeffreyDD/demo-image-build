podTemplate(inheritFrom: 'podman-rootless') {
  node(POD_LABEL) {
    stage('Run shell') {
      container('podman-rootless') {
        git branch: 'main', url: 'https://github.com/JeffreyDD/demo-image-build.git'
        sh "echo hello from $POD_CONTAINER" // displays 'hello from mycontainer'
        sh "podman run ubi8 echo hello"
        sh "podman build -f Dockerfile.busyfedora ."
      }
    }
  }
}
