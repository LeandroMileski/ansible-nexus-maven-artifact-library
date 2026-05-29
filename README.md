# ansible-nexus-maven-artifact-library
Goal: Write an Ansible playbook that takes a JAR file path as input and uploads it to a Nexus Maven repository.

ansible-playbook push-artifact.yml  \
    -e "jar_file=./my-app.jar" \
    -e "artifact_id=my-app" \
    -e "version=1.0.0" \ 
    --ask-vault-pass \
    --extra-vars "@vault.yml"