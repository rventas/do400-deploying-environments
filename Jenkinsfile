pipeline {
agent {
node {
label 'maven'
}
}
stages {
stage('Tests') {
steps {
sh './shopping-cart/mvnw clean test'
}
}
stage('Package') {
steps {
sh '''
./shopping-cart/mvnw package -DskipTests \
-Dquarkus.package.type=uber-jar
'''
archiveArtifacts 'target/*.jar'
}
}
}
}