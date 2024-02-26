// We pass empty values to the static assets bucket variables to make kilonova use the default aws-role provided by the pipeline-definition arguments library.
def runTestTask() {
    sh(script:"""
        docker run \
            --cidfile containerid \
            --user 1000:1000 \
            --network="host" \
            -v /var/run/docker.sock:/var/run/docker.sock \
            -v ${env.WORKING_DIRECTORY}/tmp:${env.WORKING_DIRECTORY}/locks \
            -v /tmp:/tmp \
            -v ${env.WORKING_DIRECTORY}:${env.WORKING_DIRECTORY} \
            -w ${env.WORKING_DIRECTORY} \
            -e GITHUB_USERNAME='${env.GITHUB_CREDENTIALS_USR}' \
            -e GITHUB_PASSWORD='${env.GITHUB_CREDENTIALS_PSW}' \
            -e DOCKER_REGISTRY_SECRET_USERNAME='${env.DOCKER_REGISTRY_CREDENTIALS_USR}' \
            -e DOCKER_REGISTRY_SECRET_PASSWORD='${env.DOCKER_REGISTRY_CREDENTIALS_PSW}' \
            -e DOCKERHUBPRO_REGISTRY_SECRET_USERNAME='${env.DOCKERHUBPRO_REGISTRY_CREDENTIALS_USR}' \
            -e DOCKERHUBPRO_REGISTRY_SECRET_PASSWORD='${env.DOCKERHUBPRO_REGISTRY_CREDENTIALS_PSW}' \
            -e CREDENTIAL_DOCKERHUB_PRO_CREDENTIALS_USER='${env.DOCKERHUBPRO_REGISTRY_CREDENTIALS_USR}' \
            -e CREDENTIAL_DOCKERHUB_PRO_CREDENTIALS_PASSWORD='${env.DOCKERHUBPRO_REGISTRY_CREDENTIALS_PSW}' \
            -e CREDENTIAL_KILONOVA_VERSIONS_SERVICE_ADMIN_TOKEN='${env.CREDENTIAL_KILONOVA_VERSIONS_SERVICE_ADMIN_TOKEN}' \
            -e CREDENTIAL_HARBOR_DOCKER_REGISTRY_RO_USER='${env.DOCKER_REGISTRY_CREDENTIALS_USR}' \
            -e CREDENTIAL_HARBOR_DOCKER_REGISTRY_RO_PASSWORD='${env.DOCKER_REGISTRY_CREDENTIALS_PSW}' \
            -e CREDENTIAL_NPM_PRIVATE_REGISTRY_TOKEN='${env.CREDENTIAL_NPM_PRIVATE_REGISTRY_TOKEN}' \
            -e CREDENTIAL_NPM_ARTIFACTORY_PRIVATE_REGISTRY_TOKEN='${env.CREDENTIAL_NPM_ARTIFACTORY_PRIVATE_REGISTRY_TOKEN}' \
            -e CREDENTIAL_ARTIFACTORY_EDGE_RO_NPM_TOKEN='${env.CREDENTIAL_ARTIFACTORY_EDGE_RO_NPM_TOKEN}' \
            -e CREDENTIAL_KILONOVA_BUCKET_AWS_ACCESS_KEY_ID='${env.CREDENTIAL_KILONOVA_BUCKET_AWS_ACCESS_KEY_ID}' \
            -e CREDENTIAL_KILONOVA_BUCKET_AWS_SECRET_KEY='${env.CREDENTIAL_KILONOVA_BUCKET_AWS_SECRET_KEY}' \
            -e CREDENTIAL_KILONOVA_BUCKET_AWS_KMS_KEY_ID='${env.CREDENTIAL_KILONOVA_BUCKET_AWS_KMS_KEY_ID}' \
            -e CREDENTIAL_KILONOVA_GIT_PRIVATE_KEY='${env.CREDENTIAL_KILONOVA_GIT_PRIVATE_KEY}' \
            -e CREDENTIAL_KILONOVA_GITHUB_USER='${env.GITHUB_CREDENTIALS_USR}' \
            -e CREDENTIAL_KILONOVA_GITHUB_PASSWORD='${env.GITHUB_CREDENTIALS_PSW}' \
            -e CREDENTIAL_SONARQUBE_KBUILD_USERNAME='${env.CREDENTIAL_SONARQUBE_KBUILD_USERNAME}' \
            -e CREDENTIAL_SONARQUBE_KBUILD_PASSWORD='${env.CREDENTIAL_SONARQUBE_KBUILD_PASSWORD}' \
            -e CREDENTIAL_SONARQUBE_KBUILD_SERVER_TOKEN='${env.CREDENTIAL_SONARQUBE_KBUILD_SERVER_TOKEN}' \
            -e CREDENTIAL_NEXUSIQ_USER='${env.CREDENTIAL_NEXUSIQ_USER}' \
            -e CREDENTIAL_NEXUSIQ_PASSWORD='${env.CREDENTIAL_NEXUSIQ_PASSWORD}' \
            -e CREDENTIAL_HARBOR_DOCKER_REGISTRY_USER='${env.DOCKER_REGISTRY_CREDENTIALS_USR}' \
            -e CREDENTIAL_HARBOR_DOCKER_REGISTRY_TOKEN='${env.DOCKER_REGISTRY_CREDENTIALS_PSW}' \
            -e CREDENTIAL_KILONOVA_SLACK_TOKEN='${env.CREDENTIAL_KILONOVA_SLACK_TOKEN}' \
            -e CREDENTIAL_NEWRELIC_INSIGHTS_TOKEN='${env.CREDENTIAL_NEWRELIC_INSIGHTS_TOKEN}' \
            -e CREDENTIAL_HELM_BUCKET_WRITER_AWS_ACCESS_KEY_ID='${env.CREDENTIAL_HELM_BUCKET_WRITER_AWS_ACCESS_KEY_ID}' \
            -e CREDENTIAL_HELM_BUCKET_WRITER_AWS_SECRET_ACCESS_KEY='${env.CREDENTIAL_HELM_BUCKET_WRITER_AWS_SECRET_ACCESS_KEY}' \
            -e CREDENTIAL_MULETEER_REDIS_HOSTNAME='${env.CREDENTIAL_MULETEER_REDIS_HOSTNAME}' \
            -e CREDENTIAL_MULETEER_KOBANI_JWT_TOKEN='${env.CREDENTIAL_MULETEER_KOBANI_JWT_TOKEN}' \
            -e CREDENTIAL_PUBLIC_NEXUS_USER='${env.CREDENTIAL_PUBLIC_NEXUS_USER}'\
            -e CREDENTIAL_PUBLIC_NEXUS_PASSWORD='${env.CREDENTIAL_PUBLIC_NEXUS_PASSWORD}'\
            -e CREDENTIAL_BUILD_NEXUS_USER='${env.CREDENTIAL_BUILD_NEXUS_USER}'\
            -e CREDENTIAL_BUILD_NEXUS_PASSWORD='${env.CREDENTIAL_BUILD_NEXUS_PASSWORD}'\
            -e CREDENTIAL_KILONOVA_REPOSITORY_MASTER_BUILD_USER='${env.CREDENTIAL_KILONOVA_REPOSITORY_MASTER_BUILD_USER}'\
            -e CREDENTIAL_KILONOVA_REPOSITORY_MASTER_BUILD_PASSWORD='${env.CREDENTIAL_KILONOVA_REPOSITORY_MASTER_BUILD_PASSWORD}'\
            -e CREDENTIAL_KILONOVA_NEXUS_BUILD_USER='${env.CREDENTIAL_KILONOVA_NEXUS_BUILD_USER}'\
            -e CREDENTIAL_KILONOVA_NEXUS_BUILD_PASSWORD='${env.CREDENTIAL_KILONOVA_NEXUS_BUILD_PASSWORD}'\
            -e CREDENTIAL_BUILD_ARTIFACTORY_USER='${env.CREDENTIAL_BUILD_ARTIFACTORY_USER}'\
            -e CREDENTIAL_BUILD_ARTIFACTORY_PASSWORD='${env.CREDENTIAL_BUILD_ARTIFACTORY_PASSWORD}'\
            -e CREDENTIAL_ARTIFACTORY_EDGE_RO_USER='${env.CREDENTIAL_ARTIFACTORY_EDGE_RO_USER}'\
            -e CREDENTIAL_ARTIFACTORY_EDGE_RO_PASSWORD='${env.CREDENTIAL_ARTIFACTORY_EDGE_RO_PASSWORD}'\
            -e CREDENTIAL_KILONOVA_ARTIFACTORY_EDGE_BUILD_RO_USER='${env.CREDENTIAL_KILONOVA_ARTIFACTORY_EDGE_BUILD_RO_USER}'\
            -e CREDENTIAL_KILONOVA_ARTIFACTORY_EDGE_BUILD_RO_PASSWORD=='${env.CREDENTIAL_KILONOVA_ARTIFACTORY_EDGE_BUILD_RO_PASSWORD}'\
            -e CREDENTIAL_ARTIFACTORY_MAIN_USER='${env.CREDENTIAL_ARTIFACTORY_MAIN_USER}' \
            -e CREDENTIAL_ARTIFACTORY_MAIN_PASSWORD='${env.CREDENTIAL_ARTIFACTORY_MAIN_PASSWORD}' \
            -e CREDENTIAL_PRE_FALCON_ECR_USER='${env.CREDENTIAL_PRE_FALCON_ECR_USER}' \
            -e CREDENTIAL_PRE_FALCON_ECR_PASSWORD='${env.CREDENTIAL_PRE_FALCON_ECR_PASSWORD}' \
            -e CREDENTIAL_SVC_FALCON_MSFT_IMGS_PAT='${env.CREDENTIAL_SVC_FALCON_MSFT_IMGS_PAT}' \
            -e CREDENTIAL_FALCON_EASY_MTLS_CERT_BASE64='${env.CREDENTIAL_FALCON_EASY_MTLS_CERT_BASE64}' \
            -e CREDENTIAL_FALCON_EASY_MTLS_CERT_KEY_BASE64='${env.CREDENTIAL_FALCON_EASY_MTLS_CERT_KEY_BASE64}' \
            -e CREDENTIAL_SALESFORCE_INTERNAL_DOMAIN_CERT_BASE64='${env.CREDENTIAL_SALESFORCE_INTERNAL_DOMAIN_CERT_BASE64}' \
            -e CREDENTIAL_STATIC_ASSETS_BUCKET_AWS_ACCESS_KEY_ID='' \
            -e CREDENTIAL_STATIC_ASSETS_BUCKET_AWS_SECRET_ACCESS_KEY='' \
            -e CREDENTIAL_STATIC_ASSETS_BUCKET_AWS_KMS_KEY_ID='' \
            -e CREDENTIAL_EVENT_BUS_REDIS_AUTH_TOKEN='${env.CREDENTIAL_EVENT_BUS_REDIS_AUTH_TOKEN}' \
            -e CREDENTIAL_PTS_TOKEN='${env.CREDENTIAL_PTS_TOKEN}' \
            -e CREDENTIAL_KILONOVA_FUNNEL_CRT_BASE64='${env.CREDENTIAL_KILONOVA_FUNNEL_CRT_BASE64}' \
            -e CREDENTIAL_KILONOVA_FUNNEL_CRT_KEY_BASE64='${env.CREDENTIAL_KILONOVA_FUNNEL_CRT_KEY_BASE64}' \
            -e CREDENTIAL_KILONOVA_FUNNEL_PEM_BASE64='${env.CREDENTIAL_KILONOVA_FUNNEL_PEM_BASE64}' \
            -e VERSION_SERVICE_URL=http://kilonova-versions-service.kbuild.msap.io/api/v1 \
            -e HTTP_PORT='8081' \
            -e AGENTS_PORT='50001' \
            -e BUILD_URL='${BUILD_URL}' \
            -e HUDSON_URL='${HUDSON_URL}' \
            -e CLUSTER_CREATION_FL='${env.WORKING_DIRECTORY}'/locks/cluster_lock \
            -e BUILD_KILONOVA_CLI=true \
            -e USE_LOCAL_PIPELINE_DEFINITION=true \
            -e REPOSITORIES='${params.REPOSITORIES}' \
            -e SHOULD_BUILD=true \
            -e SHOULD_DEPLOY=true \
            releases-docker.jfrog.io/jfrog/artifactory-pro:7.71.11@sha256:a026016494439cbd87be19de8b899c738daca6fcd337a792b77386be72af024e
    """,
    label: "Run tests")
}

