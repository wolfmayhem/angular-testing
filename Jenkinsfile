node {
stage ('Checkout') {
checkout scm
}
stage ('Build') {
docker.image('trion/ngc-li').inside {
sh 'npm install'
sh 'ngbuild --progress false --prod --aot'
sh ' tar -cvzf dist.tar. gz --strip components=1 dist'
}
archive' dist.tar.gz'
}
stage ('Test') {
docker.image ('trion/ng cli -karma').inside {
sh'ng test --progress false --watch false'
}
}
}
