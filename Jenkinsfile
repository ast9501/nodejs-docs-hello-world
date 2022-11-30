podTemplate(yaml: '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: docker
    image: docker:19.03.1-dind
    securityContext:
      privileged: true
    env:
      - name: DOCKER_TLS_CERTDIR
        value: ""
''') {
    node(POD_LABEL) {
        git 'https://github.com/ast9501/nodejs-docs-hello-world.git'
        container('docker') {
            sh 'docker version && docker build -t nodejs-demo .'
        }
    }
}
