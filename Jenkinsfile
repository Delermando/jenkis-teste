stage 'Checkout'
 node('slave') {
  deleteDir()
  checkout scm
}

stage 'Build & Archive Apk'
 node('slave') {
  sh 'export ANDROID_SERIAL=192.168.56.101:5555 ; echo $ANDROID_SERIAL > build.txt'
  step([$class: 'ArtifactArchiver', artifacts: 'build.txt'])
 }