pipeline {
    agent { label "kilonova" }
    parameters {
        string(name: 'KILONOVA_PIPELINE_BRANCH', defaultValue: 'master', description: 'Branch of the kilonova-pipeline repo to use for the tests.')
        string(name: 'KILONOVA_DEFINITIONS_BRANCH', defaultValue: 'master', description: 'Branch of the kilonova-pipeline-definition repo to use for the tests.')
        string(name: 'REPOSITORIES', defaultValue: 'kilonova-node-npm-lib-example,kilonova-java-maven-library,kilonova-java-gradle-library', description: 'Comma-separated list of repositories to test.')
    }
    environment {
        DOCKER_REGISTRY_CREDENTIALS = credentials('harbor-docker-registry')
        DOCKERHUBPRO_REGISTRY_CREDENTIALS = credentials('dockerhub-pro-credentials')
        GITHUB_CREDENTIALS = credentials('github-exchange')
        CREDENTIAL_NPM_PRIVATE_REGISTRY_TOKEN = credentials('npm-mulesoft')
        CREDENTIAL_NPM_ARTIFACTORY_PRIVATE_REGISTRY_TOKEN = credentials('npm-artifactory-private-registry-token')
        CREDENTIAL_ARTIFACTORY_EDGE_RO_NPM_TOKEN = credentials('artifactory-edge-ro-npm-token')
        CREDENTIAL_KILONOVA_BUCKET_AWS_ACCESS_KEY_ID = credentials('kilonova-bucket-aws-access-key-id')
        CREDENTIAL_KILONOVA_BUCKET_AWS_SECRET_KEY = credentials('kilonova-bucket-aws-secret-key')
        CREDENTIAL_KILONOVA_BUCKET_AWS_KMS_KEY_ID = credentials('kilonova-bucket-aws-kms-key-id')
        CREDENTIAL_HELM_BUCKET_WRITER_AWS_ACCESS_KEY_ID = credentials('helm-bucket-writer-aws-access-key-id')
        CREDENTIAL_HELM_BUCKET_WRITER_AWS_SECRET_ACCESS_KEY = credentials('helm-bucket-writer-aws-secret-access-key')
        CREDENTIAL_KILONOVA_VERSIONS_SERVICE_ADMIN_TOKEN = credentials('kilonova-versions-service-admin-token')
        CREDENTIAL_KILONOVA_GIT_PRIVATE_KEY = credentials('kilonova-git-private-key')
        CREDENTIAL_SONARQUBE_KBUILD_USERNAME = credentials('sonarqube-kbuild-username')
        CREDENTIAL_SONARQUBE_KBUILD_PASSWORD = credentials('sonarqube-kbuild-password')
        CREDENTIAL_SONARQUBE_KBUILD_SERVER_TOKEN = credentials('sonarqube-kbuild-server-token')
        CREDENTIAL_NEXUSIQ_USER = credentials('nexusiq-user')
        CREDENTIAL_NEXUSIQ_PASSWORD = credentials('nexusiq-password')
        CREDENTIAL_KILONOVA_SLACK_TOKEN = credentials('kilonova-slack-token')
        CREDENTIAL_NEWRELIC_INSIGHTS_TOKEN = credentials('newrelic-insights-token')
        CREDENTIAL_PUBLIC_NEXUS_USER = credentials('public-nexus-user')
        CREDENTIAL_PUBLIC_NEXUS_PASSWORD = credentials('public-nexus-password')
        CREDENTIAL_BUILD_NEXUS_USER = credentials('build-nexus-user')
        CREDENTIAL_BUILD_NEXUS_PASSWORD = credentials('build-nexus-password')
        CREDENTIAL_KILONOVA_REPOSITORY_MASTER_BUILD_USER = credentials('kilonova-repository-master-build-user')
        CREDENTIAL_KILONOVA_REPOSITORY_MASTER_BUILD_PASSWORD = credentials('kilonova-repository-master-build-password')
        CREDENTIAL_KILONOVA_NEXUS_BUILD_USER = credentials('kilonova-nexus-build-user')
        CREDENTIAL_KILONOVA_NEXUS_BUILD_PASSWORD = credentials('kilonova-nexus-build-password')
        CREDENTIAL_BUILD_ARTIFACTORY_USER = credentials('build-artifactory-user')
        CREDENTIAL_BUILD_ARTIFACTORY_PASSWORD = credentials('build-artifactory-password')
        CREDENTIAL_ARTIFACTORY_EDGE_RO_USER = credentials('artifactory-edge-ro-user')
        CREDENTIAL_ARTIFACTORY_EDGE_RO_PASSWORD = credentials('artifactory-edge-ro-password')
        CREDENTIAL_KILONOVA_ARTIFACTORY_EDGE_BUILD_RO_USER = credentials('kilonova-artifactory-edge-build-ro-user')
        CREDENTIAL_KILONOVA_ARTIFACTORY_EDGE_BUILD_RO_PASSWORD = credentials('kilonova-artifactory-edge-build-ro-password')
        CREDENTIAL_ARTIFACTORY_MAIN_USER = credentials('artifactory-main-user')
        CREDENTIAL_ARTIFACTORY_MAIN_PASSWORD = credentials('artifactory-main-password')
        CREDENTIAL_MULETEER_REDIS_HOSTNAME = credentials('muleteer-redis-hostname')
        CREDENTIAL_MULETEER_KOBANI_JWT_TOKEN = credentials('muleteer-kobani-jwt-token')
        CREDENTIAL_PRE_FALCON_ECR_USER = credentials('pre-falcon-ecr-user')
        CREDENTIAL_PRE_FALCON_ECR_PASSWORD = credentials('pre-falcon-ecr-password')
        CREDENTIAL_SVC_FALCON_MSFT_IMGS_PAT = credentials('svc-falcon-msft-imgs-pat')
        CREDENTIAL_FALCON_EASY_MTLS_CERT_BASE64 = credentials('falcon-easy-mtls-cert-base64')
        CREDENTIAL_FALCON_EASY_MTLS_CERT_KEY_BASE64 = credentials('falcon-easy-mtls-cert-key-base64')
        CREDENTIAL_SALESFORCE_INTERNAL_DOMAIN_CERT_BASE64 = credentials('salesforce-internal-domain-cert-base64')
        CREDENTIAL_EVENT_BUS_REDIS_AUTH_TOKEN = credentials('event-bus-redis-auth-token')
        CREDENTIAL_PTS_TOKEN = credentials('pts_token')
        CREDENTIAL_KILONOVA_FUNNEL_CRT_BASE64 = credentials('kilonova-funnel-crt-base64')
        CREDENTIAL_KILONOVA_FUNNEL_CRT_KEY_BASE64 = credentials('kilonova-funnel-crt-key-base64')
        CREDENTIAL_KILONOVA_FUNNEL_PEM_BASE64 = credentials('kilonova-funnel-pem-base64')
    }

    stages {
        stage('Checkout') {
            steps {
                dir("integration-tests") {
                    dir("kilonova-pipeline") {
                        checkout([
                            $class: 'GitSCM',
                            branches: [[name: "${params.KILONOVA_PIPELINE_BRANCH}"]],
                            extensions: [
                                [$class: 'SubmoduleOption', recursiveSubmodules: true]
                            ],
                            submoduleCfg: [],
                            userRemoteConfigs: [[
                                url: 'https://github.com/mulesoft/kilonova-pipeline.git',
                                credentialsId: scm.userRemoteConfigs[0].getCredentialsId()
                            ]]
                        ])
                    }

                    dir("kilonova-pipeline-definition") {
                        checkout([
                            $class: 'GitSCM',
                            branches: [[name: "${params.KILONOVA_DEFINITIONS_BRANCH}"]],
                            extensions: [
                                [$class: 'SubmoduleOption', recursiveSubmodules: true]
                            ],
                            submoduleCfg: [],
                            userRemoteConfigs: [[
                                url: 'https://github.com/mulesoft/kilonova-pipeline-definition.git',
                                credentialsId: scm.userRemoteConfigs[0].getCredentialsId()
                            ]]
                        ])
                    }
                }
            }
        }

        stage('Integration Tests') {
            environment {
                WORKING_DIRECTORY = "${env.WORKSPACE}/integration-tests"
            }
            steps {
                lock(inversePrecedence: true, resource: "${NODE_NAME}") {
                    dir("integration-tests") {
                        timeout(time: 60, unit: 'MINUTES') {
                            sh("mkdir -p /tmp/jenkins")
                            sh(script:"mkdir tmp")
                            sh(script:"echo '${env.DOCKER_REGISTRY_CREDENTIALS_PSW}' | docker login -u '${env.DOCKER_REGISTRY_CREDENTIALS_USR}' --password-stdin artifacts.msap.io", label:"log in to artifacts.msap.io")
                            script {
                                try {
                                    runTestTask()
                                } finally {
                                    sh("docker stop \$(cat containerid)")
                                    docker.image('releases-docker.jfrog.io/jfrog/artifactory-pro:7.71.11@sha256:a026016494439cbd87be19de8b899c738daca6fcd337a792b77386be72af024e').inside('-u root:root') {
                                        steps.sh("rm -rf integration-tests")
                                    }
                                    sh("rm -rf .docker /tmp/jenkins")
                                }
                            }
                        }
                    }
                }
            }
            post {
                always {
                    sh("rm -rf integration-tests")
                }
            }
        }
    }
}